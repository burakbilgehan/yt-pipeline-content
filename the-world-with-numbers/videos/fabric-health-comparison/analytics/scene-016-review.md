# Scene 016 Review — Synthetic Microfiber Persistence

## Spec vs Render Comparison

### ✅ PASS Items

1. **Title** — "Synthetic Microfiber Persistence" matches spec exactly. Bold, white, top-left. Readable.
2. **Chart type** — Horizontal bar chart as specified. Two bars: Minimum and Maximum.
3. **Data values** — "58 years" and "1,200 years" displayed correctly, matching JSON items.
4. **Labels** — "Minimum" and "Maximum" labels present on left side of bars.
5. **Context annotation** — "Human lifespan: ~80 years" present at bottom with a vertical reference line. Spec says "Human lifespan: ~80 years" — matches.
6. **Source citation** — "Source: De Falco et al., Scientific Reports, 2019" visible bottom-right. Matches spec.
7. **Background color** — Appears to be #2A2A32 (dark charcoal). On-brand.
8. **Bar colors** — Minimum bar is blue (#7BA7C9 range), Maximum bar is pink (#E88CA5 range). Matches spec colors array.

### 🔴 CRITICAL Issues

1. **Bar lengths are visually WRONG — both bars appear nearly the same width**
   - Category: Data Accuracy
   - The Minimum bar (58 years) and Maximum bar (1,200 years) are rendered at nearly identical widths. The Maximum bar is only marginally wider than the Minimum bar.
   - In reality, 1,200 is ~20.7x larger than 58. The Maximum bar should be roughly 20x the length of the Minimum bar.
   - This completely destroys the data visualization's purpose — the viewer cannot perceive the massive difference between 58 and 1,200 years.
   - **Fix:** The bar-chart component is likely scaling both bars to a 0-max range but rendering minimum incorrectly. The Minimum bar at 58/1200 = 4.8% of the chart width, not ~95%. Fix the bar width calculation in the bar-chart template.

2. **No gradient fill across the bar**
   - Category: Visual Spec Compliance
   - Spec says: "gradient fill (Accent Blue at 58 → Accent Pink at 1,200)" — this implies a SINGLE continuous bar from 58 to 1,200 with gradient, or at minimum gradient-colored bars.
   - Render shows two separate solid-color bars (one flat blue, one flat pink). No gradient transition.
   - **Fix:** Implement gradient fill as specified — either a single range bar with CSS linear-gradient, or apply gradient coloring across both bars.

### 🟡 MINOR Issues

3. **Missing secondary stat: "500,000+ microfibers per kg per wash"**
   - Category: Content Completeness
   - Spec field `secondaryStat` = "500,000+ microfibers per kg per wash" — this text is nowhere in the render.
   - **Fix:** Add the secondary stat text below the chart area, likely in JetBrains Mono per spec description.

4. **Missing scale markers at 58, 200, 500, 1000, 1200**
   - Category: Visual Spec Compliance
   - Spec description calls for "Scale markers at 58, 200, 500, 1000, 1200 years" along the axis. None are visible — there's no x-axis with tick marks.
   - **Fix:** Add an x-axis with labeled tick marks at the specified values.

5. **Human lifespan reference line placement is ambiguous**
   - Category: Layout
   - Spec says it should be "a thin vertical line early on the bar for perspective." In the render, it appears as a standalone label with a small vertical bar at the bottom of the chart, detached from the bars themselves. It should be overlaid ON the bar area as a vertical reference line cutting through the chart.
   - **Fix:** Render the ~80 year mark as a vertical dashed line overlaid on the chart area at the proportionally correct x-position.

6. **Font verification uncertain**
   - Category: Brand Compliance
   - Spec requires JetBrains Mono for all numbers. The "58 years" and "1,200 years" labels appear to use a sans-serif font but it's difficult to confirm if it's JetBrains Mono vs Inter from the render. Worth verifying in code.

### Screen Utilization
- Estimated ~55-60%. The chart area uses a good portion but the bottom third is mostly empty (where the secondary stat should go). Borderline acceptable.

## Summary

| Aspect | Rating |
|--------|--------|
| Data Accuracy | 🔴 FAIL — bar proportions are completely wrong |
| Layout | 🟡 Acceptable but missing elements |
| Colors | ✅ PASS — brand compliant |
| Text/Labels | 🟡 Missing secondary stat |
| Source Citation | ✅ PASS |
| Visual Quality | 🟡 No gradient, no scale markers |

**Scene 016 Verdict: FAIL — the bar proportions make this misleading data visualization.**
