# Scene 017 Review — Human Body Microplastic Locations

## Spec vs Render Comparison

### ✅ PASS Items

1. **AI image style** — Human body anatomical silhouette, dark translucent, x-ray style. Matches spec's "anatomical outline style" perfectly. Cinematic, documentary aesthetic achieved.
2. **Background color** — Dark, close to #2A2A32. On-brand.
3. **Three organ regions highlighted** — Brain (top of head), Lungs (chest), and a lower pelvic organ are all visible with pink fiber particle clusters. Matches the "three location markers" concept.
4. **Fiber particle clusters** — Pink/pinkish fiber-like structures visible in all three organ areas. Good.
5. **Source citation** — "Source: Leslie et al., Env. Int., 2022" visible in bottom-right. Matches spec exactly.
6. **No identifiable face** — The silhouette is anonymous as required.
7. **Film grain / documentary feel** — The image has a subtle grain texture. Good.
8. **No off-brand colors** — No purple, no green. The pink fibers use accent pink range.

### 🔴 CRITICAL Issues

1. **ALL THREE TEXT OVERLAY LABELS ARE MISSING**
   - Category: Content Completeness
   - Spec requires three text overlays with blur-fade-in:
     - "Found in human lungs" (at lung-area)
     - "Found in human brains" (at brain-area)  
     - "Found in placentas" (at placenta-area)
   - NONE of these labels appear in the render. The organs are highlighted visually but there is zero text identifying what they are.
   - A viewer cannot tell which organ is which without labels. This defeats the narrative purpose.
   - **Fix:** Add the three text overlay labels at their respective positions with connecting lines as specified in the JSON `textOverlay.lines` array.

2. **Placenta depicted as UTERUS/REPRODUCTIVE ORGAN — anatomically misleading**
   - Category: Data Accuracy / Scientific Accuracy
   - Spec says "Placenta" — the third location. The render shows what appears to be a uterus with fallopian tubes (a complete female reproductive system outline), NOT a placenta specifically.
   - A placenta is a temporary organ that exists only during pregnancy. Showing a uterus as "placenta" is anatomically incorrect and could undermine credibility.
   - Without the text labels (Issue #1), viewers will see "reproductive organs" and be confused about what's being claimed.
   - **Fix:** This is an AI-generated image issue. Either: (a) regenerate with a prompt that specifically shows a placenta (a disk-shaped organ attached to uterine wall during pregnancy), or (b) if keeping this image, the text label "Found in placentas" with a connecting line would at least clarify intent. Option (a) is scientifically preferable.

### 🟡 MINOR Issues

3. **No connecting lines from labels to organs**
   - Category: Visual Spec Compliance
   - Spec description says "Each location label in Inter 400 with connecting line." Since labels are missing entirely, connecting lines are also absent.
   - **Fix:** Implement alongside the text labels (part of fix for Issue #1).

4. **Brain region is subtle / low contrast**
   - Category: Readability
   - The brain area at the top of the head has very faint pink fiber clusters compared to the lungs (which are prominently detailed). The brain highlight is barely visible — could be missed by viewers.
   - **Fix:** Increase the brightness/opacity of the fiber cluster in the brain region, or add a subtle glow effect to make it more visible.

5. **Screen utilization — bottom third is empty**
   - Category: Layout
   - The silhouette is centered but the lower portion (below the pelvic area) is mostly empty dark space. Estimated utilization ~55%.
   - Acceptable for this artistic/narrative scene, but the missing text labels would have filled some of this space.

### Screen Utilization
- ~55%. The silhouette dominates the center well, but the absence of text overlays leaves the composition feeling incomplete.

## Summary

| Aspect | Rating |
|--------|--------|
| Data Accuracy | 🔴 Placenta shown as uterus |
| Layout | 🟡 Acceptable but text-less |
| Colors | ✅ PASS — brand compliant |
| Text/Labels | 🔴 ALL labels missing |
| Source Citation | ✅ PASS |
| Visual Quality | 🟡 Brain region too subtle |

**Scene 017 Verdict: FAIL — missing all text overlays makes this scene unintelligible to viewers, and the placenta/uterus confusion is a scientific accuracy problem.**
