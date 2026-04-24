# Layout Contracts (LC-1 through LC-6) — The World With Numbers DS

Where things go — always. Every template must honour these or explicitly document an exception.

## LC-1: Title Anchor — Default Bottom-Left

Default position for titles is **bottom-left**. Strong recommendation, not absolute rule — deviate if the scene's data layout requires it, but document why.

- Eyebrow: 11px, pink, uppercase — 4px above title
- Title: Montserrat 52–64px (by length)
- Max width: 66% of frame
- BigStatScene may move title to top-left (see LC-3)

## LC-2: Citation Anchor — Bottom-Right (Mandatory)

Citations **always** appear bottom-right on every data scene.

- Position: 2% from bottom, 3% from right
- Font: 22px Inter, `var(--text-muted)`
- Prefix "Source:" in mono, same size, 8px right-margin
- Max 2 lines. Abbreviate if longer: "IMF WEO, Oct 2024"
- No URL underlines — print-style

## LC-3: Hero Number — Center, Never Shares Focus

The hero number (160px Montserrat) **centers both horizontally and vertically**.

- Descriptor sits below with 32px gap
- Never pair two hero numbers in same frame — use split-scene instead
- Eyebrow moves to top-left when hero is present (overrides LC-1)

## LC-4: Chart Canvas — 3/4 Frame, Right-Dominant

Chart scenes give **~75% of frame to the chart canvas**.

- Chart canvas: 72% wide × 86% tall, right-aligned with 2% gutter
- Title column: 24% wide, left side, vertically centered on chart
- Citation per LC-2
- Direct data labels over legends (VB-5)

## LC-5: Duel Split — 50/50 Vertical, Value-Dominant

Two-value comparisons split frame down the middle.

- Each half: label (top), big number (center), descriptor (below)
- 2% center gutter — no dividing line
- Left = pink data, Right = blue data
- Proportional bar (VB-3) spans full width at base
- Delta chip in center gutter if difference matters

## LC-6: Ranked List — Left Column, Bars Extend Right

- Rank number: 11px mono, muted, 44px gutter
- Item label: 22–28px Inter medium
- Value: tabular Montserrat, right-aligned at bar end
- Stagger entrance: 10f between items (VB-6)
- No stripes, no alternating-row backgrounds (VB-5)

## Spacing Scale — 8-Point Grid

All spacing is a multiple of 8px. Non-negotiable.

| Token | Value | Use |
|:------|:------|:----|
| `--s-1` | 8px | Icon-to-text, tight inline gaps |
| `--s-2` | 16px | Stacked metadata, list item inner padding |
| `--s-3` | 24px | Section internal padding |
| `--s-4` | 32px | Between related blocks |
| `--s-6` | 48px | Major vertical rhythm |
| `--s-8` | 64px | Section separators |
| `--s-12` | 96px | Hero breathing room |

## Frame-Level Geometry (1920×1080)

| Property | Value |
|:---------|:------|
| Outer frame padding | 58px horizontal / 32px vertical (min) |
| Primary content bounds | 1804×1016 (≥ 88% utilization) |
| Safe zone (critical content) | 10% inset on all sides |
| End-screen reserved area | Bottom-right 560×320px (closing scenes only) |
