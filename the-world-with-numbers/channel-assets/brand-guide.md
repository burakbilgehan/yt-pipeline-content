# The World With Numbers: Brand Guide (v7)

Rules for how the channel looks and sounds. Exact values (hex colors, px sizes, easing curves, durations, atmosphere numbers) live only in `yt-pipeline/src/remotion/catalog/tokens.ts`; this guide names tokens and never restates their values. The research behind v7 is in `research/brand/` (dated records, not rules). Supersedes v6 (26.09.2026, owner direction: darker, premium, never loud, neutral enough for statistics).

## Position and voice

- The calm, late-night desk lamp of data YouTube: one well-lit fact at a time, sourced, measured and shown to scale.
- Number first, then context, then source. Short declarative sentences; the drama is in the magnitude.
- Name units and years every time. Say "we do not know" when the data ends.
- Never: hype words, stacked rhetorical questions, exclamation marks on screen, emoji, whooshes or hit stingers on data beats. A value can be "the highest on record", never "outrageous".

## Color

- Every frame is `bg`, flat. Cards, chips and digit cells use `surface`, then `surface2`; elevation is lightness only, no shadows.
- `highlight` marks the one thing the narration is about: at most one item or one series per scene. `contrast` only when the narration names a second item. Everything else is `dataNeutral`.
- Text: `textPrimary` for titles and values that matter, `textSecondary` for labels, `textTertiary` only at caption size.
- No red/green pair, no positive/negative colors: direction is a sign and an arrow.
- Every mark (bar, segment, panel, digit cell) has a subtle corner, `SHAPE.radius`; a bar rounds only its value end, its baseline stays square. Cards use `SHAPE.cardRadius`, chips are pills. (user, 27.09.2026)

## Type

- Four roles only (`TYPE.giant`, `value`, `body`, `caption`), each at one of its token sizes. `giant` (the display family) is the number or phrase the scene is about; everything else, every mark value included, is in the text family.
- Headers, labels, chips, panels and sources are captions: uppercase and tracked.

## Atmosphere

- Every frame: film grain at the `ATMOSPHERE.grain` settings. Depth comes from 3D layers, cards and turns (`MOTION`), not from light.
- Never a glow, gradient, shadow or texture on data marks or text. No other effect exists and a storyboard cannot request one.

## Motion

- A "kick" (a short shake or punch of the frame) is an accent for a few key moments, never rhythmic or periodic: no pulse or heartbeat on every beat. Ambient motion is slow drift only; energy comes from cuts, 3D turns and moves that carry information. (user, 26.09.2026)
- One type system per video: the heading family and the body family from the tokens, nothing else. (user, 26.09.2026)

## Maps

- Routes, pipelines, shipping lanes and borders come from sourced coordinates recorded in the video's `research/`; a simplified path is labeled "schematic" on screen. Never sketch geography by eye. (user, 26.09.2026)

## Imagery

- No photographs and no AI-generated images. The vocabulary is type, numbers, bars, lines, maps (Natural Earth, Equal Earth projection), flags and Lucide icons.
- No people on screen. Objects (tankers, barrels, pipes, devices) are clean vector drawings, not photos or renders. (user, 26.09.2026)
- The channel has no logo yet; its name is set in plain type.

## Sound

- Ambient or lo-fi instrumental, 60 to 85 bpm, no vocals and no drum hit on a data beat, at least 18 LU under the voice.
- Sources: YouTube Audio Library (attribution not required filter), Pixabay Content License, Free Music Archive CC0 or CC BY only.

## Scenes and charts

Scene types, layout and honest-chart rules are defined by the scene catalog: `yt-pipeline/src/remotion/catalog/schema.ts` (what a scene may contain) and the `storyboard` skill (how to choose one).
