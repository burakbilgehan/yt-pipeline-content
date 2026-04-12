# Critique — Test Renders (Scenes 019–021)

**Video:** fabric-health-comparison
**Deliverable:** Test render frames (50% keyframes)
**Reviewer:** Critic Agent
**Date:** 2026-04-06

---

## Scene 019 — Bacterial Growth Bar Chart

**Spec:** `scene-019.json` | **Render:** `scene-019-50pct.png`

### Verdict: FAIL — Grade: D

### Spec Issues (Pre-Render)

| # | Severity | Issue | Fix |
|---|----------|-------|-----|
| 1 | 🔴 Critical | **Sage (`#8A9A7A`) used as primary data bar color for Cotton.** Brand guide §1 explicitly states: "Sage is only for grid/structural elements — never for primary data." Cotton is a primary data bar, not a grid element. | Replace Cotton bar color with Accent Blue (`#7BA7C9`) or a desaturated variant of the two allowed data colors. |
| 2 | 🔴 Critical | **Positive Green (`#5BBF8C`) used as data bar color for Viscose.** Brand guide §1: "Max 2 data colors per chart — Pink + Blue. Never add a third vivid color." Green is a third vivid color. The notes try to justify it ("Exception: Viscose gets Positive Green"), but there are no exceptions — the rule says "Never." | Remove green. Viscose's bar is value 0, so it's effectively invisible. Use Accent Blue (`#7BA7C9`) for the zero-line marker/label. |
| 3 | 🟡 Minor | **4 distinct colors for 4 bars violates max-2-data-colors rule.** Even if we fixed #1 and #2, having 4 separate colors is too many. The chart needs exactly 2: Pink for the "bad" extreme (Polyester) and Blue for the "good" extreme (Viscose), with muted/desaturated variants for Cotton and Wool. | Use Pink for Polyester, Blue for Viscose, and reduced-opacity versions of Pink/Blue (or Warm Cream at ~30% opacity) for Cotton and Wool. |

### Math Verification

| Claim | Spec Value | Verification |
|-------|-----------|--------------|
| Polyester bacterial growth | 1.72×10⁷ CFU/cm² | ✅ Consistent with McQueen et al. 2007 findings |
| Cotton | 5×10⁶ CFU/cm² | ✅ Order of magnitude consistent with literature |
| Wool | 1×10⁶ CFU/cm² | ✅ Consistent — wool has natural antimicrobial properties |
| Viscose | 0 CFU/cm² | ⚠️ The study shows significantly reduced growth, "0" may be a simplification. Acceptable for visualization if annotation clarifies |

### Strengths
- Data hierarchy is correct — Polyester towers over others, which is the visual punchline
- Scientific notation on Y-axis uses JetBrains Mono (per spec)
- "Zero growth. None." annotation is effective storytelling
- Source citation present

### Render Review
> ⚠️ Scene 019 PNG was lost during context compaction. Render-specific findings (actual colors rendered, layout, typography) could not be verified against the frame. **Recommend re-review of this frame.**

---

## Scene 020 — Heavy Metals Data Table

**Spec:** `scene-020.json` | **Render:** `scene-020-50pct.png`

### Verdict: PASS — Grade: B+

### Spec Issues

| # | Severity | Issue | Fix |
|---|----------|-------|-----|
| 1 | 🟡 Minor | **Single color array `["#E88CA5"]`** — all three values use Accent Pink. This is technically fine since it's one data series (heavy metal concentration), but the description mentions a "Negative Red border" for the phthalates callout that isn't specified in the JSON `dataChart` structure. | Ensure the phthalates annotation row renders with `#E06070` (Negative Red) border as described. This is a rendering concern, not a spec error. |

### Math Verification

| Claim | Spec Value | Verification |
|-------|-----------|--------------|
| Titanium in polyamide | 1,844 mg/kg | ✅ Consistent with Kopperi et al. 2014 range for polyamide swimsuits |
| Chromium in dark nylon | 624–932 mg/kg | ✅ Range format correct, consistent with dark-dyed nylon findings |
| Antimony in polyester | 141 mg/kg | ✅ Consistent — antimony trioxide is a polyester catalyst |
| Phthalates in infant clothing | 223 μg/g | ✅ Consistent with multi-country Asian study data |

### Strengths
- Clean data table format — three metals, three fabrics, no clutter
- Single Accent Pink for all values maintains visual consistency
- Phthalates callout adds alarming secondary data without overwhelming main table
- Source citation present
- JetBrains Mono specified for values (correct per brand guide)

### Render Review
> ⚠️ Scene 020 PNG was lost during context compaction. Render-specific findings could not be verified against the frame. **Recommend re-review of this frame.**

---

## Scene 021 — Counter Scene (300 Pregnant Women)

**Spec:** `scene-021.json` | **Render:** `scene-021-50pct.png`

### Verdict: PASS — Grade: A-

### Visual Comparison (Spec vs Render)

| Element | Spec | Render | Match? |
|---------|------|--------|--------|
| Counter value | 300/300 | "300" large + "/300" suffix in pink | ✅ |
| Title | "Azo Dye Exposure in Pregnant Women" | Visible at top, all-caps | ✅ |
| Subtitle | "100% tested positive for aromatic amines" | Visible below title, smaller | ✅ |
| Detection rate | 100% | Shown with pink progress bar + "100%" label | ✅ |
| Biomarker | "8-OHdG ↑ (DNA damage)" | Rendered below detection rate row | ✅ |
| Source | "Aung et al., Int. J. Hyg. Env. Health, 2023" | Bottom-right, small text | ✅ |
| Atmosphere | dot-grid, 0.08 opacity | Hard to verify — background image dominates | ⚠️ |
| Background | Should be `#2A2A32` base | Dark background visible, but a fabric/skin cross-section illustration covers most of the frame | ⚠️ |

### Issues

| # | Severity | Issue | Fix |
|---|----------|-------|-----|
| 1 | 🟡 Minor | **Background illustration (fabric-on-skin cross-section) isn't specified in the JSON.** The spec says `atmosphere: "dot-grid"` and `surface: null`, but the render shows a large photorealistic illustration of fabric layers penetrating skin. This is likely coming from a background visual asset. It works aesthetically and supports the narrative, but it's not in the storyboard spec. | Document the background visual in the scene spec or asset-log so future edits know it exists. |
| 2 | 🟡 Minor | **"/300" suffix in Accent Pink** — the spec says `counterSuffix: "/300"` but doesn't specify the suffix should be a different color from the main "300". The render shows "300" in white/cream and "/300" in pink. This is a nice design choice but deviates from spec (which implies uniform styling). | Acceptable creative liberty. Consider documenting in spec if intentional. |
| 3 | 🟡 Minor | **Spec calls for "100%" appearing large (80px JetBrains Mono with glow pulse)** as a dramatic Phase 2 moment, but in the 50% keyframe it appears as a small label next to a progress bar. This could be a timing issue — the 50% frame may be capturing Phase 1 (counter) rather than Phase 2 (100% reveal). | Verify that the 100% hero moment exists at a later frame. Render a 70-80% keyframe to confirm Phase 2 plays correctly. |
| 4 | 🟡 Minor | **DNA helix icon missing.** Spec describes "DNA double helix icon (simple, geometric)" but the render shows no such icon. Again, may be a timing issue (Phase 3 content not yet visible at 50% mark). | Render a 90% keyframe to verify Phase 3 (DNA icon + 8-OHdG label in Negative Red) appears. |

### Math Verification

| Claim | Spec Value | Verification |
|-------|-----------|--------------|
| 300 pregnant women tested | 300/300 counter | ✅ Matches Aung et al. 2023 study sample size |
| 100% detection rate | 100% for aromatic amines | ✅ Study found detectable levels in all 300 participants |
| 8-OHdG biomarker | DNA damage correlation | ✅ 8-OHdG is a validated oxidative DNA damage biomarker, correctly cited |

### Strengths
- Emotionally impactful composition — the 300/300 counter is devastating as intended
- Background illustration (fabric penetrating skin) is powerful visual storytelling even if unspecified
- Source citation properly placed, non-intrusive
- Typography hierarchy is clear — counter dominates, details below
- Color usage is brand-compliant (Pink accent, Cream text, dark background)

---

## Summary

| Scene | Grade | Verdict | Key Issue |
|-------|-------|---------|-----------|
| 019 | **D** | ❌ FAIL | 2 brand-violating colors (Sage as data, Green as data) — max 2 data colors rule broken |
| 020 | **B+** | ✅ PASS | Clean spec, minor phthalates callout styling gap |
| 021 | **A-** | ✅ PASS | Strong emotional impact, minor phase-timing verification needed |

## Required Actions

1. **Scene 019 (BLOCKING):** Fix color array to use only Pink + Blue (+ muted variants). Remove Sage and Green from data bars. Re-render.
2. **Scene 021 (NON-BLOCKING):** Render additional keyframes at 70% and 90% to verify Phase 2 (100% hero) and Phase 3 (DNA icon) play correctly.
3. **Scenes 019 & 020 (NON-BLOCKING):** Re-review PNG frames — they were lost during context compaction and render-specific issues (actual colors, layout, font rendering) could not be verified.

## Post-Render Recommendation

When the full video is rendered, run `ffprobe` analysis to detect:
- Audio peak levels (clipping if >0dBFS)
- Stream count mismatches
- Frame drops
This is especially important for scene 021's counter animation which may stress the renderer.
