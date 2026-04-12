# QA Report — fabric-health-comparison

> Executive summary. Full details in [`qa-log.md`](qa-log.md).

| Field | Value |
|-------|-------|
| Date | 2026-04-06 |
| Project | fabric-health-comparison |
| Channel | the-world-with-numbers |
| Audit Type | Full retroactive audit |
| Verdict | **FAIL — video is not publishable** |

---

## What Happened

The video went through research → script → storyboard → TTS → render without a single quality gate catching systemic visual and process failures. The user provided detailed, escalating feedback across multiple sessions. None of it triggered the QA loop. A 30-minute render was executed with 24+ unresolved items.

## By the Numbers

| Metric | Value |
|--------|-------|
| Total feedback items identified | 30 |
| Resolved | 3 (10%) |
| Partially resolved | 3 (10%) |
| **Fully open** | **24 (80%)** |
| P0 (Critical) items open | 8 |
| P1 (High) items open | 12 |
| P2 (Medium) items open | 7 |
| RCA entries logged | 14 |
| External components awaiting intake | 2 |
| DS surfaces missing showcases | 2 |

## Root Cause Categories

### 1. Director Process Failures (5 RCAs)
- QA never invoked despite repeated user frustration — the single biggest process failure
- Render launched without user approval and with unresolved feedback
- Feedback file never tracked systematically
- Two user-provided external components completely ignored
- Two DS surfaces created without completing the mandatory 4-step intake gate

### 2. Visual / Design Failures (6 RCAs)
- Screen utilization chronically below the 80% minimum (VB-1 violation) — affects >50% of scenes
- Off-brand colors (purple, green) used despite defined brand palette in design-system.json
- Bar charts too thin, inconsistent styling, text overflow
- No unified visual language — 27 scenes look like 27 different videos
- TiltCard motion primitive exists but was never assigned to any scene
- Stock imagery issues: AI branding artifacts, image flashes <0.5s, one completely blank scene

### 3. Technical Failures (3 RCAs)
- SSML parser bug caused narrator to say "PAUSE" literally (fixed)
- Scene-end padding adds ~40s of dead air across the video (partially fixed)
- Data accuracy concern on cotton health ranking unverified

## Top 5 Actions (Priority Order)

1. **Process the 2 external components** (Glass Calendar, Glassmorphism Trust Hero) through the full External Component Intake gate — the user explicitly requested this.
2. **Overhaul chart templates** — screen utilization ≥85%, kill hardcoded colors, fix bar thickness auto-scaling.
3. **Define unified visual strategy** for the video — one surface treatment, one background approach, one accent pattern.
4. **Fix scene-specific bugs** — blank scene 22, flash scene 27, off-brand scene 26, misaligned scene 6.
5. **Propose Director prompt updates** to prevent recurrence — negative-feedback gate, pre-render checklist, feedback tracking protocol.

## Render Gate

No render until all P0 items resolved and user explicitly approves. The previous render was a waste of 30 minutes because this gate didn't exist.

## Process Recommendation

The Director agent prompt needs 4 specific additions (R-21 through R-24 in qa-log.md). These are prompt changes that require user approval. The QA agent has drafted them; the Director should present them at the next session start.

---

*Audit conducted retroactively by QA agent. This audit should have happened at the first "çok kötü" — not after a render.*
