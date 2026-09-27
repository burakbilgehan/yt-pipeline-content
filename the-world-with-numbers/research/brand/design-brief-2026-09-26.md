# Design Brief: The World With Numbers, scene catalog v1

Date: 2026-09-26. Scope: 1920x1080, 30 fps, Remotion. Free assets only. This brief is the contract the storyboard AI picks from; it does not add scene types, it fills data.

Measured baseline (work/baseline-legacy, 55 sampled frames): 13 of 55 are the bare background hash (identical empty frames), several more are axes with no data yet; the line charts use smoothed curves that invent values between data points; annotations are stacked rounded "sticker" cards floating over the plot.

## 1. Design principles

1. The stage is never empty: every scene inherits a header band and footer band from the previous scene, so frame 0 of any scene already has content. Why: the 4% median content and 20 to 30 s empty title cards are the single biggest quality gap.
2. One highlight, everything else gray: pink marks the one thing the narration is about; blue is the single contrast series; all other data is neutral gray. Why: Datawrapper's rule that readers look first at the most saturated color, then the grays; if everything is colored nothing is emphasized.
3. Something changes every 3 to 5 seconds, and the change carries information (a value lands, a bar sorts, a label appears), never decoration. Why: retention editing sources converge on a visual reset every few seconds; data beats are the cheapest honest reset.
4. Build from what is on screen: a new scene enters by transforming or displacing an existing element, not by fading in from black. Why: Heer and Robertson show animated, staged transitions improve object tracking; a hard reset makes the viewer re-parse the whole frame.
5. Encode honestly or do not encode: bar length, area, and slope are always proportional to the data; if the data cannot be shown proportionally at 1080p, change scene type, never the scale. Why: truncated or clamped bars are the one mistake viewers screenshot and mock.
6. Numbers are the hero and are always tabular: every number is set in Inter with tabular figures, right-aligned, so tickers do not jitter and columns line up. Why: Montserrat from Google Fonts ships without tnum.
7. Five type sizes, three text levels, two accents; nothing else. Why: inconsistency between videos was measured; a closed token set is the only fix that survives an AI author.
8. Source line on every data scene, in the footer, always in the same place. Why: FT, Economist, and Our World in Data all treat the source as part of the chart, and it is the cheapest credibility signal available.

## 2. Tokens

### Type scale (px at 1080p)

| Role | Font | Size | Weight | Use |
|---|---|---|---|---|
| display | Inter, tnum | 168 | 700 | the one hero number of a big-number scene |
| h1 | Montserrat | 88 | 800 | chapter titles, statements |
| h2 | Montserrat | 52 | 700 | scene title in header band |
| body | Inter | 34 | 500 | labels, values on charts, timeline text |
| caption | Inter | 24 | 400 | axis ticks, source line, footnotes; hard floor, nothing smaller |

Line height 1.1 for display and h1, 1.25 for h2, 1.35 for body and caption. Letter spacing -0.02em for display and h1. Load with @remotion/google-fonts with explicit weights and subsets (required from v5.0). Numbers anywhere use `fontVariantNumeric: 'tabular-nums'`.

### Color roles

| Role | Hex | Rule |
|---|---|---|
| bg | #2A2A32 | the only page background; no gradients, no vignettes |
| surface | #34343E | header band, footer band, table rows, annotation plates |
| grid | #3E3E49 | gridlines, axis lines; zero line and index=100 line use text-tertiary instead |
| text-primary | #F0EDE8 | titles, values that matter |
| text-secondary | #B9B6B2 | labels, secondary values |
| text-tertiary | #7F7D82 | ticks, source, inactive items |
| highlight | #E88CA5 | the story item; max one item or one series per scene |
| contrast | #7BA7C9 | the second series or the comparison item, only when narration names both |
| data-neutral | #6C6C78 | every other bar, line, country, slice |

No positive/negative pair. Direction is carried by the highlight plus an arrow glyph and the sign in the label; a red/green pair would add two hues and break the one-highlight rule. Revisit only if a whole video is built on gains versus losses (an inference, not a tested claim). Map land uses data-neutral at 60% opacity, borders in grid, focus country in highlight, ocean is bg.

### Spacing and safe zones

8 px base grid. Outer margins 96 px left/right and 72 px top/bottom, which sits inside the EBU R95 title-safe rectangle for 1080p (96 px sides, 54 px top/bottom). Header band: y 72 to 200 (kicker in caption, title in h2). Content area: y 232 to 928, x 96 to 1824. Footer band: y 960 to 1008 (source left in caption, chapter marker right). Keep the bottom-right 400x100 free of essential data because the YouTube player overlays controls there on hover (inference from player UI, not a published spec). Gutter between columns 48 px, between rows 24 px.

### Motion tokens (frames at 30 fps)

| Token | Curve (cubic-bezier) | Use |
|---|---|---|
| ease-enter | 0.05, 0.7, 0.1, 1 | anything appearing or growing (Material 3 emphasized decelerate) |
| ease-exit | 0.3, 0, 0.8, 0.15 | anything leaving (Material 3 emphasized accelerate) |
| ease-move | 0.2, 0, 0, 1 | re-sorting, morphing, camera moves (Material 3 standard) |
| linear | 0, 0, 1, 1 | line drawing along time, progress bars |

Durations: enter 12 f; exit 8 f; move/morph 18 f; number count-up 30 f; bar grow 20 f; line draw 60 to 120 f scaled to the narration span; map zoom 36 f; scene cross-transition 10 f with a 6 f overlap so the screen is never empty. Stagger 3 f per item; when items exceed 8, compress so total stagger never exceeds 24 f (stagger the first 5, land the rest together). Springs only for count-up overshoot on the display number (damping 200, no visible bounce); everything else uses the beziers so timing is predictable per scene budget.

## 3. Scene catalog

Common to every type: props `{ kicker?: string (<=40 chars), title: string (<=60 chars), source: string (<=90 chars), chapter: { index: number, total: number } }`. Every type renders inside the persistent stage (bg, header band, footer band). "Beats" are keyed to narration timestamps supplied by the scene-timing skill; a scene has 1 to 6 beats, each beat advances one visible state.

### chapter-card
Beat: section change, 2 to 3 s, never longer than 4 s.
Layout: header band collapses; a thin highlight rule sweeps the content area at y 540 over 18 f; chapter number in caption above, h1 title below the rule, both left-aligned at x 96. The footer chapter marker updates in the same frame.
Schema: `{ number: number, title: string (<=40 chars) }`.
Enter: previous scene content exits with ease-exit while the rule sweeps in; the next scene's header title is formed from this h1 shrinking into the header band (ease-move, 18 f), so the title is never typed twice.
Adaptation: none; if title exceeds 40 chars it wraps to two lines at h1 and the rule moves up 60 px.

### statement
Beat: a claim, a quote, a definition, a question.
Layout: text block max 1200 px wide, left-aligned at x 96, vertically centered in the content area; h1 for the line, caption for attribution. Highlight is applied to the key phrase via `emphasis` spans (max 1 span).
Schema: `{ text: string (<=120 chars), emphasis?: string (substring of text), attribution?: string (<=60) }`.
Enter: words reveal in groups of 3 with 3 f stagger (word-level, never character-level); emphasis span gets highlight color 12 f after the sentence lands. Beats: one optional second line appears below.
Adaptation: >80 chars drops to h2; >120 chars is rejected by the schema.

### big-number
Beat: one figure that the narration stops on.
Layout: two-column. Left column (60%) has the display number with unit prefix/suffix in h2 and a one-line context in body underneath; right column (40%) holds an optional reference figure in h2 with caption label, drawn as a small proportional bar pair under both numbers so the ratio is visible, not just stated.
Schema: `{ value: number, unit?: string, prefix?: string, decimals: 0..2, context: string (<=70), reference?: { label: string (<=30), value: number } }`.
Enter: number counts from 0 or from the previous scene's related value over 30 f with ease-enter; the proportional bars grow 20 f after the number lands; context line fades in last. Beats: reference appears on cue.
Adaptation: numbers over 7 significant digits are auto-abbreviated (1.2 billion) and the full value shown in caption; numbers below 1 show up to 2 decimals.

### compare-values
Beat: 2 to 4 items compared by magnitude, stated honestly.
Layout: horizontal bars stacked vertically, label left (body), value right-aligned at the bar end (body, tnum), highlight on the story item, others data-neutral. Bars start at x 480 and scale to the largest value at 1200 px length. When max/min ratio exceeds 40 the type switches to "scale mode": the largest item keeps 1200 px, small items render at their true pixel length (even 1 px) with the value label placed to the right of the axis origin, and a caption states the ratio ("480 times larger").
Schema: `{ items: [{ label: string (<=24), value: number, highlight?: boolean }] (2..4), unit?: string, format?: 'number' | 'percent' | 'currency' }`.
Enter: bars grow with ease-enter, 20 f, 3 f stagger; values count up in sync. Beats: items appear one at a time on cue, or the highlight moves from one item to another (color transition 12 f).
Adaptation: 2 items use 120 px bar height, 3 items 96 px, 4 items 80 px.

### ranked-bars
Beat: a ranking of 5 to 12 items, optionally re-ranked across time.
Layout: same grammar as compare-values but denser; rank number in caption left of the label; the top item is highlight only when the narration is about it, otherwise the named item is; everything else data-neutral. No axis; values are labeled directly.
Schema: `{ items: [{ label, value, flag?: ISO2, highlight?: boolean }] (5..12), unit?, sortDesc: true, snapshots?: [{ label: string, items: [...] }] (<=4) }`.
Enter: rows land with 3 f stagger (compressed rule); flags from flag-icons at 32x24. Beats: each snapshot re-sorts rows with ease-move 18 f and re-grows bars; the snapshot label sits in the header kicker. This replaces the bar-chart race: at most 4 discrete re-sorts, each held at least 3 s.
Adaptation: 5 to 7 items row 84 px; 8 to 10 row 64 px; 11 to 12 row 52 px with body labels dropping to caption. Beyond 12 the storyboard must split into two scenes.

### time-series
Beat: change over time, 1 to 4 series.
Layout: plot occupies the full content area minus a 200 px right margin for end labels; y axis on the left with 4 to 6 gridlines labeled in caption; x axis with tick marks and no gridlines; the series are straight segments between data points, never smoothed. End labels sit at the line end (label in body, value in body tnum). Highlight series is 4 px, contrast 3 px, neutral 2 px.
Schema: `{ series: [{ label (<=20), points: [{ x: number|string, y: number }] (2..200), role: 'highlight'|'contrast'|'neutral' }] (1..4), yMin?: number, yMax?: number, indexLine?: number, annotations?: [{ x, text (<=40) }] (<=3) }`.
Enter: axes appear with the header; lines draw left to right with linear timing over the narration span; end labels land when the draw ends. Beats: annotations appear as a thin vertical rule in text-tertiary plus a caption label anchored at the x position, not as floating cards; a second series can be added mid-scene; y domain may re-scale with ease-move when a new series exceeds it.
Adaptation: y axis may crop (does not need to start at zero) but then the footer gets the automatic note "axis does not start at 0"; an indexLine (100 or 0) is drawn in text-tertiary and heavier than gridlines; over 60 points, point markers are suppressed; 3 or 4 series force at most 1 highlight and 1 contrast.

### map-focus
Beat: where something is, a region, a route, or a choropleth of a few countries.
Layout: full-content-area map, equal-earth projection for world views, the same projection zoomed by fitExtent on the focus feature's bounding box with 120 px padding for country or region views. Land data-neutral at 60% opacity, borders grid color, ocean bg. Focus countries in highlight, comparison countries in contrast, label plates in surface with body text placed at the feature centroid or at a fixed anchor with a 1 px leader.
Schema: `{ focus: [ISO3166 numeric ids] (1..6), contrast?: [ids] (<=3), view: 'world'|'fit', labels?: [{ id, text (<=30), value?: string }] (<=6), route?: { from: [lon, lat], to: [lon, lat], via?: [[lon, lat]] (<=4) } }`.
Enter: if the previous scene was a map, the projection interpolates scale and translate over 36 f with ease-move (a camera move, not a cut); otherwise the world map fades in under the header in 12 f and the focus fill sweeps in. Beats: fill a country, add a label, draw a great-circle route (geoInterpolate, linear, 45 f), zoom to the next focus.
Adaptation: world view uses countries-110m; fit view uses countries-50m; more than 6 focus countries collapse to a single "region" fill with one label.

### timeline
Beat: 3 to 7 dated events in sequence.
Layout: horizontal rail at y 580 from x 96 to 1824, tick per event, year in caption above the tick, event text in body below, alternating above and below when spacing is tight. The current event is highlight; past events text-secondary; future events text-tertiary.
Schema: `{ events: [{ date: string (<=12), text: string (<=60), emphasis?: boolean }] (3..7), scale: 'even'|'proportional' }`.
Enter: the rail draws linearly 24 f; the first event lands. Beats: each cue advances the highlight along the rail; the rail dims behind. Proportional scale is used only when gaps matter to the story and the ratio of largest to smallest gap is under 20.
Adaptation: 3 to 4 events give 300 px per slot; 5 to 7 events alternate above and below and drop text to caption.

### breakdown
Beat: parts of a whole.
Layout: a single 100% stacked horizontal bar, 120 px tall, spanning the content width; segments labeled below with a leader for anything under 8% width; the story segment in highlight, an optional second in contrast, the rest in three steps of data-neutral (100%, 75%, 55% opacity). A waffle (10x10 squares) variant is used when the narration is about "x out of 100".
Schema: `{ parts: [{ label (<=24), value: number, role?: 'highlight'|'contrast' }] (2..8), total?: number, variant: 'bar'|'waffle' }`.
Enter: segments grow from the left in sequence (linear, 30 f total); labels land with stagger. Beats: a segment is highlighted on cue, or the bar splits into a second breakdown of one segment (the segment expands to full width with ease-move 18 f, then subdivides).
Adaptation: parts summing to less than the total render a "remainder" segment in grid color; more than 8 parts must be merged into "other" by the storyboard.

### matrix
Beat: two dimensions compared at once (countries by metrics), only when the narration actually reads across both. Justified only up to 5 rows by 4 columns; larger tables are not video content.
Layout: header row in caption uppercase, rows in surface alternating with bg, labels body left-aligned, values body tnum right-aligned; the cell the narration is about is highlight; a whole highlighted column gets the highlight in its header text only.
Schema: `{ columns: [string (<=16)] (2..4), rows: [{ label (<=20), values: [number|string] }] (2..5), highlightCell?: [row, col], highlightRow?: number }`.
Enter: rows slide in with 3 f stagger; values count up. Beats: highlight moves cell to cell or row to row.
Adaptation: 2 to 3 rows use 96 px rows; 4 to 5 use 80 px.

## 4. Continuity rules

The stage persists across every cut: background, header band, footer band. The header title changes by cross-fading text in 10 f; the kicker updates instantly. The chapter marker only changes in chapter-card. Within a chapter, a data scene does not repeat the source line animation; it swaps text in place.

Consecutive scenes of the same type morph rather than cut: compare-values to ranked-bars keeps the bar grammar and adds rows; time-series to time-series with the same x domain keeps the axes and only redraws series; map-focus to map-focus is a camera move. Different types transition by displacing: the outgoing content exits with ease-exit (8 f) while the incoming enters with ease-enter (12 f) starting 6 f before the exit ends. Fade to bg is never used except before the outro.

Element positions are fixed per type, so the viewer learns where values, labels, and sources live. Big-number's display value sits at the same origin as the h1 of statement, so a statement can turn into a big-number by the words shrinking and the number growing in place.

## 5. Honest-chart rules

Bars and stacked bars start at zero, always, no minimum bar width, no clamping; a 1-unit item next to a 6738-unit item is a 1 px sliver with its label outside, and the scene says the ratio in a caption. If that reads badly, the storyboard uses compare-values scale mode or a big-number with reference, never an equal-length bar. Log scales are forbidden on bars; permitted on time-series only with the axis labeled "log scale" in the header kicker. Lines are drawn through actual data points with straight segments; no curve smoothing. Cropped y axes on line charts trigger the automatic footer note. Ranked items are sorted by value; the one highlight is the item the narration names. No dual y axes. No pie or donut; part-to-whole is a stacked bar or a waffle. No 3D, no shadows, no gradients on data marks. Index charts draw the base line (100 or 0) heavier than gridlines. Values shown on screen must equal the values in the data file to the displayed precision (math-verification skill).

## 6. Delete from current practice

Empty title cards held 20 to 30 s; any frame where the content area is bare. Scenes that start from a blank plot and build over many seconds. Smoothed line charts. Stacked "sticker" annotation cards; annotations are rules plus captions anchored to data. Watermark year in the plot center. Minimum bar widths and equal-length bars. Per-video font sizes and colors; only tokens above. AI-generated images; the visual vocabulary is type, numbers, bars, lines, maps, flags, Lucide icons, nothing photographic. Character-level text reveals, text-rotate, container-text-flip, shiny or gradient text, sparkles, meteors, spotlight beams, 3D cards, marquee tickers (gallery gimmicks that read as web landing pages, not journalism). Rotating globes as decoration. Bar chart races with continuous re-sorting.

## 7. What to port from component galleries

Worth porting as pure frame functions: number count-up (reactbits Count Up, magicui Number Ticker; reimplement as `interpolate(frame)` with tnum, the originals depend on framer-motion and in-view hooks), blur-to-sharp entrance for text plates (already in the DS as blur-fade-in), word-group split text reveal (reactbits Split Text, at word level only), staggered list entrance (magicui Animated List, the mechanism for ranked-bars rows). Not worth porting: anything from Aceternity's 3D and glow set, morphing text, typing animation, and background effects. 21st.dev is a marketplace of React and Tailwind components; use it for reference only, never as a dependency.

## 8. Free resources

Maps: world-atlas 2.0.2 (ISC) via `https://cdn.jsdelivr.net/npm/world-atlas@2/countries-110m.json` and `countries-50m.json`, ids are ISO 3166-1 numeric; vendor the two files into the repo so renders are offline and deterministic. Natural Earth 4.1.0 underlying data is public domain (no attribution required, "Made with Natural Earth" is courteous). d3-geo (ISC) for geoEqualEarth, fitExtent, geoPath, geoInterpolate; topojson-client (ISC) for feature extraction; `@remotion/paths` interpolatePath for simple shape morphs. Flags: lipis/flag-icons (MIT), 4x3 SVGs keyed by ISO alpha-2. Icons: Lucide (ISC; Feather-derived glyphs MIT) as the single icon set, 24 grid, stroke 2, rendered at 48 or 64 px in text-secondary; Tabler (MIT) only as a fallback when Lucide lacks a glyph, since it shares the grid and stroke. Fonts: Montserrat and Inter under the SIL Open Font License via @remotion/google-fonts.

## 9. Verified versus inferred

Verified by fetching the source this session: Material 3 easing beziers and duration tokens; Datawrapper rules on gray and single-highlight emphasis and on zero baselines with dot-plot and line-chart alternatives; ONS guidance on zero baselines, log scales, gridline counts, and emphasized zero line; world-atlas license, version, CDN path, and id scheme; Natural Earth public-domain terms; Lucide ISC license; flag-icons MIT; Remotion Easing.bezier, @remotion/transitions presentation list, interpolatePath signature, loadFont v5 requirement for weights and subsets; EBU R95 title-safe numbers for 1080p; Montserrat on Google Fonts lacking tnum (GitHub issue); Heer and Robertson paper sections "Congruence" and "The Case for Staging" exist (PDF outline); the baseline frame audit above.

Inferred from search summaries or professional practice, not verified against primary sources: the specific visual habits of Wendover, RealLifeLore, Johnny Harris, PolyMatter (secondary articles only); the 3 to 5 s visual-change cadence (retention-editing blogs, no platform data); the YouTube player overlay area; the exact frame durations, which are my translation of 200 to 500 ms UI guidance to 30 fps video and should be tuned in the showcase composition; the claim that no positive/negative pair is needed for this channel.

## 10. Sources

- Datawrapper, Emphasize with color: https://www.datawrapper.de/blog/emphasize-with-color-in-data-visualizations
- Datawrapper, Colors for data vis style guides: https://www.datawrapper.de/blog/colors-for-data-vis-style-guides
- Datawrapper Academy, Why bar charts start at zero: https://www.datawrapper.de/academy/why-our-column-and-bar-charts-start-at-zero
- ONS service manual, Axes and gridlines: https://service-manual.ons.gov.uk/data-visualisation/guidance/axes-and-gridlines
- FT Visual Vocabulary: https://github.com/Financial-Times/chart-doctor/tree/main/visual-vocabulary
- Our World in Data, Grapher redesign: https://ourworldindata.org/redesigning-our-interactive-data-visualizations
- Heer and Robertson, Animated Transitions in Statistical Data Graphics (2007): https://idl.cs.washington.edu/files/2007-AnimatedTransitions-InfoVis.pdf
- Built In, Why some experts hate bar chart races: https://builtin.com/data-science/bar-chart-races
- Material 3 motion tokens (source): https://github.com/material-components/material-web/blob/main/tokens/versions/v0_192/_md-sys-motion.scss
- Remotion Easing: https://www.remotion.dev/docs/easing
- Remotion transitions presentations: https://www.remotion.dev/docs/transitions/presentations/
- Remotion interpolatePath: https://www.remotion.dev/docs/paths/interpolate-path
- Remotion loadFont: https://www.remotion.dev/docs/google-fonts/load-font
- world-atlas: https://github.com/topojson/world-atlas and https://cdn.jsdelivr.net/npm/world-atlas@2/package.json
- Natural Earth terms: https://www.naturalearthdata.com/about/terms-of-use/
- d3-geo: https://github.com/d3/d3-geo
- Remotion map example: https://github.com/Calm-Rock/map-trip-video
- Lucide license: https://lucide.dev/license
- flag-icons: https://github.com/lipis/flag-icons
- Icon set comparison: https://dev.to/svgicons/lucide-vs-tabler-vs-phosphor-which-free-icon-set-fits-your-ui-4ocl
- Montserrat tnum issue: https://github.com/google/fonts/issues/2628
- EBU R95 safe areas: https://tech.ebu.ch/publications/r095
- magicui Number Ticker: https://magicui.design/docs/components/number-ticker
- reactbits Count Up and Split Text: https://reactbits.dev/text-animations/count-up and https://reactbits.dev/text-animations/split-text
- 21st.dev: https://21st.dev/
- Vox style analysis (secondary): https://www.premiumbeat.com/blog/replicating-vox-motion-graphic/
- Wendover style (secondary): https://yespress.io/wendover-productions
- Retention pacing (secondary): https://editmyreels.com/how-to-edit-youtube-videos-for-higher-retention/
