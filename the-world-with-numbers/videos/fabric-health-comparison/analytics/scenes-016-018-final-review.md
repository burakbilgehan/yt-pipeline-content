# Scenes 016–018 Final Review — Test Render Quality Gate

**Project:** fabric-health-comparison
**Channel:** the-world-with-numbers
**Stage:** Production — Test Render Review
**Scenes:** 016, 017, 018
**Date:** 2026-04-06

---

VERDICT: **FAIL**
GRADE: **D**

---

## STRENGTHS

1. **Source citations are 3/3** — every scene has the correct academic source in bottom-right. Consistent placement, correct text. This is a non-trivial win for a data-driven channel.
2. **Brand color compliance is perfect** — no purple, no green, no off-brand colors in any scene. Background consistently #2A2A32. Accent pink and secondary blue used correctly.
3. **Scene 018 AI image is excellent** — the fabric-skin cross-section illustration is the strongest visual of the batch. Clear scientific metaphor, detailed skin layers, tight-vs-loose weave contrast immediately communicable. High production quality.
4. **Scene 017 AI image has strong cinematic quality** — the x-ray anatomical silhouette with fiber particles achieves the documentary aesthetic well. Film grain present.
5. **Conceptual accuracy of all three scenes** — the underlying visual concepts match their storyboard specs. The problems are execution-level, not conceptual.

## ISSUES

### 🔴 CRITICAL

1. [🔴 Critical] [Data Accuracy]
   Description: Scene 016 bar chart proportions are completely wrong. The Minimum bar (58 years) and Maximum bar (1,200 years) render at nearly identical widths. 1,200 is ~20.7x larger than 58 — the Minimum bar should be ~5% of chart width, not ~95%. This is misleading data visualization.
   Location: Scene 016 — bar-chart template width calculation
   Fix: Fix the bar width scaling logic in the horizontal bar chart component. Minimum bar width = 58/1200 ≈ 4.8% of chart area. Verify by re-rendering and confirming visual 20:1 ratio.

2. [🔴 Critical] [Content Completeness]
   Description: Scene 017 is missing ALL THREE text overlay labels ("Found in human lungs", "Found in human brains", "Found in placentas"). Without labels, a viewer sees highlighted organs but cannot identify what they are or what's being claimed. The scene is unintelligible.
   Location: Scene 017 — textOverlay rendering (likely not wired to the ai-image template)
   Fix: Implement textOverlay.lines rendering for ai-image scenes. Add the three labels at lung-area, brain-area, and placenta-area positions with connecting lines as specified in scene-017.json.

3. [🔴 Critical] [Content Completeness]
   Description: Scene 018 is missing BOTH text overlay labels ("Occlusive Microenvironment" in Accent Pink, "Breathable" in Accent Blue). These are the key educational terms — without them the viewer sees a nice illustration but doesn't learn the scientific concept.
   Location: Scene 018 — textOverlay rendering (same root cause as Scene 017)
   Fix: Same as Scene 017 — implement textOverlay.lines for ai-image scenes. Add left-label and right-label at respective positions with correct brand colors.

4. [🔴 Critical] [Visual Spec Compliance]
   Description: Scene 016 has no gradient fill across the bar. Spec requires "gradient fill (Accent Blue at 58 → Accent Pink at 1,200)." Render shows two separate solid-color bars (flat blue, flat pink).
   Location: Scene 016 — bar-chart template fill/color logic
   Fix: Implement CSS linear-gradient or SVG gradient fill from #7BA7C9 to #E88CA5 across the bar range.

5. [🔴 Critical] [Scientific Accuracy]
   Description: Scene 017 depicts the placenta location as a full uterus with fallopian tubes. A placenta is a temporary organ during pregnancy, not the uterus itself. This could undermine channel credibility with knowledgeable viewers.
   Location: Scene 017 — AI-generated image prompt / asset
   Fix: Regenerate the AI image with a prompt that specifically shows a placenta (disk-shaped organ), or at minimum ensure the text label "Found in placentas" is prominent enough to clarify intent.

### 🟡 MINOR

6. [🟡 Minor] [Content Completeness]
   Description: Scene 016 missing secondary stat "500,000+ microfibers per kg per wash" from spec's secondaryStat field.
   Location: Scene 016 — bar-chart template, secondaryStat rendering
   Fix: Add secondary stat text below chart area in JetBrains Mono.

7. [🟡 Minor] [Visual Spec Compliance]
   Description: Scene 016 missing scale markers at 58, 200, 500, 1000, 1200 years along the x-axis.
   Location: Scene 016 — bar-chart template, axis rendering
   Fix: Add x-axis with labeled tick marks at specified values.

8. [🟡 Minor] [Layout]
   Description: Scene 016 human lifespan reference line (~80 years) is detached from chart area. Should be a vertical line overlaid ON the bars.
   Location: Scene 016 — bar-chart template, annotation positioning
   Fix: Render the ~80yr mark as a vertical dashed line at the proportionally correct x-position within the chart area.

9. [🟡 Minor] [Readability]
   Description: Scene 017 brain region fiber clusters are too subtle/low contrast compared to lungs. Could be missed by viewers.
   Location: Scene 017 — AI image asset
   Fix: Increase brightness/opacity of brain region fiber clusters, or add subtle glow.

10. [🟡 Minor] [Layout]
    Description: Scene 017 screen utilization ~55%. Bottom third mostly empty. Missing text labels would have filled some of this space.
    Location: Scene 017 — overall composition
    Fix: Adding the missing text overlays will improve utilization. No other action needed.

---

## Root Cause Analysis

**The text overlay issue (Issues #2 and #3) shares a single root cause:** the Remotion template for `ai-image` type scenes likely does not render `textOverlay.lines` from the storyboard JSON. This affects 2 out of 3 scenes reviewed — it's a systemic template gap, not a per-scene oversight.

**The bar chart issue (Issue #1) is a scaling bug** in the horizontal bar chart component — likely dividing both values by themselves or using a wrong normalization.

**Priority order for fixes:**
1. Fix textOverlay rendering for ai-image scenes (unblocks 017 + 018)
2. Fix bar width scaling logic (unblocks 016)
3. Add gradient fill to bar chart (016)
4. Address minor items (scale markers, secondary stat, reference line, brain contrast)

---

## Per-Scene Summary

| Scene | Verdict | Critical Issues | Minor Issues | Best Aspect |
|-------|---------|----------------|--------------|-------------|
| 016 | FAIL | 2 (bar proportions, no gradient) | 4 | Colors, source citation |
| 017 | FAIL | 2 (all labels missing, placenta anatomy) | 3 | AI image cinematic quality |
| 018 | FAIL | 1 (both labels missing) | 2 | AI image is excellent — best of batch |

**Overall: 3/3 scenes FAIL. Grade D — significant problems that must be fixed before these scenes can ship.**
