# "The World With Numbers" — Visual Brand Guide (v6.0)

This is the **visual ruleset** for all video rendering. Every agent (storyboard, video-production, collector) MUST read and follow this guide. No exceptions.

> **Color Source of Truth:** `channel-assets/design-system.json`
> All color values below are derived from that file. Do NOT hardcode hex values in code — import from `src/remotion/palette.ts` (auto-generated via `npm run sync-palette`).

## 1. Color Palette

| Role | Name | Value | Usage |
|:-----|:-----|:------|:------|
| **Background** | Deep Base | `#2A2A32` | Master video background |
| **Data Set A** | Accent Pink | `#E88CA5` | Primary data series, highlights, accented elements |
| **Data Set B** | Accent Blue | `#7BA7C9` | Secondary data series, stable/comparative data |
| **Text** | Warm Cream | `#F0EDE8` | All readable text — titles, labels, callouts |
| **Axis/Grid** | — | `rgba(240,237,232,0.35)` | Axis labels, tick marks, structural elements (not a brand color) |
| **Positive** | Green | `#5BBF8C` | Positive change, growth indicators |
| **Negative** | Red | `#E06070` | Negative change, decline indicators |
| **Surface** | — | `#2E2E38` | Card/panel backgrounds |
| **Border** | — | `rgba(240,237,232,0.12)` | Subtle borders and dividers |

### Color Rules
- **Max 2 data colors per chart** — Pink + Blue. Never add a third vivid color.
- **Sage** (`#8A9A7A`) removed from v6 palette. Grid/axis elements use `rgba(240,237,232,0.35)` (AXIS token). Grid lines use `rgba(240,237,232,0.08)` — max 10% opacity (VB-5).
- **No gradient text.** Ever.
- **No pure white (`#FFF`).** Use Warm Cream for all text.
- Background is always solid `#2A2A32` — no gradient backgrounds unless explicitly specified in storyboard.
- **Never hardcode hex values in source code.** Import from `src/remotion/palette.ts`.

## 2. Typography

| Role | Font | Weight | Notes |
|:-----|:-----|:-------|:------|
| **Headings / Hook Titles** | `Montserrat` | 700–800 (Bold/ExtraBold) | Impact titles, section headers |
| **Data Labels & Numbers** | `Montserrat` | 600–700 | `fontVariantNumeric: "tabular-nums lining-nums"` — tabular nums MANDATORY so digits don't shift width |
| **Body Text** | `Montserrat` | 400 | Subtitles, explanations, small labels |

### Typography Rules
- **Heading sizes:** Hook/hero titles 64–80px, section titles 36–48px, labels 16–22px
- **Line height:** 1.2 for headings, 1.5 for body
- **Letter spacing:** -0.02em for headings, normal for body
- **All text color is Warm Cream** (`#F0EDE8`) unless it's a data value using Pink or Blue

## 3. Visual Texture (CSS/SVG Generated — No External Files)

These textures are generated in code. No external PNG files needed.

### Film Grain (Every Scene)
Apply as the **topmost layer** on every scene, 3% opacity:
```
filter: url(#noiseFilter);
opacity: 0.03;
mix-blend-mode: overlay;
```
Implementation: SVG `<feTurbulence>` filter — see Remotion shared components.

### Dot Grid (Data Visualization Scenes)
Background dot pattern for data-heavy scenes:
- 28px spacing, `rgba(240,237,232,0.04)` — 4% opacity (VB-5: data-ink ratio)
- Creates subtle "graph paper" feel without being distracting

## 4. Animation Principles

All motion must feel **smooth, weighted, and deliberate**. Never mechanical. Never linear.

### Easing
- **Default motion:** `Easing.bezier(0.33, 1, 0.68, 1)` — the "muted easing" curve
- **Never use linear easing** for any visible element
- **Fallback for complex motion:** `Easing.out(Easing.exp)`

### Springs
- **Bar charts / counters:** `spring({ stiffness: 100, damping: 20 })` — slight bounce on arrival
- **Cards / panels:** `spring({ stiffness: 80, damping: 18 })` — softer entrance

### Stagger
- **List/leaderboard items:** 10-frame stagger between each item
- **Chart bars:** 6-frame stagger
- **No simultaneous entrance** of multiple data elements — always stagger

### Timing
- **Line charts:** strokeDashoffset reveal, left-to-right, 60–90 frames
- **Number counters:** interpolate from 0 to value over 30–45 frames
- **Scene transitions:** 8-frame crossfade default

## 5. Composition Guidelines

### Layout Principles
- **Left-aligned data, right-aligned visuals** when combining text + chart
- **Generous padding:** minimum 60px from screen edges
- **Visual hierarchy:** One focal element per scene — never compete for attention
- **Data density:** Max 6–8 items visible in any leaderboard/list at once

### Scene Category Defaults

**Hero / Hook:**
- Title centered or left-aligned, large (64–80px Montserrat Bold)
- Subtitle below in Montserrat, muted
- Clean background — no charts, no clutter
- Single accent element (underline, small stat) in Accent Pink

**Data Visualization (Charts):**
- Chart occupies 60–70% of frame
- Title top-left, source bottom-right (small, muted)
- Dot grid background active
- Y-axis labels in Montserrat, `fontVariantNumeric: "tabular-nums lining-nums"`

**Comparison / Duel:**
- Side-by-side layout, equal weight
- Thin vertical divider (`rgba(240,237,232,0.35)`, 1px)
- Entity names 24px Montserrat, key stat 48px Montserrat
- Flag/icon max 48px — don't overshadow the data

**Leaderboard / List:**
- Vertical stack, full-width items
- Rank number (Montserrat, Accent Pink), name (Montserrat), value (Montserrat, right-aligned, tabular-nums)
- Max 6–8 visible items, staggered entrance
- Horizontal bars behind values showing relative scale

**Narrative / Explanation:**
- Large key stat or quote centered
- Supporting text below in Montserrat
- Optional subtle background visual at 15% opacity

**CTA / Closing:**
- Channel name + subscribe prompt
- Minimal — accent underline only
- No busy backgrounds

## 6. AI Image Generation Rules

When generating images via Gemini or DALL-E:

### Always
- Dark background, close to `#2A2A32`
- Cinematic lighting, single light source preferred
- Minimal composition — one subject, clean negative space
- Muted, desaturated color grading matching the palette
- High detail, photorealistic style

### Never
- No text in generated images (Remotion adds text)
- No faces or identifiable people
- No busy/cluttered compositions
- No bright/saturated colors that break the muted palette
- No stock photo clichés (handshake, lightbulb, etc.)

### Style Prompt Template
```
[subject description], dark moody background, cinematic lighting, 
muted color palette, minimal composition, high detail, 
photorealistic, editorial documentary style, no text, no people
```

## 7. Visual Reference

See `channel-assets/Gemini_Generated_Image_go4311go4311go43.png` for the template screen layouts.
See `channel-assets/Detaylı_Asset_ve_Animasyon_Talebi.mp4` for animation rhythm reference.

These files define the target aesthetic. All renders should match this visual quality and mood.
