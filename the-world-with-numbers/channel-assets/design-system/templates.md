# Scene Template Library — The World With Numbers DS

Select by **data shape**, not topic. See VB-7.

## Layer 2 — Primitives & Elements (8 templates)

Atom building blocks. Single-purpose. L3 scenes compose these — never used standalone.

<!-- L2 primitives table -->

| Template | Purpose | Key Spec |
|:---------|:--------|:---------|
| **AnimatedCounter** | 0 → target value, tabular | `spring(100,20)`, 30–45f, prefix/suffix support |
| **Callout** | Inline highlight block | Border-left 2px accent-pink + label + value |
| **CitationBlock** | Source attribution | Bottom-right, 22px Inter, text-muted. **Mandatory on every data scene** (VB-5) |
| **SectionTitle** | Eyebrow + heading | Mono eyebrow (pink, 11px, uppercase) + Montserrat H1. Default: bottom-left (LC-1) |
| **GridlineOverlay** | Chart gridline layer | 8% opacity horizontal lines. Auto-fits chart bounds |
| **AxisLabels** | Chart axis labels | 14px, axis-opacity, tabular-nums |
| **TrendArrow** | ↑/↓ change indicator | Positive/negative colored arrow + percentage |
| **DataPoint** | Direct label on chart | Attached to data point. Use instead of legend (VB-5) |

## Layer 3 — Scene Templates (18 templates)

Full scene compositions. Storyboard agent picks from this layer.

### Rankings & Lists

| Template | Purpose | Key Spec |
|:---------|:--------|:---------|
| **TopNListScene** | Ranked list 1→N | 10f stagger, bars normalized to max, 5–15 items |
| **RankingResortScene** | Animated rank change | Two columns (Year X → Year Y), spring resort, 90f |
| **HorseRaceChart** | Bar chart race | **Flagged** — pipeline test required before use, high complexity |
| **PodiumScene** | Top 3, podium style | Exactly 3 items. 1st=pink, 2nd=blue, 3rd=muted. Hero numbers |

### Comparisons & Duels

| Template | Purpose | Key Spec |
|:---------|:--------|:---------|
| **DuelSplitScene** | A vs B, 50/50 split | Full-screen vertical split. Label + big number each side. Proportional bar at base (VB-3) |
| **BeforeAfterCards** | Two states, side by side | Before/after cards + delta chip center. Historical comparisons |
| ~~ScaleComparison~~ | ~~Visual size comparison~~ | **Removed.** Use DuelSplitScene + proportional values instead |
| **GapHighlight** | Gap between two extremes | Two end values + annotated distance. **Rare** — use BigStatScene or DuelSplitScene first |

### Timelines & Trends

| Template | Purpose | Key Spec |
|:---------|:--------|:---------|
| **LineTrendScene** | Single series over time | strokeDashoffset L→R reveal (60–90f). Direct labels for min/max/current |
| **DualLineTrendScene** | Two series over time | Pink + blue lines reveal simultaneously. Intersections marked with DataPoint |
| **BaselineZoneDiagram** | Value vs reference band | Grid-opacity reference band + series line. Above/below deviations colored positive/negative |
| **TimelineMilestones** | Dated events, horizontal | Horizontal line with event markers. Year muted, title Montserrat. Max 5–8 events |

### Distributions & Stats

| Template | Purpose | Key Spec |
|:---------|:--------|:---------|
| **BigStatScene** | Single hero number | 160px Montserrat center frame + descriptor + source. Channel's highest-impact frame (LC-3) |
| **BarChartScene** | Categorical bars | 6f stagger. Direct value labels on bars. 3–15 categories |
| **DotPlotScene** | Dot distribution | **Flagged** — rarely fits channel data shape. Try WaffleChartScene first |
| **WaffleChartScene** | 10×10 square grid | Filled squares = percentage. Pink = share, muted = remainder |

### Narrative Scenes

| Template | Purpose | Key Spec |
|:---------|:--------|:---------|
| **OpeningScene** | Hook / title card | Channel eyebrow (mono pink) + video title (Montserrat H1). First 3–5s. VB-1 exception: centered, ~60% utilization |
| **ClosingScene** | Closing card | Summary + subscribe. Bottom-right 30% reserved for YouTube end-screen overlay. VB-1 exception |

## Layer 4 — Composed Sequences (Removed)

Layer 4 removed (Burak, 2026-04-17). Multi-scene stories use sequential L3 templates with 8f crossfade transitions. No mandatory sequences. If a stable recurring pattern emerges from real videos, it can be documented as L4 — but it must be proven, not invented.

## Data-Shape → Template Decision Tree

| Data Shape | Template |
|:-----------|:---------|
| Single number, high impact | BigStatScene |
| Ranked list 5–15 items | TopNListScene |
| Two values compared | DuelSplitScene |
| Value changed between 2 points | BeforeAfterCards |
| Rank changed over time | RankingResortScene |
| Single series over time | LineTrendScene |
| Two series over time | DualLineTrendScene |
| % of population / 100 | WaffleChartScene (or DotPlotScene) |
| Categorical comparison | BarChartScene |
| Top 3 highlight | PodiumScene |
| Dated events | TimelineMilestones |
| Value vs reference line | BaselineZoneDiagram |
