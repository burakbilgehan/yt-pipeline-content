# The World With Numbers — Design System v6

> Source of truth: `channel-assets/design-system.json`
> Runtime: `yt-pipeline/src/remotion/`
> Tokens: 7 colors · 2 fonts · 8-point spacing grid

This directory is a **readable reference** for agents, not the source of truth. Token values come from `design-system.json`. When a value changes, update the JSON first, then `npm run sync-palette`.

## Files

| File | What it covers |
|:-----|:---------------|
| `colors.md` | 7 brand tokens, text opacity, surface/card, structural colors, data palette, color rules |
| `typography.md` | 2-family system (Montserrat + Inter), type scale, weight/spacing tokens, tabular-nums |
| `visual-rules.md` | VB-1..7: screen utilization, chromatic scale, bar truth, type floor, data-ink, animation budget, genericity |
| `templates.md` | L2 primitives (8), L3 scene templates (18), data-shape → template decision tree |
| `layout-contracts.md` | LC-1..6: title anchor, citation anchor, hero number, chart canvas, duel split, ranked list, 8pt grid |
| `agent-contracts.md` | Storyboard/scene/critic/data agent rules, shared preamble, handoff contract |
| `checklist.md` | 27-point pre-render gate (content, tokens, VB, LC, render checks) |

## Scene Category Defaults

From `design-system.json → sceneDefaults`. Storyboard agent assigns these by default — override only with justification.

| Category | Atmosphere | Surface | Motion | Notes |
|:---------|:-----------|:--------|:-------|:------|
| **hero** | dot-grid | flat | blur-fade-in | Hook titles, clean background, single accent element |
| **data-viz** | dot-grid | glass | blur-fade-in | Chart 60–70% of frame, title top-left, source bottom-right |
| **comparison** | dot-grid | glass | blur-fade-in | Side-by-side equal weight, 1px divider |
| **list** | dot-grid | flat | blur-fade-in | Max 6–8 items, 10f stagger, horizontal bars behind values |
| **narrative** | film-grain | none | blur-fade-in | Centered key stat or quote, optional 15% bg visual |
| **cta** | dot-grid | glow | blur-fade-in | Minimal: channel + subscribe + accent underline only |

## Brand at a Glance

- **Tone:** Precise · Curious · Understated · Authoritative · Atmospheric
- **Not:** No hype. No red clickbait arrows. No emoji. No gradient text. No glow effects. No pure white. No host persona.
- **Dramatic device:** The numbers are the drama. Typography and silence do the heavy lifting.

Full brand identity: `channel-assets/brand-identity.md`
Visual brand guide: `channel-assets/brand-guide.md`
