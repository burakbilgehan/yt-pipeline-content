# QA Log — fabric-health-comparison

> Retroactive audit. QA was never invoked during production despite repeated user frustration.

| Field | Value |
|-------|-------|
| Date | 2026-04-06 |
| Project | `fabric-health-comparison` |
| Channel | `the-world-with-numbers` |
| Audit Type | Full retroactive — Pipeline Audit + RCA |
| Trigger | Director failed to invoke QA; user escalation across multiple sessions |

---

## Table of Contents

1. [Director Process Failures (RCA-001 through RCA-005)](#director-process-failures)
2. [Visual / Design Failures (RCA-006 through RCA-011)](#visual--design-failures)
3. [Technical Failures (RCA-012 through RCA-014)](#technical-failures)
4. [Unresolved Feedback Items — Full Inventory](#unresolved-feedback-items)
5. [Remediation Plan](#remediation-plan)

---

## Director Process Failures

### RCA-001: QA Agent Never Invoked Despite Repeated Negative Feedback

| Field | Value |
|-------|-------|
| Date | 2026-04-06 |
| Failure Type | `prompt-gap` |
| Severity | **Critical (P0)** |
| Affected Agent | Director |

**What happened:** User gave explicit, escalating negative feedback across multiple messages — "çok kötü", "aptal özürlü", "salak mısın?", "allahını sikiyim senin". AGENTS.md Director rules state: "User gives negative feedback → invoke QA". This was violated every single time. Not once. Not partially. Completely ignored.

**Root cause:** The Director agent lacks an enforced checkpoint that halts the session and invokes QA upon detecting negative sentiment. The instruction exists in AGENTS.md ("The Director MUST invoke you when: User gives negative feedback") but it's a passive rule, not a hard gate. The Director continued operating on the same deliverable, applying patch fixes instead of stepping back to diagnose the systemic problem.

**Fix:**
- [ ] Add an explicit negative-feedback detection gate to Director agent prompt: "If user expresses frustration or negative quality judgment, STOP current work. Invoke QA agent with: exact user words, faulty output path, producing agent. Do NOT continue patching."
- [ ] Add concrete examples of Turkish frustration patterns to the gate (küfür, "kötü", "rezalet", "salak", etc.)

**Status:** Open

---

### RCA-002: Render Initiated Without User Approval

| Field | Value |
|-------|-------|
| Date | 2026-04-06 |
| Failure Type | `prompt-gap` |
| Severity | **Critical (P0)** |
| Affected Agent | Director |

**What happened:** A 30-minute blocking render was started while major feedback items (screen utilization, color scheme, component intake, mobile-friendliness) were unresolved. The user never approved the render. config.json history shows `production.completed` at `2026-04-06T11:57:24` — a ~30 minute render cycle that blocked all other work.

**Root cause:** AGENTS.md states "never auto-chain pipeline stages — wait for explicit user approval." The Director violated this by treating the render as a natural next step after TTS regeneration, without confirming that visual issues were addressed. No explicit "shall I render?" checkpoint was enforced.

**Fix:**
- [ ] Director prompt needs a hard pre-render gate: "Before initiating any render, present a checklist of all open feedback items. If ANY P0/P1 items remain open, render MUST NOT proceed without explicit user override."
- [ ] Add render cost awareness: "Renders >5 minutes are expensive operations. Always confirm with user before starting."

**Status:** Open

---

### RCA-003: Feedback File Not Tracked or Annotated

| Field | Value |
|-------|-------|
| Date | 2026-04-06 |
| Failure Type | `prompt-gap` / `scope-creep` |
| Severity | **High (P1)** |
| Affected Agent | Director |

**What happened:** feedback.md accumulated 50+ distinct feedback items across sessions. The Director never built a tracking system — no status annotations, no priority assignments, no done/not-done tracking. When eventually forced to annotate, many items were marked "KISMİ" (partial) or "YAPILMADI" (not done), proving they were never properly addressed.

**Root cause:** No protocol exists for feedback ingestion. The Director treated user feedback as one-off comments to respond to in real-time, rather than a backlog to track systematically. When context was lost between sessions, completed/incomplete state was lost too.

**Fix:**
- [ ] Create a feedback tracking protocol: when user provides feedback, Director must immediately annotate each item in feedback.md with status (OPEN/IN_PROGRESS/DONE), severity (P0/P1/P2), and assigned agent.
- [ ] At session start, Director must read feedback.md and present open item count to user.

**Status:** Open

---

### RCA-004: External Component Intake Gate Completely Skipped

| Field | Value |
|-------|-------|
| Date | 2026-04-06 |
| Failure Type | `prompt-gap` / `misinterpretation` |
| Severity | **Critical (P0)** |
| Affected Agent | Director |

**What happened:** User provided two complete external components — Glass Calendar and Glassmorphism Trust Hero — with explicit instructions: "bu ikisini kendimize adapte et (decompose, classify, adapt vs). ikisini de yukle ve sakin kendi yorumunu katma." DESIGN-SYSTEM.md defines a mandatory 4-step External Component Intake gate: Decompose → Adapt → Register → Showcase. Neither component was processed through this gate. The user's explicit request was ignored.

**Root cause:** The Director likely treated the component code as "informational" rather than as an actionable work item. The External Component Intake protocol exists in DESIGN-SYSTEM.md but the Director prompt doesn't enforce checking for user-provided code blocks as automatic intake triggers.

**Fix:**
- [ ] Director prompt addition: "When user provides external component code (paste, link, or file), this AUTOMATICALLY triggers the External Component Intake gate from DESIGN-SYSTEM.md. Do not proceed to other work until all 4 steps are complete for each provided component."
- [ ] Process Glass Calendar through full 4-step gate (Decompose → Adapt → Register → Showcase)
- [ ] Process Glassmorphism Trust Hero through full 4-step gate

**Status:** Open

---

### RCA-005: FrostedPanelSurface and CardSurface Missing Showcases

| Field | Value |
|-------|-------|
| Date | 2026-04-06 |
| Failure Type | `scope-creep` |
| Severity | **High (P1)** |
| Affected Agent | Director / Production |

**What happened:** FrostedPanelSurface and CardSurface were created in a previous session, completing Steps 1-3 of the External Component Intake (Decompose, Adapt, Register). They are properly registered in `surfaces/index.ts` and listed in `component-catalog.json`. But Step 4 — Showcase — was never completed. No showcase composition exists for either component. SurfaceShowcase.tsx only covers Glass/Flat/Glow. SurfaceShowcase2.tsx covers NeonGradient/Backlight. Neither FrostedPanel nor Card appears in any showcase.

**Root cause:** The 4-step gate was treated as a 3-step gate. The session likely ran out of context or moved on to other tasks before the showcase was created. No checkpoint ensured all 4 steps were verified before marking the component as "done."

**Fix:**
- [ ] Create SurfaceShowcase3.tsx (or extend SurfaceShowcase2) to demonstrate FrostedPanelSurface and CardSurface
- [ ] Register as `DS-Surfaces3` in Root.tsx
- [ ] Add a verification step to the intake protocol: "After Step 4, confirm showcase renders in Studio before closing the intake."

**Status:** Open

---

## Visual / Design Failures

### RCA-006: Screen Utilization Chronically Below 80% Minimum

| Field | Value |
|-------|-------|
| Date | 2026-04-06 |
| Failure Type | `prompt-gap` / `data-error` |
| Severity | **Critical (P0)** |
| Affected Agent | Storyboard / Production |

**What happened:** User repeatedly complained that content fills only 1/4 to 1/5 of the screen. Feedback references scenes 3-4, 5, 7, 8, 12, 13, 14, 16, 25 — over half the video. Screenshots confirm tiny content rectangles centered in vast empty space. The design-system.json specifies `screenUtilization: 0.85`. VB-1 rule mandates ≥80% frame fill. This was violated pervasively.

**Root cause:** Two issues compounded:
1. Chart/template components use conservative padding and fixed max-widths, not frame-relative sizing. They were likely designed at desktop scale without considering 1920×1080 video frame economics.
2. Storyboard scene files don't enforce a `screenUtilization` parameter. The production agent has no gate to check whether rendered content actually fills the frame.

**Fix:**
- [ ] Audit ALL chart templates (HorizontalBarChart, BarChart, PieChart, etc.) — replace fixed max-widths with frame-relative widths (≥85% of 1920px = 1632px minimum content width)
- [ ] Add a VB-1 compliance check to the Critic: "Estimate bounding box of visible content. If <80% of frame, fail."
- [ ] Scene detail files should include explicit `layout.width` and `layout.height` percentages

**Status:** Open

---

### RCA-007: Off-Brand Color Usage (Purple, Green, Random Accents)

| Field | Value |
|-------|-------|
| Date | 2026-04-06 |
| Failure Type | `data-error` / `context-loss` |
| Severity | **Critical (P0)** |
| Affected Agent | Storyboard / Production |

**What happened:** User identified multiple off-brand colors:
- Purple (#6C63FF) used as accent — channel has no purple. Brand accents are `#E88CA5` (dusty pink) and `#7BA7C9` (muted blue).
- Green accent in scene 26 — "bizim ne zaman yeşil renk accentimiz oldu?"
- Random glow colors in scene 1 with no rationale.
- Inconsistent section background colors — "kiminde arkaplanda dörtgen yok, kiminde var, kiminde yarısaydam var, kiminde arkaplan kararmış."

**Root cause:** Production agent either didn't read `channel-config.json` / `design-system.json` brand colors, or used hardcoded fallback colors in chart templates. The color palette (`accent1: #E88CA5`, `accent2: #7BA7C9`, `positive: #5BBF8C`, `negative: #E06070`) was not enforced during scene rendering. Template code likely contains hardcoded hex values that bypass the design token system.

**Fix:**
- [ ] Audit every template in `src/remotion/templates/` for hardcoded color values. Replace with design token references.
- [ ] Grep for `#6C63FF` and remove every instance — this is not a channel color.
- [ ] Production agent prompt: "BEFORE rendering, read `design-system.json` and extract the color palette. Only use colors from this palette unless the scene explicitly overrides with a data-driven chromatic scale (VB-2)."
- [ ] Storyboard agent: "Never invent colors. Reference token names (accent1, accent2, positive, negative) in scene files, not hex codes."

**Status:** Open

---

### RCA-008: Bar Chart Proportions and Styling Inconsistencies

| Field | Value |
|-------|-------|
| Date | 2026-04-06 |
| Failure Type | `prompt-gap` |
| Severity | **High (P1)** |
| Affected Agent | Production / Templates |

**What happened:** User reported:
- Bars are too thin ("ince uzun çizgiler gibi") — they fill only ~10% of vertical space with 3-4 items
- Inconsistent border radius: some bars rectangular, some rounded/elliptical ("bi siyah veriyosun bi arkaplanla aynı renkte")
- Text overflow on bars in scene 8 ("yazılar bile taşmış")
- VB-3 proportional sizing violation: scene 6 shows 73 as full bar but 61 as truncated

**Root cause:** Bar chart templates lack proportional thickness calculation relative to available vertical space. With 3-4 items, bar thickness should auto-scale to fill available space. The `borderRadius: 6` standardization was noted as done in feedback annotations, but the underlying proportional sizing issue persists.

**Fix:**
- [ ] HorizontalBarChart template: bar thickness = `(availableHeight / itemCount) * 0.7` with a minimum of 48px
- [ ] Enforce consistent borderRadius across all bar variants via design token (`spacing.cornerRadius: 8` from design-system.json)
- [ ] Add text overflow protection: if label width > bar width, render label outside the bar
- [ ] VB-3 compliance: audit all scenes with comparative bars for proportional accuracy

**Status:** Open

---

### RCA-009: TiltCard Motion Never Used in Any Scene

| Field | Value |
|-------|-------|
| Date | 2026-04-06 |
| Failure Type | `context-loss` |
| Severity | **Medium (P2)** |
| Affected Agent | Storyboard |

**What happened:** User noted "tilt motion'ını hiç kullanmamışsın sanki." TiltCard is a registered L3 motion primitive with a working showcase (DS-TiltCard). It exists in the component catalog. Yet zero scene detail files reference it.

**Root cause:** The storyboard agent didn't consult `component-catalog.json` when assigning visuals to scenes. The catalog explicitly lists TiltCard use cases, but the agent defaulted to basic blur-fade-in for every scene instead of matching visual needs to available primitives.

**Fix:**
- [ ] Storyboard agent prompt: "Read `component-catalog.json` before scene detailing. For each scene, check if any registered motion/surface/atmosphere matches the scene's visual needs better than the default."
- [ ] Specifically assign TiltCard to scenes with stat cards, comparison panels, or hero numbers.

**Status:** Open

---

### RCA-010: Visual Inconsistency Across Scenes — No Unified Visual Language

| Field | Value |
|-------|-------|
| Date | 2026-04-06 |
| Failure Type | `prompt-gap` |
| Severity | **Critical (P0)** |
| Affected Agent | Storyboard / Production |

**What happened:** User: "sahnelerin hepsinde ayrı şey denemişsin. Kiminde arkaplanda dörtgen yok. Kiminde var, kiminde yarısaydam var, kiminde arkaplan kararmış. Neyin peşindesin?" Each scene appears to use a different visual strategy — some have section backgrounds, some don't, some have semi-transparent panels, some darken the background. The video looks like 27 different videos spliced together.

**Root cause:** The storyboard skeleton doesn't enforce a unified visual strategy. `design-system.json` defines `sceneDefaults` per category (hero/data-viz/comparison/etc.) but these defaults were apparently not applied consistently. Individual scene detail files each made independent visual decisions without a global coherence pass.

**Fix:**
- [ ] Define a `visualStrategy` block in the storyboard skeleton that applies to ALL scenes: consistent surface treatment, consistent background approach, consistent accent usage.
- [ ] Storyboard agent: after generating all scene details, run a coherence pass — verify every scene uses the same visual language for the same type of content.
- [ ] Critic checkpoint: "Are all data-viz scenes using the same surface? Are all comparison scenes using the same layout pattern?"

**Status:** Open

---

### RCA-011: Stock Imagery Quality and Integration Issues

| Field | Value |
|-------|-------|
| Date | 2026-04-06 |
| Failure Type | `data-error` / `tooling-issue` |
| Severity | **High (P1)** |
| Affected Agent | Production |

**What happened:** Multiple image-related issues:
- Scene 17-18: "gemini logosu gözüküyo. daha zoom in yapsana" — AI-generated image contains visible branding artifacts
- Scene 19: Chart overlaid on image creates readability conflict — "görselin üzerine grafik koymak ne kadar iyi fikir?"
- Scene 22: "direkt boş" — scene renders with no visible content
- Scene 27: "anlık olarak resim gözüküyo ama yarım saniye bile değil" — image flash so brief it's useless

**Root cause:** 
1. AI image prompts didn't include negative prompts for brand logos/text
2. No validation that image + data overlay combinations are readable
3. Scene timing errors — image display duration miscalculated (scene 27)
4. Missing content detection — scene 22 rendered empty with no error

**Fix:**
- [ ] AI image prompts: always include negative prompt "no text, no logos, no brand names, no watermarks"
- [ ] When scene has both image and chart, use frosted-panel surface as separator (exactly what the user's Glass Calendar intake was meant to enable)
- [ ] Add empty-scene detection: if a rendered frame has <5% non-background pixels, flag as error
- [ ] Fix scene 27 timing: image must be visible for minimum 2 seconds

**Status:** Open

---

## Technical Failures

### RCA-012: SSML/TTS Narrator Reading "PAUSE" Literally

| Field | Value |
|-------|-------|
| Date | 2026-04-06 |
| Failure Type | `tooling-issue` |
| Severity | **High (P1)** — marked as resolved |
| Affected Agent | TTS / Production |

**What happened:** Narrator literally said "PAUSE" out loud instead of pausing. Script contained raw SSML markup that was passed to TTS as text rather than being parsed.

**Root cause:** Script markup format used `{PAUSE:1.0s}` or similar, but the TTS conversion didn't translate these to proper SSML `<break>` tags. The text was sent verbatim to Google TTS.

**Fix:**
- [x] `convertPauseMarkup()` + `escapeForSSML()` functions added
- [x] TTS regenerated — 27/27 blocks error-free
- [ ] Add a TTS pre-flight validation: "Scan output text for non-SSML markup tokens before sending to API. If any found, abort and report."

**Status:** Fixed (narrator issue), Open (pre-flight guard)

---

### RCA-013: Excessive Scene-End Padding / Pauses

| Field | Value |
|-------|-------|
| Date | 2026-04-06 |
| Failure Type | `data-error` |
| Severity | **High (P1)** — partially resolved |
| Affected Agent | Scene Timing / Production |

**What happened:** "Özellikle her sahnenin sonunda anlamsız bir uzunlukta bekleme var." Every scene had dead air at the end. Padding was reduced from an unknown higher value to 1.0s + 0.5s gap, but user indicated it may still be too much.

**Root cause:** Scene timing calculation adds a fixed padding buffer at the end of each scene. With 27 scenes, even 1.5s padding per scene = 40.5 seconds of dead air in a ~600s video (6.75% wasted).

**Fix:**
- [x] Reduced to 1.0s padding + 0.5s gap (from higher values)
- [ ] Further reduction: 0.5s padding + 0.3s gap recommended. Total dead air budget for a 27-scene video should be <20s.
- [ ] Scene timing skill should define max-padding-per-scene as a function of total video length, not a fixed constant.

**Status:** Partially fixed, needs further reduction

---

### RCA-014: Data Accuracy Concern (Scene 11 — Cotton Ranking)

| Field | Value |
|-------|-------|
| Date | 2026-04-06 |
| Failure Type | `data-error` |
| Severity | **High (P1)** |
| Affected Agent | Researcher / Content Writer |

**What happened:** User questioned scene 11: "bundan emin miyiz? cotton daha kötü çıkıyor." The scene visualizes data that suggests cotton has worse health outcomes than expected — which contradicts common knowledge and may indicate a data error or misleading visualization.

**Root cause:** Either:
1. The research data is correct but the visualization lacks context (e.g., organic vs conventional cotton)
2. The data is being visualized incorrectly (wrong metric, wrong axis, inverted scale)
3. The source data itself is unreliable

This was never investigated because no agent verified the claim.

**Fix:**
- [ ] Cross-reference scene 11 data against research-v1.md sources
- [ ] If correct, add contextual explanation (e.g., "conventional cotton — pesticide-treated")
- [ ] If incorrect, fix the data and re-render
- [ ] Add a math-verification pass for all data-viz scenes (load `math-verification` skill)

**Status:** Open

---

## Unresolved Feedback Items

Every feedback item from `feedback.md`, categorized and severity-rated. Items marked ✅ are verified resolved. All others are **open**.

### P0 — Critical (Must fix before any render)

| # | Item | Source | Status | RCA |
|---|------|--------|--------|-----|
| F-01 | Screen utilization <80% across majority of scenes (3-4, 5, 7, 8, 12-14, 16, 25) | General + Scene notes | **OPEN** | RCA-006 |
| F-02 | Off-brand colors: purple #6C63FF accent throughout | General | **PARTIAL** — removed from Root.tsx/PieChart, but may persist in other templates | RCA-007 |
| F-03 | Off-brand green accent in scene 26 | Scene 26 | **OPEN** | RCA-007 |
| F-04 | Mobile-friendliness ("MOBILE FRIENDLY YAP") — everything too small | General | **OPEN** | RCA-006 |
| F-05 | Visual inconsistency across scenes — no unified visual language | Scene 19-24 + General | **OPEN** | RCA-010 |
| F-06 | Glass Calendar external component — not processed through intake gate | Glass Calendar section | **OPEN** | RCA-004 |
| F-07 | Glassmorphism Trust Hero external component — not processed through intake gate | Trust Hero section | **OPEN** | RCA-004 |
| F-08 | Scene 22 is completely blank/empty | Scene 22 | **OPEN** | RCA-011 |

### P1 — High (Must fix before publishing)

| # | Item | Source | Status | RCA |
|---|------|--------|--------|-----|
| F-09 | Bar charts too thin — bars fill ~10% of vertical space with 3-4 items | General | **PARTIAL** — thickness increased but not enough | RCA-008 |
| F-10 | Bar chart borderRadius inconsistency (rectangular vs elliptical) | General | ✅ DONE — standardized to borderRadius: 6 | RCA-008 |
| F-11 | Text overflow on bar charts (scene 8 — yazılar taşmış) | Scene 8 | **OPEN** | RCA-008 |
| F-12 | Scene 6 alignment — labels don't start at same position, 73 full bar but 61 truncated | Scene 6 | **OPEN** | RCA-008 |
| F-13 | TiltCard motion never used in any scene | General | **OPEN** | RCA-009 |
| F-14 | Scene-end pauses still too long (reduced to 1.0s + 0.5s, may need further cut) | General | **PARTIAL** | RCA-013 |
| F-15 | Every data claim needs source attribution overlay | General | ✅ DONE — sourceText added to 27 scenes, citation overlay added | — |
| F-16 | Cotton data accuracy (scene 11) — "bundan emin miyiz?" | Scene 11 | **OPEN** | RCA-014 |
| F-17 | Scene 11 + 15 use circle charts inconsistently ("neden dairelerle ifade ettik?") | Scene 11, 15 | **OPEN** | RCA-010 |
| F-18 | Scene 17-18 AI image has Gemini logo visible, needs zoom/crop | Scene 17-18 | **OPEN** | RCA-011 |
| F-19 | Scene 17-18 artistic direction not fitting channel style | Scene 17-18 | **OPEN** | RCA-010 |
| F-20 | Scene 27 image flash <0.5s — "direkt salaklik" | Scene 27 | **OPEN** | RCA-011 |
| F-21 | FrostedPanelSurface missing showcase (Step 4 of intake) | DS Integrity | **OPEN** | RCA-005 |
| F-22 | CardSurface missing showcase (Step 4 of intake) | DS Integrity | **OPEN** | RCA-005 |
| F-23 | Scene 5 — unnecessary section background color over background | Scene 5 | **OPEN** | RCA-010 |

### P2 — Medium (Should fix, can ship without)

| # | Item | Source | Status | RCA |
|---|------|--------|--------|-----|
| F-24 | Scene 1 glow color choice has no rationale | Scene 1 | **OPEN** | RCA-007 |
| F-25 | Scene 7 — "sıkıcı" presentation, useful area <20% of frame | Scene 7 | **OPEN** | RCA-006 |
| F-26 | Scene 7 — inconsistent section background colors (some black, some match bg) | Scene 7 | **OPEN** | RCA-010 |
| F-27 | Scene 12-13 — accumulation of all visual issues (generic "tüm yorumlar geçerli") | Scene 12-13 | **OPEN** | Multiple |
| F-28 | Scene 14+16 — "iğrenç bar chart", text overflow, poor screen utilization | Scene 14, 16 | **OPEN** | RCA-008 |
| F-29 | Scene 19 — chart overlaid on image creates readability conflict | Scene 19 | **OPEN** | RCA-011 |
| F-30 | Scene 26 should use VerticalTabScene template ("tam yeni VerticalTabScene'i kullanmalıkmış") | Scene 26 | **OPEN** | RCA-009 |

### Resolved Items (for completeness)

| # | Item | Source | Status |
|---|------|--------|--------|
| F-31 | SSML — narrator saying "PAUSE" literally | General | ✅ DONE |
| F-32 | Bar chart borderRadius standardization | General | ✅ DONE |
| F-33 | Source attribution overlays on data scenes | General | ✅ DONE |

**Summary: 30 distinct items identified. 3 resolved. 3 partially resolved. 24 fully open.**

---

## Remediation Plan

Ordered by priority. No render may be initiated until Phase 1 is complete.

### Phase 0 — Immediate (Before any new work on this video)

| # | Action | Addresses | Agent |
|---|--------|-----------|-------|
| R-01 | Process Glass Calendar through External Component Intake gate (Decompose → Adapt → Register → Showcase) | F-06, RCA-004 | Production |
| R-02 | Process Glassmorphism Trust Hero through External Component Intake gate | F-07, RCA-004 | Production |
| R-03 | Create SurfaceShowcase3 for FrostedPanelSurface + CardSurface, register in Root.tsx | F-21, F-22, RCA-005 | Production |
| R-04 | Verify in Remotion Studio that all 4 new/updated surfaces render correctly | R-01 through R-03 | Production |

### Phase 1 — Template Overhaul (Before any scene re-rendering)

| # | Action | Addresses | Agent |
|---|--------|-----------|-------|
| R-05 | Audit ALL chart templates for hardcoded colors. Replace with design token references or props. Grep and kill #6C63FF everywhere. | F-02, F-03, F-24, RCA-007 | Production |
| R-06 | Overhaul screen utilization in ALL chart templates: minimum content width = 85% of frame width. Remove conservative max-widths and excessive padding. | F-01, F-04, F-25, RCA-006 | Production |
| R-07 | Fix bar thickness auto-scaling: `(availableHeight / itemCount) * 0.7`, min 48px | F-09, F-11, F-12, F-28, RCA-008 | Production |
| R-08 | Add text overflow protection to bar charts: if label > bar width, render outside | F-11, RCA-008 | Production |
| R-09 | Define unified `visualStrategy` for this video: consistent surface (frosted-panel recommended), consistent bg approach, consistent accent usage | F-05, F-23, F-26, RCA-010 | Storyboard |

### Phase 2 — Scene-Level Fixes (After template overhaul)

| # | Action | Addresses | Agent |
|---|--------|-----------|-------|
| R-10 | Fix scene 6 alignment: labels start at same x-position, proportional bar widths per VB-3 | F-12 | Production |
| R-11 | Fix scene 8 text overflow | F-11 | Production |
| R-12 | Fix scene 11 data accuracy — cross-reference research, add context or correct | F-16 | Researcher |
| R-13 | Unify chart types: scenes 11+15 should use same chart type as other comparable scenes | F-17 | Storyboard |
| R-14 | Fix scene 17-18: re-prompt AI image without brand logos, crop tighter | F-18, F-19 | Production |
| R-15 | Fix scene 19: use frosted-panel surface between image and chart overlay | F-29 | Production |
| R-16 | Fix scene 22: investigate why it's blank, populate with content | F-08 | Production |
| R-17 | Fix scene 26: apply VerticalTabScene template, remove off-brand green | F-30, F-03 | Storyboard |
| R-18 | Fix scene 27: ensure image displays for minimum 2 seconds | F-20 | Production |
| R-19 | Apply TiltCard motion to appropriate scenes (stat cards, comparisons, hero numbers) | F-13 | Storyboard |
| R-20 | Reduce scene-end padding to 0.5s + 0.3s gap | F-14 | Production |

### Phase 3 — Process Improvements (Prevent recurrence)

| # | Action | Addresses | Agent | Requires User Approval |
|---|--------|-----------|-------|----------------------|
| R-21 | Add negative-feedback detection gate to Director agent prompt | RCA-001 | QA → Director | **Yes** (prompt change) |
| R-22 | Add pre-render checklist gate to Director agent prompt | RCA-002 | QA → Director | **Yes** (prompt change) |
| R-23 | Create feedback tracking protocol for Director | RCA-003 | QA → Director | **Yes** (new protocol) |
| R-24 | Add auto-trigger for External Component Intake in Director prompt | RCA-004 | QA → Director | **Yes** (prompt change) |
| R-25 | Add TTS pre-flight validation (scan for non-SSML markup tokens) | RCA-012 | QA → TTS | **Yes** (tooling change) |
| R-26 | Add VB-1 compliance check to Critic | RCA-006 | QA → Critic | **Yes** (prompt change) |
| R-27 | Add empty-scene detection to render pipeline | RCA-011 | QA → Production | **Yes** (tooling change) |

### Render Gate

**DO NOT render until:**
1. All Phase 0 items complete (DS components available)
2. All Phase 1 items complete (templates fixed)
3. All Phase 2 items complete (scenes fixed)
4. User explicitly approves render with knowledge of what changed

**Estimated effort:** Phase 0 (2-3 hours), Phase 1 (3-4 hours), Phase 2 (2-3 hours), Phase 3 (1-2 hours for proposals).

---

*This QA log was generated retroactively. The fact that it had to be retroactive is itself the primary finding — QA should have been invoked at the first frustrated user message.*
