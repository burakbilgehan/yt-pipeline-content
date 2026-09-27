# Brand Direction: The World With Numbers, v7 color and atmosphere layer

Date: 2026-09-26. Scope: the brand layer on top of work/design-brief.md (catalog v1). Layout, type scale, motion tokens and the ten scene types stay; this document replaces colour, atmosphere, the heading font and the matching rules in brand-guide.md v6. Every measured number comes from work/brand-tools/palette-check.mjs (`node palette-check.mjs` reproduces them).

Owner constraints in priority order: premium; never loud, playful, over-saturated or gimmicky; neutral, credible, data first. The "2 am music video" reference is a mood target, not a licence for effects: the default frame is flat, texture and light are optional and gated.

## 1. Positioning statement

The World With Numbers is the calm, late-night desk lamp of data YouTube: one well-lit fact at a time, sourced, measured and shown to scale, for people who would rather see a chart than hear a take. It looks like a quiet studio at night, not a dashboard and not a music video: near-black navy, one warm pink highlight, one cool blue comparison, everything else gray. It never shouts, never rounds a number to win an argument, never lets decoration touch a data mark.

## 2. Voice rules

Do: number first, then context, then source. Short declarative sentences; the drama is in the magnitude, not the adjectives. Name units and years every time. Say "we do not know" when the data ends. Let a big number sit in silence for a beat. Source line in the footer of every data scene, same place.

Do not: hype words (insane, shocking, destroyed), stacked rhetorical questions, countdown suspense. No editorializing: a value can be "the highest on record", never "outrageous". No exclamation marks on screen. No emoji, whooshes or hit stingers on data beats. No animation without information (design-brief principle 3). No red/green for good/bad; direction is a sign and an arrow.

Pacing: narration at the calibrated 127 wpm, a visual change every 3 to 5 seconds, music at least 18 LU under the voice with no drum hit on a data beat.

## 3. Mood keywords

Quiet studio at night. Desk lamp, not neon sign. Warm light in a cold room. Measured, unhurried, precise. Matte, not glossy. Deep and still. Editorial, not startup. Credible before beautiful.

## 4. What makes late-night visuals feel premium instead of cheap

The references (Lofi Girl, synthwave visualizers, melodysheep, Kurzgesagt's darker episodes, Material and Uxcel dark-mode guidance, Datawrapper) agree, and most of it is restraint.

Palette structure: one very dark, slightly cool, low-chroma base; surface steps that differ by lightness only (Material expresses dark elevation with lighter surfaces, not shadows); one warm accent as the single point of interest; one cool accent for contrast; grays for everything else. The eye goes to the most saturated colour first (Datawrapper), so only the story item gets it.

Value contrast, not hue contrast: a long tonal range (L* 8 background, L* 94 text, 14.7:1) with accents in the middle (L* 62 to 67). v6 looks washed out because its background is L* 17: the accents have nowhere to be brighter than the room.

Saturation discipline: synthwave runs maximum chroma against maximum darkness and reads as neon; Material asks for desaturated accents because saturated colour vibrates on dark. The target sits between: OKLCH chroma 0.11 to 0.15 for accents (#FF2D8F, a neon pink, is 0.25). Base and surfaces stay at chroma 0.016 to 0.023 so the navy is felt, not seen.

Light, texture, motion: lofi calm comes from one warm light source in a dark surround; in a chart that is at most one soft off-centre light at single-digit opacity and a shallow vignette, never bloom on data (a glowing bar has no honest edge). Fine monochrome grain under 10 percent makes flat colour feel like a material; coloured grain, scanlines and VHS artefacts read as costume. Ambient motion is measured in pixels per second, not per frame.

## 5. Palette v7

Background is a grayish near-black navy (OKLCH L 0.211, chroma 0.016, hue 274): navy next to a pure gray, near-black on its own. Text stays faintly warm (hue 85, chroma 0.006) so text and pink share a temperature and the blue reads as the cold one.

| Role | Hex | Use | vs bg | vs surface | vs surface-2 |
|---|---|---|---|---|---|
| bg | #161820 | the only page background | 1.00 | 1.10 | 1.24 |
| surface | #1E212A | header band, footer band, table rows | 1.10 | 1.00 | 1.12 |
| surface-2 | #262A36 | annotation plates, map label plates, alternate rows | 1.24 | 1.12 | 1.00 |
| grid | #30353F | gridlines, axis lines, hairlines | 1.44 | 1.31 | 1.16 |
| text-primary | #ECEAE6 | titles, values that matter | 14.74 | 13.38 | 11.92 |
| text-secondary | #A7ABB6 | labels, secondary values | 7.71 | 7.00 | 6.23 |
| text-tertiary | #6F7483 | ticks, source, inactive | 3.80 | 3.45 | 3.07 |
| highlight | #F27FA3 | the story item, max one per scene; also allowed as text colour for the display number | 7.03 | 6.39 | 5.69 |
| contrast | #5A9BD8 | the second series or comparison item | 6.00 | 5.45 | 4.85 |
| data-neutral | #5E6474 | every other bar, line, country | 3.00 | 2.72 | 2.42 |
| ambient (optional) | #F27FA3 at 6 percent | the one allowed light tint, tier 1 scenes only | n/a | n/a | n/a |

Ratios are WCAG 2.x contrast. Text-primary and text-secondary pass AA (4.5:1) on every surface and AAA (7:1) on bg. Text-tertiary is used only at caption size (24 px, the floor, equal to 18 pt large text) and passes the 3:1 large-text threshold everywhere. Both accents pass 4.5:1 on every surface, so values may be set in accent colour. Data-neutral meets the 3:1 non-text threshold on bg (3.00) but not on surfaces (2.72, 2.42), so bars are always drawn on bg, never inside a plate, as the catalog already does. Text inside a highlight bar is not allowed (2.10); values sit beside the bar end.

Chroma: highlight 0.145, contrast 0.113 (v6: 0.115 and 0.069 on an L* 17 background, the washed-out look). The accents are vivid because the room is darker, not because chroma went to neon.

## 6. Colour-deficiency check

Method: Machado, Oliveira and Fernandes (2009) matrices at severity 1.0 from the colour-science dataset, applied in linear RGB (DaltonLens shows that applying them to gamma-encoded sRGB invalidates the result), converted back to sRGB, compared with CIEDE2000.

Deuteranopia (most common): highlight becomes #AEABA0 (warm gray), contrast #7091D7 (still blue). Distance 29.3 dE2000; highlight to data-neutral 29.8; contrast to neutral 23.0. All three roles separate with wide margins.

Protanopia: highlight becomes #9196A4, contrast #819DDB. Distance 13.8 (above 10 reads as different colours), highlight to neutral 19.0, contrast to neutral 24.6. The weak spot: the pink loses its hue and survives as "the lighter gray", so for a protanope the highlight is carried by lightness (L* 62 against neutral L* 42). Acceptable because the catalog never relies on colour alone: the highlight item is also the one the narration names and labels in text-primary. Grayscale check (Datawrapper's "get it right in black and white") passes: highlight L* 67, contrast 62, neutral 42, bg 8.

Verdict: pass for both. No change to the pink/blue pair is needed; a red/green pair would have failed, which confirms design-brief's decision not to have one.

## 7. Atmosphere layer spec (Remotion, free, deterministic)

Two tiers. Tier 0 is every frame. Tier 1 is allowed only on chapter-card, statement, intro and outro, which contain no data marks; all eight data scene types stay at tier 0.

Tier 0, always on:

1. Background: flat #161820. No gradient.
2. Elevation by lightness only (surface, surface-2). No box-shadow, no border glow; a 1 px hairline in grid colour where a plate needs an edge.
3. Film grain: one full-frame SVG on top of everything, `mix-blend-mode: overlay`, opacity 0.035. Filter: `feTurbulence type="fractalNoise" baseFrequency="0.85" numOctaves="2" stitchTiles="stitch"`, then `feColorMatrix type="saturate" values="0"` (monochrome; colour grain reads as VHS). Seed is a pure function of the frame, `seed = 11 + (Math.floor(frame / 2) % 8)`: eight fixed patterns cycling at 15 Hz, identical on every render. Render through a 384x384 `<pattern>` tile, not a full-frame filter region, to keep frame time low. At 3.5 percent overlay its effect on contrast is well under 0.1 (estimate, not measured).
4. Nothing else on data scenes: no vignette, no light, no glow.

Tier 1, optional, non-data scenes only:

5. Ambient light: one radial gradient between bg and content, `radial-gradient(ellipse 70% 70% at X Y, rgba(242,127,163,0.06) 0%, rgba(242,127,163,0) 55%)`. Anchor X = 18 percent, Y = 10 percent of the frame. Drift with t = frame / 30: `X += 40 * sin(2π t / 24)`, `Y += 24 * sin(2π t / 31)` px, peak speed under 12 px per second, never leaving the top-left quadrant.
6. Vignette: `radial-gradient(ellipse 80% 80% at 50% 50%, rgba(0,0,0,0) 55%, rgba(0,0,0,0.18) 100%)` above the light, under content. Darkening the bg raises text contrast; it never lowers it.
7. Glow: exactly two elements, the chapter-card highlight rule and the outro logo mark, `filter: drop-shadow(0 0 12px rgba(242,127,163,0.35))`. Never on text, data marks or plates.

Never on bars, lines, areas, map fills, waffle squares, table cells, axis lines or text: a glow softens the edge of a shape whose length is the data, and a gradient behind a bar changes its apparent length.

Replacement rule (supersedes brand-guide v6 "Background is always solid; no gradient backgrounds unless specified in storyboard" and design-brief "no gradients, no vignettes"): The background is flat #161820 on every frame. On chapter-card, statement, intro and outro, and only there, the stage may add one ambient light (highlight colour, 6 percent, top left, drift under 12 px per second) and one vignette (18 percent at the corners). Grain at 3.5 percent overlay is on every frame. No other gradient, glow, shadow or texture exists in the design system, and the storyboard cannot request one.

## 8. Typography decision

Inter stays for display, body and caption: it has tabular figures, it is neutral, and the numbers are the hero. Montserrat goes. Its wide, round geometric capitals are friendly and slightly loud; at 88 px ExtraBold they read as a landing page, and "never a clown" plus the late-night mood call for a tighter, cooler heading face. Replacement: Manrope for h1 and h2, weights 800 and 700, same sizes, line heights and tracking. Manrope is a semi-condensed geometric grotesque, OFL-1.1, variable 200 to 800, present in @remotion/google-fonts (getInfo lists 200 through 800).

Not chosen: Inter for everything (headings lose distinction from body at 52 px); Sora and Plus Jakarta Sans (rounder, closer to the problem than the fix); IBM Plex Sans (corporate). Flip condition: if Manrope 800 at 88 px looks too narrow in the showcase render, keep Montserrat at weight 700; the palette carries most of the improvement.

## 9. Changes versus brand-guide v6 (replace list)

1. Section 1 palette table: replace with the v7 table. #2A2A32 becomes #161820; #E88CA5 becomes #F27FA3; #7BA7C9 becomes #5A9BD8; #F0EDE8 becomes #ECEAE6; Surface #2E2E38 becomes #1E212A plus a new surface-2 #262A36; Axis/Grid rgba becomes solid #30353F; Border rgba is deleted.
2. Delete Positive #5BBF8C and Negative #E06070 (and #76B896, #C96B7A in channel-config.json and design-system.json). Direction is sign plus arrow (design-brief section 2).
3. Colour rules: replace "Background is always solid #2A2A32; no gradient backgrounds unless explicitly specified in storyboard" with the replacement rule in section 7. Keep no gradient text, no pure white, max two data colours, never hardcode hex.
4. Section 2 typography: headings Montserrat becomes Manrope 700/800; labels, numbers and body Montserrat become Inter with tabular-nums; the size list becomes the five-role scale of design-brief section 2.
5. Section 3: film grain opacity 0.03 becomes 0.035 with the monochrome and frame-seed rules; the dot grid is deleted (a 4 percent dot pattern under bars competes with data-neutral and reads as graph paper, the opposite of a quiet room).
6. Sections 4 and 5 (animation, composition): superseded by design-brief motion tokens and layout. Delete "never use linear easing", "rank number in Accent Pink" (rank numbers are caption in text-tertiary) and "optional background visual at 15 percent".
7. Sections 6 and 7 (AI images, Gemini template PNG, rhythm mp4): delete; design-brief section 6 removed AI images.
8. channel-config.json `brand.colors`, `visuals.*` colours and `fontFamily` update to v7 and "Manrope, Inter, sans-serif"; design-system.json `tokens.colors`, `typography.fontFamily`, `effects.dotGridOpacity` (0), `filmGrainOpacity` (0.035), `atmospheres` gains `ambient-light` and `vignette` (tier 1 only), sceneDefaults `dot-grid` becomes `grain`.
9. src/remotion/catalog/tokens.ts: COLOR and FONT update to v7; add `surface2` and an `ATMOSPHERE` constant (grain opacity and seed function, light anchor and drift, vignette stops, glow filter).

## 10. Sound direction

Ambient or lofi at 60 to 85 bpm: soft electric piano or pad, minor or modal, no vocals, no drum hits, light tape hiss acceptable, no sidechain pumping. At least 18 LU under the voice, never a stinger on a data beat. Sources: YouTube Audio Library (genre Ambient or Cinematic, mood Calm, filter "Attribution not required"; the standard licence permits monetized YouTube use with no credit, CC BY tracks need YouTube's credit line in the description); Pixabay Music (Pixabay Content License, no credit, keep the download receipt for Content ID disputes); Free Music Archive only CC0 or CC BY with credit.

## 11. Verified versus inferred

Verified this session (fetched or executed): every contrast ratio, OKLCH value, CIEDE2000 distance and simulated hex above (palette-check.mjs, run 2026-09-26); the Machado 2009 severity-1.0 matrices (colour-science dataset); DaltonLens guidance to apply them in linear RGB; Datawrapper's rules on gray, single highlight and "vary by lightness"; Uxcel's summary of Material dark-theme numbers; Remotion noise2D determinism and the @remotion/google-fonts import pattern; Manrope in @remotion/google-fonts at weights 200 to 800, OFL-1.1; YouTube Audio Library licence terms; feTurbulence grain guidance (fractalNoise, baseFrequency 0.6 to 0.9, opacity under 0.1); the v6 brand files, tokens.ts and showcase stills.

Inferred: the visual descriptions of Lofi Girl, synthwave, melodysheep and Kurzgesagt come from secondary articles, not frame analysis; the Material m2 page did not render for fetching, so its numbers are not used as tokens; the atmosphere values (grain 0.035, light 6 percent, vignette 0.18, drift periods 24 s and 31 s) are my calibration, to be tuned once in the showcase composition; my preview render (qlmanage, fallback fonts, no filter support) validated colour relationships only; Manrope's tabular figures were not checked (all numbers are set in Inter); the 18 LU music level is standard practice, not measured for this voice.

## 12. Sources

- Datawrapper, colours for data vis style guides: https://www.datawrapper.de/blog/colors-for-data-vis-style-guides
- Datawrapper, colour-blind friendly palettes (part 2): https://www.datawrapper.de/blog/colorblindness-part2
- Material Design dark theme (m2): https://m2.material.io/design/color/dark-theme.html
- Uxcel, 12 principles of dark mode design: https://uxcel.com/blog/12-principles-of-dark-mode-design-627
- Machado, Oliveira, Fernandes 2009 paper: https://www.inf.ufrgs.br/~oliveira/pubs_files/CVD_Simulation/Machado_Oliveira_Fernandes_CVD_Vis2009_final.pdf
- colour-science Machado matrices dataset: https://github.com/colour-science/colour/blob/develop/colour/blindness/datasets/machado2010.py
- DaltonLens, understanding CVD simulation: https://daltonlens.org/understanding-cvd-simulation/
- Remotion noise2D: https://www.remotion.dev/docs/noise/noise-2d
- Remotion loadFont: https://www.remotion.dev/docs/google-fonts/load-font
- Manrope repository (OFL-1.1): https://github.com/googlefonts/manrope
- Inter font family (OpenType features incl. tnum): https://rsms.me/inter/
- Codrops, SVG feTurbulence texture: https://tympanus.net/codrops/2019/02/19/svg-filter-effects-creating-texture-with-feturbulence/
- CodeFronts, feTurbulence parameter breakdown: https://codefronts.com/design-styles/css-grain-texture/svg-feturbulence-noise-parameter-breakdown/
- CSS-Tricks, grainy gradients: https://css-tricks.com/grainy-gradients/
- YouTube Audio Library help: https://support.google.com/youtube/answer/3376882
- vidIQ, YouTube Audio Library attribution rules 2026: https://vidiq.com/blog/post/royalty-free-music-youtube-audio-library/
- Lofi Girl analysis (secondary): https://www.alibaba.com/product-insights/why-is-lofi-girl-such-a-popular-study-stream-and-what-makes-it-calming.html
- Synthwave style (secondary): https://styleshift.design/styles/synthwave
- melodysheep (secondary): https://en.wikipedia.org/wiki/John_D._Boswell
- Kurzgesagt colour tutorial (not watched, for follow-up): https://www.youtube.com/watch?v=_VrNiya8kLg
- Manrope and Montserrat comparisons (secondary): https://bonfx.com/what-fonts-go-with-manrope/
