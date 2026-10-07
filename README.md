# Kabanchik

An animated boar companion for your workspace, game, or desktop. Kabanchik has charcoal bristles, amber eyes, small ivory tusks, and a curious, determined personality.

This open-source artwork pack includes a transparent sprite sheet, animation metadata, and ready-to-view previews, all released under the MIT license.

[Sprite sheet](assets/kabanchik.png) · [Animation video](previews/all-states.mp4) · [MIT license](LICENSE) · [Russian README](README.ru.md)

![Kabanchik animation](previews/all-states.gif)

## What's included

- **73 poses** in a single transparent PNG sprite sheet.
- **Nine animations:** idle, running right, running left, waving, jumping, failure, waiting, focused work, and review.
- **16 head and gaze directions**, arranged clockwise.
- GIF previews for each animation, a combined GIF and MP4, a gaze loop, and an idle-to-jump transition.
- A [sprite manifest](spritesheet.json) with frame coordinates and timing, plus the [character prompt](prompts/character.md).

## Getting started

Download [assets/kabanchik.png](assets/kabanchik.png) and [spritesheet.json](spritesheet.json), or clone the repository:

```sh
git clone https://github.com/Efansson/kabanchik-pet.git
```

Use the sprite sheet and manifest in a compatible animation renderer, game, or desktop companion. The repository contains the artwork and metadata; you supply the renderer.

## Sprite sheet format

The layout follows the ChatGPT Work Pets v2 geometry:

| Property | Value |
| --- | --- |
| Image | 1536 × 2288 px, PNG with alpha |
| Grid | 8 columns × 11 rows |
| Frame size | 192 × 208 px |
| Populated cells | 73 |
| Empty cells | 15, fully transparent |

Rows and columns are zero-indexed. To extract a frame, crop a **192 × 208 px** rectangle with its top-left corner at:

```text
x = column × 192
y = row × 208
```

Animation frames start in the leftmost cell of each row. Unused cells are fully transparent.

| Row | State | Frames |
| --- | --- | ---: |
| 0 | idle | 6 |
| 1 | running-right | 8 |
| 2 | running-left | 8 |
| 3 | waving | 4 |
| 4 | jumping | 5 |
| 5 | failed | 8 |
| 6 | waiting | 6 |
| 7 | running (focused work/thinking) | 6 |
| 8 | review | 6 |
| 9 | look: 0° → 157.5° | 8 |
| 10 | look: 180° → 337.5° | 8 |

Gaze angles advance clockwise: **0° up, 90° screen-right, 180° down, and 270° screen-left**. Intermediate poses near the vertical axis use subtle horizontal cues. See the [manifest](spritesheet.json) for individual frame durations.

## Previews

![Four poses](previews/four-poses.png)

[All poses](previews/contact-sheet.png) · [Gaze directions](previews/look-directions.png) · [Gaze loop](previews/look-loop.gif) · [Idle → jump → idle](previews/idle-jump-idle.gif)

## How it was made

Kabanchik was created in October 2026 using OpenAI image generation and the Pets workflow in Codex, inspired by a wild-boar engraving. This repository contains the generated artwork; the original reference image is not included.

The sprite sheet was checked for grid structure, transparency, frame counts, jump movement, pose alignment, and gaze direction. File hashes are listed in [CHECKSUMS.sha256](CHECKSUMS.sha256).

This is an independent community project and is not affiliated with or endorsed by OpenAI.

## Contributing

Bug reports, animation improvements, and integrations are welcome. When changing the artwork:

- Keep the character recognizable and preserve the transparent padding around each frame.
- Include previews showing the animation before and after your changes.
- Update the manifest when frame layout or timing changes, and refresh the checksums for modified files.

## License

Released under the [MIT license](LICENSE), which covers the materials distributed in this repository. The artwork was generated with AI assistance.
