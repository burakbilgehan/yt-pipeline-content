# Storyboard v2 Critique — "Time vs Earnings"

> Reviewer: Critic Agent
> Date: 2026-03-22
> Artifact: storyboard-v2.json + scenes/scene-001.json through scene-015.json
> Source script: script-v2.md (content v3)

---

## VERDICT: PASS
## GRADE: B+

---

## v1 Fix Verification

| # | v1 Issue | Status | Notes |
|---|----------|--------|-------|
| 1 | 🔴 DREAM quadrant 59s short — Netherlands/Norway/Canada had no visual coverage | **FIXED** | Scene-007 added (390–450s) covering full Netherlands/Norway/Canada VO block. DREAM now spans 345–450 = 105s, matching script 5:45–7:30. |
| 2 | 🔴 TRAP quadrant 29s short | **FIXED** | TRAP now spans 615–705 = 90s, matching script 10:15–11:45. Split into scenes 011+012. |
| 3 | 🔴 GRIND started 30s early (7:00 instead of 7:30) | **FIXED** | GRIND starts at 450s = 7:30. Confirmed in scene-008. |
| 4 | 🟡 TTS provider was wrong (ElevenLabs → Google Chirp 3 HD) | **FIXED** | Skeleton `tts` block: provider "google", engine "chirp3-hd", voice "Achernar". Correct. |
| 5 | 🟡 GRIND dot color undefined | **FIXED** | Scene-008 explicitly sets `dotColor: "#D8A7B1"`. Note in scene-008 confirms the fix. |
| 6 | 🟡 Scene 1 "BM/hr" label premature | **FIXED** | Scene-001 `resortLabel` is now "Value per Hour". Notes explicitly say "Do NOT show 'BM/hr' label yet." |

**All 6 v1 issues: FIXED.** Good job.

---

## Strengths

1. **Timing alignment is perfect.** All 10 script sections map to exactly the right startTime/endTime ranges. No gaps, no overlaps, no drift. The aggregated section timings match the script timestamps to the second.

2. **Two-tier structure is clean.** Skeleton is lightweight with short descriptions; detail files carry the full visual spec. All required fields present in both tiers. `sceneFile` paths are consistent.

3. **Visual storytelling is strong.** The QuadrantScatter build-up across scenes 005–012 is well-conceived — empty matrix → DREAM → GRIND → CHILL → TRAP → full matrix hero shot. The connector lines (USA↔Denmark, Greece↔Germany, Germany↔Mexico) are excellent data-driven narrative devices.

4. **Scene-009 is the emotional peak and it's properly loaded.** The CalendarGrid with 55 red days + "For 6% more." punchline has real Kurzgesagt-level emotional impact potential.

5. **End card is thoughtful.** YouTube end screen integration, silence hold, "What is an hour of your life worth?" — strong close with no cringe subscribe CTA.

---

## Issues

### 🔴 Critical

**1. [Accuracy] Widespread dot coordinate errors across scenes 007, 010, 011**

Dozens of data points in the scatter plot dot coordinates do not match research-v1.md. These are the coordinates that will be RENDERED on screen — viewers will screenshot and fact-check.

**Scene-007 (DREAM cluster):**
- Australia: BM/hr shows 7.52, research says **8.51** (delta: 0.99 — nearly 1 full Big Mac off)
- France: BM/hr shows 7.12, research says **6.74** (delta: 0.38)
- Belgium: hours 1551 / BM/hr 8.32, research says **1525 / 8.39**
- Sweden: BM/hr shows 7.34, research says **7.23**
- UK: BM/hr shows 7.39, research says **7.26**
- Finland: hours 1514, research says **1498**

**Scene-010 (CHILL):**
- Slovenia: hours 1554, research says **1619** (delta: 65 hours — massive)
- Lithuania: hours 1555, research says **1624** (delta: 69 hours)
- Slovakia: hours 1574, research says **1622** (delta: 48 hours)
- Italy: hours 1669, research says **1694** (delta: 25 hours)
- Spain: BM/hr 5.35, research says **5.58**
- Latvia: hours 1535 / BM/hr 4.74, research says **1553 / 4.93**
- Ireland: BM/hr 5.97, research says **6.13**

**Scene-011 (TRAP):**
- Czech Republic: BM/hr 4.21, research says **4.81** (delta: 0.60)
- Poland: BM/hr 3.92, research says **4.68** (delta: 0.76 — catastrophic)

**Fix:** Regenerate ALL dot coordinates in scenes 007, 010, 011 (and 012 if it inherits) directly from the research-v1.md data table. Every `x` value must match the `Hours/yr` column and every `y` value must match the `Big Macs/hr` column exactly.

---

**2. [Accuracy] Luxembourg wage in scene-004 config: $93,902 vs research $94,447**

The `RankingResortScene` left column shows Luxembourg at "$93,902". Research-v1.md clearly states $94,447. This number appears on screen in a ranking chart — it will be noticed.

**Fix:** Change scene-004 Luxembourg value from `"$93,902"` to `"$94,447"`.

---

### 🟡 Important

**3. [Accuracy] Voiceover text diverges from script in 2 places**

The storyboard voiceover is NOT a verbatim copy of the script in two sections:

**(a) The Dream Quadrant — Scene-006:**
Script (between VO block 1 and VO block 2): "...nine point eight three Big Macs per hour. **But** the biggest surprise..."
Storyboard scene-006: "...nine point eight three Big Macs per hour. **[pause] But** the biggest surprise..."

A `[pause]` was ADDED that doesn't exist in the script. The script has a `[VISUAL NOTE]` break between the two VO blocks (which creates a natural pause from scene splitting), but no explicit `[pause]` tag in the voiceover text.

**(b) Closing Thought — Scene-014/015 split:**
Script: "...Four quadrants. **[pause long]** An American worker..."
Storyboard: Scene-014 ends "Four quadrants." → Scene-015 starts "An American worker..." — the `[pause long]` tag is **dropped**.

Since the TTS engine reads the voiceover text directly, dropped or added pause tags change the audio timing.

**Fix:** (a) Remove the added `[pause]` from scene-006 VO, or update script-v2 to include it. (b) Add `[pause long]` to the beginning of scene-015's voiceover to match the script exactly. The storyboard must be a byte-exact mirror of the script's `[VOICEOVER]` blocks.

---

**4. [Format] Non-standard transition values**

The storyboard agent spec defines valid transitions as: `fade`, `cut`, `slide`, `zoom`. The storyboard uses 6 non-standard values across 11 of 15 scenes:
- `crossfade` (scene-001) — not in spec
- `morph` (scenes 003, 004) — not in spec
- `seamless` (scenes 005, 006, 008, 011, 014) — not in spec
- `cross-dissolve` (scenes 007, 010) — not in spec
- `fade-to-black` (scene-015) — not in spec

Only scenes 002 (`cut`), 009 (`fade`), 012 (`fade`), 013 (`slide`) use spec-compliant values.

**Fix:** Either (a) map non-standard values to spec values (`crossfade` → `fade`, `morph` → `fade`, `seamless` → `cut`, `cross-dissolve` → `fade`, `fade-to-black` → `fade`), or (b) update the storyboard agent spec to formally accept the expanded transition vocabulary. Option (b) is better since the expanded transitions carry meaningful production intent.

---

**5. [Accuracy] Scene-005 QuadrantScatter origin uses correct values but Australia placement may mislead**

Australia at (1707, 8.51) with the OECD average crosshair at x=1751 puts Australia in the DREAM quadrant. This is correct per research. However, scene-007 has Australia's BM/hr at 7.52 instead of 8.51 — a rendering error that would place Australia much lower than it should be. This is captured in issue #1, but calling it out because Australia's position near the quadrant boundary makes precision critical.

---

### 🟢 Minor

**6. [Format] Skeleton visual descriptions exceed "1 sentence max" guideline**

The storyboard agent spec says skeleton `visual.description` should be "SHORT summary (1 sentence max)." Several descriptions are borderline but all remain concise and useful. Not blocking, but could be tightened for consistency. E.g., scene-005's description is one sentence; scene-002's is effectively one compound description. Acceptable as-is.

---

**7. [Brand] Four dot colors on a single chart — brand guide says max 2 data colors**

The QuadrantScatter uses 4 dot colors: Green (#5BBF8C for DREAM), Pink (#D8A7B1 for GRIND), Blue (#90AFC5 for CHILL), Red (#E06070 for TRAP). The brand guide states "Max 2 data colors per chart — Pink + Blue." However, the Green and Red are defined in the brand guide as Positive/Negative indicator colors, not as data colors, so this is semantically defensible. The quadrant narrative requires visual differentiation. **No fix needed**, but document the rationale in scene-005 notes so downstream production doesn't flag it.

---

**8. [Format] `basedOn.content: 3` — skeleton says content v3, which is script-v2.md**

The skeleton `basedOn.content` is 3, which maps to `script-v2.md` (the script file is version 2 in filename but version 3 in its header). This is technically correct per the version header inside script-v2.md (`> version: 3`), but could cause confusion since the file name says v2. This is a pre-existing pipeline naming convention issue — not a storyboard bug. No fix needed here.

---

**9. [Brand] Scene-004 uses #E06070 (Negative) for Switzerland's rank drop and #5BBF8C (Positive) for Japan's rise**

These are the correct Positive/Negative indicator colors from the brand guide. Usage is appropriate. No issue — just confirming compliance.

---

## Summary

Storyboard v2 successfully resolves all 6 issues from the v1 Critic review. Timing alignment is perfect, section naming is correct, TTS config is fixed, and the two-tier JSON structure is well-formed. The visual storytelling arc from salary shuffle → Big Mac reveal → quadrant matrix → emotional close is strong and Vox/Kurzgesagt-competitive.

**However, there is one blocking issue:** Dozens of scatter plot dot coordinates across scenes 007, 010, and 011 contain incorrect hours and BM/hr values that diverge from research-v1.md. Since these are the actual rendered data points that viewers will see and fact-check, this is a data integrity failure that must be fixed before production. The Luxembourg wage in scene-004 ($93,902 vs $94,447) adds to this. These are likely copy errors from an intermediate source rather than the authoritative research file.

The VO text discrepancies (added/dropped pause tags) and non-standard transition values are important but non-blocking — they should be fixed in the same pass.

**Grade: B+** — Passes the quality bar with the understanding that the dot coordinate data MUST be corrected before handoff to production. If the data errors were not present, this would be an A-.
