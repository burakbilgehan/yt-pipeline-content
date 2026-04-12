# Critic Review Round 4 — Full 27-Scene Visual Audit

**Date:** 2026-04-06  
**Status:** 0 FAIL / 14 MINOR / 13 PASS  
**Overall Grade:** B+  

---

## Actionable Fixes (sorted by priority)

### HIGH — Data precision / readability

| # | Scene | Issue | Fix Type | Fix |
|---|-------|-------|----------|-----|
| 1 | 005 | Pie legend shows "69.0%" / "31.0%" — unnecessary decimals | Code | PieChart.tsx: format as integers when `value % 1 === 0` |
| 2 | 015 | Text overlay "110,000 fibers..." overlaps chart title at top-center | Code/JSON | Either offset textOverlay position or change to phase 2 |
| 3 | 008 | "Hazardous" bar label shows "150" — should be "150+" per source data | JSON | scene-008.json: change item displayValue to "150+" |

### MEDIUM — Visual polish

| # | Scene | Issue | Fix Type | Fix |
|---|-------|-------|----------|-----|
| 4 | 018 | "Breathable" label renders pink — should be blue (#7BA7C9) for positive/natural side | Code/JSON | scene-018.json: add color hint to right-side label, or update AI-image text overlay renderer |
| 5 | 013 | Annotation card border appears neutral — storyboard says Negative Red (#D94F4F) | Code | Verify ComparisonTable DuelComparison annotation card border color |
| 6 | 023 | Missing Linen/Hemp callout from storyboard description | JSON | Add `annotation` field to scene-023.json dataChart |
| 7 | 019 | Viscose bar grey (#9E9E9E) — notes say Positive Green (#5BBF8C) | JSON | scene-019.json colors[3]: decide grey vs green |

### LOW — Cosmetic / design interpretation

| # | Scene | Issue | Fix Type | Fix |
|---|-------|-------|----------|-----|
| 8 | 004 | 2030 projection marker not dashed (solid like historical) | Code | TimelineChart: add dashed style for future projections |
| 9 | 013 | "V S" spacing between entity labels | Code | ComparisonTable "vs" separator |
| 10 | 014 | Unit "ng/g (median BPA)" wraps across two lines | Code | BarChart: abbreviate or single-line unit labels |
| 11 | 016 | Renders as two bars instead of single gradient range bar | Template | Would require new sub-template — accept as-is |
| 12 | 022 | Detail card "03" number low contrast | Code | VerticalTabScene: increase number opacity |

### UNVERIFIABLE — Need Phase 2 stills

| # | Scene | Issue | Action |
|---|-------|-------|--------|
| 13 | 002 | Phase 2 "eco-friendly ≠ safe" glitch text | Render still at ~80% frame |
| 14 | 007 | Phase 2 "Not enough farmland..." blur-fade text | Render still at ~80% frame |
| 15 | 025 | Phase 2 "Fewer finishes = Fewer chemicals" stagger-reveal | Render still at ~80% frame |

---

## Scenes PASSED (no issues)

001, 004, 006, 009, 010, 012, 017, 020, 021, 024, 026, 027

## Scenes MINOR (fixable)

002, 003, 005, 007, 008, 011, 013, 014, 015, 016, 018, 019, 022, 023, 025
