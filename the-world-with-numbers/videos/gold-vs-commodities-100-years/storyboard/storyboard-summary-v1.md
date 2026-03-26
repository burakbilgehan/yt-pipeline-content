# Storyboard Summary: Gold vs Commodities — 100 Years of Prices in Gold Terms
> version: 1
> based_on: script-v2
> date: 2026-03-15

## Visual Concept: "Horse Race"

This video uses a **single continuous animated line chart** as the primary visual. Nine asset/gold ratio lines "race" forward through time (1925→2025). The chart is rendered by a custom Remotion component (`HorseRaceChart`).

Unlike traditional storyboards with distinct scene cuts, this video flows as one continuous animation with:
- **Zoom in/out** — tight shots during dramatic moments, wide shots for big-picture
- **Speed changes** — timeline slows at key historical events, speeds up during calm periods
- **Asset visibility** — lines that become irrelevant (ratio too small) drift off the bottom of the frame
- **Event markers** — text flashes for major events (Nixon Shock, Bretton Woods, etc.)
- **Annotations** — data callouts on specific assets at key moments

## Scene Breakdown (8 scenes, 3:50 total)

| # | Scene | Time | Duration | Visual Type | Description |
|---|-------|------|----------|-------------|-------------|
| 1 | Hook | 0:00–0:12 | 12s | Text overlay | "26,000% → 132%" dramatic text reveal |
| 2 | Setup | 0:12–0:30 | 18s | Composite | Formula card + chart starting gate |
| 3 | Gold Standard 1925–1971 | 0:30–1:20 | 50s | Horse race chart | Lines race through 46 years. Nikkei pulls ahead. |
| 4 | Nixon Shock 1971–1980 | 1:20–2:10 | 50s | Horse race chart | **THE MONEY SHOT.** All lines nosedive. 1:1 moment. |
| 5 | Great Reversal 1980–2000 | 2:10–2:50 | 40s | Horse race chart | Lines explode upward. Nikkei peak 96.85 then crash. |
| 6 | Gold's Revenge 2000–2025 | 2:50–3:25 | 35s | Horse race chart | All lines fall. Platinum ATL. Final zoom-out. |
| 7 | Scoreboard | 3:25–3:45 | 20s | Comparison chart | Ranked bar chart, 9 assets, green/red |
| 8 | CTA & Closing | 3:45–3:50 | 5s | Text overlay | Clean close, subscribe |

## Key Visual Moments (in order of impact)

1. **Scene 4 — Jan 22, 1980: "1:1"** — Maximum zoom, slowest speed. All lines converge at the bottom. "1 oz Gold = Entire Dow" flash. This is the emotional peak of the video.

2. **Scene 5 — Dec 1989: Nikkei peak at 96.85** — The highest any ratio ever reached. Line shoots off the top of the frame. Crown icon. Then it crashes while everything else keeps rising.

3. **Scene 1 — "26,000% → 132%"** — The opening gut punch. Text-only, maximum impact.

4. **Scene 4 — "NIXON SHOCK"** — Screen shake effect. All lines begin synchronized freefall.

5. **Scene 6 — Oil near-zero (April 2020)** — Zoom in on oil line touching near-zero during COVID.

6. **Scene 6 — Final zoom-out** — First time viewer sees the entire 100-year chart. "Wow" moment.

## Camera & Speed Map

```
Year:   1925  1934  1944  1960  1971  1975  1980  1985  1989  1995  1999  2008  2020  2025
Zoom:   1.2x  1.3x  1.0x  0.7x  0.8x  1.2x  1.8x  0.5x  0.3x  0.5x  0.6x  0.8x  1.2x  0.5x
Speed:  1.0x  0.3x  0.7x  1.0x  0.3x  0.5x  0.1x  1.0x  0.3x  0.8x  0.3x  0.4x  0.2x  0.3x

█ = slow (dramatic)  ░ = fast (calm)  ▓ = moderate
```

## Asset Colors

| Asset | Color | Hex | Type |
|-------|-------|-----|------|
| Silver | Silver | `#C0C0C0` | Commodity |
| Platinum | Platinum grey | `#E5E4E2` | Commodity |
| Oil (WTI) | Dark brown | `#4A2F1B` | Commodity |
| Copper | Copper | `#B87333` | Commodity |
| S&P 500 | Pink/coral | `#FF6584` | Index |
| Dow Jones | Purple (brand) | `#6C63FF` | Index |
| FTSE 100 | Green | `#00A86B` | Index |
| Nikkei 225 | Red | `#FF4444` | Index |
| DAX | Gold | `#FFD700` | Index |

## Asset Data Availability (when lines appear)

| Asset | First Data | Appears in Scene |
|-------|-----------|-----------------|
| Gold (reference) | 1925-03 | Always (baseline) |
| Silver | 1925-03 | Scene 3 (start) |
| S&P 500 | 1925-01 | Scene 3 (start) |
| Dow Jones | 1925-01 | Scene 3 (start) |
| Nikkei 225 | 1925-03 | Scene 3 (start) |
| Copper | 1948-03 | Scene 3 (mid) |
| DAX | 1959-12 | Scene 3 (late) |
| Platinum | 1968-03 | Scene 3 (late) |
| Oil (WTI) | 1968-01 | Scene 3 (late) |
| FTSE 100 | 1985-12 | Scene 5 |

## Image Generation Strategy

This video is **100% programmatic** — no stock footage, no AI-generated images needed.

| Visual Type | Scenes | Method |
|-------------|--------|--------|
| Horse race chart | 3, 4, 5, 6 | Custom Remotion `HorseRaceChart` component |
| Text overlay | 1, 8 | Remotion text animation component |
| Formula card | 2 | Remotion composite component |
| Scoreboard | 7 | Existing `ComparisonTable` chart component |

## Production Requirements

### Custom Remotion Components Needed
1. **`HorseRaceChart`** — The core component. Multi-series animated line chart with:
   - Time-based progression (lines draw as timeline advances)
   - Dynamic Y-axis scaling (auto-adjusts as ratios change)
   - Camera zoom/pan interpolation
   - Timeline speed variation
   - Asset visibility toggling (drop off / bring back)
   - Event marker flashes (crisis, policy, milestone styles)
   - Asset labels that follow their lines
   - Smooth SVG path rendering with `@remotion/paths`

2. **`HookReveal`** — "26,000% → 132%" text animation (Scene 1)

3. **`FormulaCard`** — Animated formula explanation (Scene 2)

### Dependencies to Install
- `@remotion/paths` — SVG path animation (evolvePath, getLength, etc.)

### Data Pipeline
- Ratio CSV files from `research/data/ratios/` → loaded as props into HorseRaceChart
- Summary statistics from `research/data/summary.json` → used for annotations and scoreboard
