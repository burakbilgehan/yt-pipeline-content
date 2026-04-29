# Visual Rules (VB-1 through VB-7) — The World With Numbers DS

Non-negotiable visual behaviours. Any violation is a critic FAIL.

## VB-1: Screen Utilization — Fill the Frame

Content must occupy **≥ 85%** of the frame area — target 90%.

| Rule | Min | Target |
|:-----|:----|:-------|
| Primary content area | 85% | 90% |
| Max horizontal padding | 3% (58px at 1920w) | 2% (38px) |
| Max vertical padding | 3% (32px at 1080h) | 2% |
| **Exception** | ClosingScene may leave bottom-right 30% clear for YouTube overlays |

## VB-2: Value-to-Color Mapping — Chromatic Scale, Never Binary

When values sit on a spectrum (low→high, good→bad), colors **interpolate proportionally**. A value at 30% of range gets a color 30% between `--negative` and `--positive`. Binary coloring (just red/green) lies about magnitude.

**Implementation:** Normalize each value to 0–1 (dataset min→max), then `interpolateColors()` between palette endpoints. Midpoint of diverging scales reads near-neutral (desaturated).

## VB-3: Proportional Bar Sizing — Bars Must Tell the Truth

Bars, progress indicators, and comparative fills must truthfully represent the underlying ratio.

- **Consistent baseline:** All bars share the same scale. Largest value = max width. Others proportional.
- **No fake normalization:** If values are 100 and 10, the visual must show 10:1. Don't each-to-its-own-max.
- **Animations target truth:** Spring/interpolate must converge to the mathematically correct final width, not an aesthetic approximation.
- **Bar corner-radius:** `0` — squared. Rounded bars are banned.

## VB-4: Typography Hierarchy — Unambiguous Reading Order

Every frame must have one focal element. Font sizes establish hierarchy. Hard floor: **20px**. See `typography.md` for the full scale. If text can't fit at 20px, the layout is wrong.

## VB-5: Data-Ink Ratio — Maximize Signal, Minimize Decoration

Every visual element must carry information. Decoration competes with data.

- **No empty bars.** Every bar must carry data. No decorative bars behind labels.
- **Gridlines ≤ 10% opacity** (`rgba(240,237,232,0.08)`).
- **Direct labelling.** Label data points directly. Legends only when direct labelling is impossible.
- **Source attribution.** Always present. Bottom-right, 22px Inter, `var(--text-muted)`.

## VB-6: Animation Timing Budget — Entrance Done in First 30%

Entrance animations must complete within: `min(scene_duration × 0.30, 8s)`

| Parameter | Value |
|:----------|:------|
| **Entrance budget** | `min(duration × 0.30, 8s)` |
| **Stagger ceiling** | Total stagger ≤ 2s always. Reduce per-item delay if N > 15 |
| **List stagger** | 10 frames between items |
| **Chart bar stagger** | 6 frames between bars |
| **Line reveal** | 60–90 frames, strokeDashoffset, L→R |
| **Counter** | 30–45 frames, `spring(100, 20)` |
| **Scene transition** | 8-frame crossfade |
| **Easing** | `cubic-bezier(0.33, 1, 0.68, 1)` |
| **Linear easing** | **Banned.** |

## VB-7: Template Genericity — Templates Visualize Structures, Not Topics

Templates are content-agnostic. They visualize data shapes — rankings, duels, timelines — not specific subjects.

- **Structural names:** `RankingResortScene` ✓ / `GDPRankingScene` ✗
- **Suffix:** `*Scene` for L3, no suffix for L2
- **No hardcoded content:** Default props use generic placeholders ("Item A", "$100") — never real-world branded names
- **Composable over monolithic:** Prefer composing L2+L3 layers over a single 500-line template

## Bauhaus Geometry Primitives

Structural layout elements — not decoration. All live in `src/remotion/design-system/primitives/`, generic, prop-driven, 8pt grid multiples.

| Primitive | Role |
|:----------|:-----|
| `EdgeStrip` | Full-thickness accent bar pinned to a frame edge (top/right/bottom/left). |
| `LogoBlock` | Flat-fill square mark + uppercase wordmark. Follows brand-identity §6 logo direction (no gradient/glow). |
| `AccentRule` | 120×3 anchor bar below titles. |
| `SectionHeader` | Eyebrow + title + optional right meta + 2px bottom rule. Standard top strip for bento scenes. |
| `KpiCell` | Bento KPI cell: micro-eyebrow + large number + descriptor. Tabular-nums applied automatically. |

**Hard rules:**
- Border radius 0 (use existing `--corner-radius` token).
- No gradients, no glow, no drop-shadow.
- Colors always from tokens (`ACCENT_PINK`, `ACCENT_BLUE`, `TEXT`, `TEXT_FAINT`, `SURFACE_BORDER_STRONG`, etc.). Hardcoded hex forbidden.
- Dimensions must be multiples of the 8pt grid (8/16/24/32/40/56/64/...).
- Structural separation: 2px = meaningful boundary, 1px = secondary divider, nothing thicker.

## Effect Tokens (CSS variables)

| Token | Value | Notes |
|:------|:------|:------|
| `--dot-grid-opacity` | `0.04` | Background dot pattern opacity (reduced from 0.10) |
| `--dot-grid-spacing` | `28px` | Dot grid spacing |
| `--corner-radius` | `0px` | Bars ALWAYS squared |
| `--padding` | `40px` | Base padding |
| `--screen-utilization-min` | `0.85` | VB-1 minimum |
| `--screen-utilization-target` | `0.90` | VB-1 target |
| `--spring-stiffness` | `100` | Spring animation stiffness |
| `--spring-damping` | `20` | Spring animation damping |
| `--stagger-list` | `10` | Frames between list items |
| `--stagger-chart` | `6` | Frames between chart bars |
| `--ease-out` | `cubic-bezier(0.33, 1, 0.68, 1)` | Default easing curve |
