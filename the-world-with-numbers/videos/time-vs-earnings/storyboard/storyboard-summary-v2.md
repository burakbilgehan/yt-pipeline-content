# Storyboard Summary v2: Time vs Earnings

> Version: 2 (JSON format)
> Based on: script-v2.md (content v3 — Chirp 3 HD markup)
> Date: 2026-03-21
> Total scenes: 15
> Total duration: ~12:36 (756s)
> Resolution: 1920×1080, 30fps
> TTS: Google Chirp 3 HD / Achernar / markup mode

## Changes from v1

- ✅ Converted from Markdown to JSON two-tier format (skeleton + scene detail files)
- ✅ **DREAM extended to 7:30** — Split into Scene 006 (leaders + Japan) + Scene 007 (NL/NO/CA cluster)
- ✅ **GRIND starts at 7:30** — Was incorrectly 7:00 in v1
- ✅ **TRAP extended to 11:45** — Split into Scene 011 (Greece) + Scene 012 (Mexico + Israel)
- ✅ **GRIND dot color defined** — #D8A7B1 (Muted Pink)
- ✅ **Scene 1 "BM/hr" label fixed** — Now "Value per Hour" (concept not yet introduced)
- ✅ **TTS notes updated** — Google Chirp 3 HD / Achernar (was ElevenLabs/Maisie)

## Scene Map

| # | ID | Section | Time | Dur | Visual Type | Key Visual |
|---|-----|---------|------|-----|-------------|------------|
| 1 | scene-001 | Hook | 0:00-0:30 | 30s | data-chart | SalaryShuffleScene — numbers re-sort |
| 2 | scene-002 | The Salary Illusion | 0:30-2:15 | 105s | composite | $3K split screen + PPP bar chart |
| 3 | scene-003 | The Big Mac Lens | 2:15-3:20 | 65s | composite | Big Mac + radial prices → bar chart |
| 4 | scene-004 | The Big Mac Lens | 3:20-4:30 | 70s | data-chart | RankingResortScene — CH drops, JP rises |
| 5 | scene-005 | Adding Time | 4:30-5:45 | 75s | data-chart | QuadrantScatter matrix materializes |
| 6 | scene-006 | The Dream Quadrant | 5:45-6:30 | 45s | data-chart | DREAM dots + Japan spotlight card |
| 7 | scene-007 | The Dream Quadrant | 6:30-7:30 | 60s | data-chart | DREAM cluster + NL/NO/CA callouts |
| 8 | scene-008 | The Grind Quadrant | 7:30-8:00 | 30s | data-chart | GRIND — only USA + South Korea |
| 9 | scene-009 | The Grind Quadrant | 8:00-9:15 | 75s | composite | USA vs Denmark + CalendarGrid 55 days |
| 10 | scene-010 | The Chill Quadrant | 9:15-10:15 | 60s | composite | Italy + Portugal vs Hungary division |
| 11 | scene-011 | The Trap Quadrant | 10:15-11:00 | 45s | data-chart | Greece vs Germany connector (3×) |
| 12 | scene-012 | The Trap Quadrant | 11:00-11:45 | 45s | data-chart | Mexico extreme + Israel callout |
| 13 | scene-013 | The Data Behind the Numbers | 11:45-12:00 | 15s | composite | Lower-third sources over dimmed matrix |
| 14 | scene-014 | Closing Thought | 12:00-12:15 | 15s | data-chart | Full matrix hero shot, zoom begins |
| 15 | scene-015 | Closing Thought | 12:15-12:36 | 21s | composite | USA-DK zoom + end card |

## New Components Needed

| Component | Scenes | Priority | Complexity |
|-----------|--------|----------|------------|
| `SalaryShuffleScene` | 001 | Medium | Medium — text + flag + spring re-sort |
| `RankingResortScene` | 004 | High | High — dual-column animated rank with trails |
| `CalendarGrid` | 009 | High | Medium — 12-month grid with 55 highlighted days |
| `DivisionComparison` | 010 | Medium | Low — animated division equation |
| `ComparisonOverlay` | 009, 011, 012 | High | Medium — connector line + stat card |
| `EndCardScene` | 015 | Low | Low — fade + watermark |

## QuadrantScatter Enhancements Needed

1. **Selective dimming** — dim all dots except specified ones
2. **Camera zoom** — smooth zoom into specific coordinate region
3. **Connector lines** — draw lines between country dots with midpoint label
4. **Phased dot entrance** — show dots by quadrant (DREAM → GRIND → CHILL → TRAP)

## Quadrant Color Assignments

| Quadrant | Dot Color | Fill (8% opacity) |
|----------|-----------|-------------------|
| DREAM (top-left) | #5BBF8C (Muted Green) | rgba(91,191,140,0.08) |
| GRIND (top-right) | #D8A7B1 (Muted Pink) | rgba(216,167,177,0.08) |
| CHILL (bottom-left) | #90AFC5 (Muted Blue) | rgba(144,175,197,0.08) |
| TRAP (bottom-right) | #E06070 (Muted Red) | rgba(224,96,112,0.08) |

## Assets to Create/Collect

1. **Country flag icons** — 33 SVG flags (emoji fallback for prototype)
2. **Big Mac image** — AI-generated, dark moody bg (`npm run generate-image`)
3. **Zurich + Mexico City silhouettes** — AI-generated or Pexels stock
4. **Calendar grid component** — for 55-day visualization
