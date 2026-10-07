# Кабанчик · Kabanchik

A curious little boar for your workspace. Charcoal bristles, amber eyes, ivory tusks—and a determined attitude toward the next task.

[Русский](README.ru.md) · [Sprite sheet](assets/kabanchik.png) · [Animation video](previews/all-states.mp4) · [MIT license](LICENSE)

![Kabanchik animation](previews/all-states.gif)

## What is included

- A transparent PNG sprite sheet with **73 poses**.
- Nine animations: idle, running right, running left, waving, jumping, failure, waiting, working, and review.
- Sixteen clockwise head and gaze directions.
- Individual GIF previews, an all-state GIF/MP4, a jump transition, and contact sheets.
- A machine-readable [sprite manifest](spritesheet.json) and a [character prompt](prompts/character.md).

## Use the artwork

Download [assets/kabanchik.png](assets/kabanchik.png) and [spritesheet.json](spritesheet.json), or clone this repository. The artwork can be used in a compatible pet renderer, a game, a desktop companion, or another creative project under the MIT license.

The sheet follows the ChatGPT Work Pets v2 geometry:

| Property | Value |
| --- | --- |
| Image | 1536 × 2288 px, PNG with alpha |
| Grid | 8 columns × 11 rows |
| Cell | 192 × 208 px |
| Populated cells | 73 |
| Empty cells | 15, fully transparent |

To extract a frame, crop the rectangle starting at `x = column × 192`, `y = row × 208`, with width `192` and height `208`. Indices start at zero. Animation frames occupy the leftmost cells in each row; unused cells stay transparent.

| Row | State | Frames |
| --- | --- | ---: |
| 0 | idle | 6 |
| 1 | running-right | 8 |
| 2 | running-left | 8 |
| 3 | waving | 4 |
| 4 | jumping | 5 |
| 5 | failed | 8 |
| 6 | waiting | 6 |
| 7 | running — focused work/thinking | 6 |
| 8 | review | 6 |
| 9 | look: 0° → 157.5° | 8 |
| 10 | look: 180° → 337.5° | 8 |

Gaze angles advance clockwise: **0° up, 90° screen-right, 180° down, 270° screen-left**. The near-vertical intermediate poses have subtle horizontal cues. Per-frame timing is in the manifest.

## Previews

![Four poses](previews/four-poses.png)

[All states](previews/contact-sheet.png) · [Look directions](previews/look-directions.png) · [Look loop](previews/look-loop.gif) · [Idle → jump → idle](previews/idle-jump-idle.gif)

## Creation and validation

Created in October 2026 with OpenAI image generation and the Pets workflow in Codex. A user-provided wild-boar engraving inspired the character. The published assets are the generated boar artwork; the original reference image is not included. This is a community artwork project and is not affiliated with or endorsed by OpenAI.

The release sheet passed structural and transparency checks, animation frame checks, jump-lift and registration checks, and independent direction review. File hashes are recorded in [CHECKSUMS.sha256](CHECKSUMS.sha256).

## Contributing

Bug reports, animation improvements, and integrations are welcome. Keep the character recognizable, preserve the transparent cell padding, and include a before/after preview with artwork changes. Update the manifest and checksums when replacing assets.

## License

[MIT](LICENSE). The license covers the material distributed in this repository. The artwork was generated with AI assistance.
