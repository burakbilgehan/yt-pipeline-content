# Pre-Render Checklist — The World With Numbers DS

Every FAIL wastes 40+ minutes of compute. Run before every render.

## A. Content & Data (4 checks — manual)

- [ ] Every data scene has a real, verifiable citation (full org + year + URL). No "Source: internet" placeholders.
- [ ] Numbers cross-checked against the primary source. Secondary aggregators (Statista wrapping another report) don't count.
- [ ] Ranking ordering matches the data, not the narrative. If re-ordered for storytelling, annotate — never silently.
- [ ] All dates/units/currencies normalized and labelled. "$" = USD nominal unless declared otherwise.

## B. Tokens & Imports (5 checks — grep)

- [ ] No hex codes in source: `grep -rE "#[0-9a-fA-F]{3,6}" src/remotion/scenes` returns nothing.
- [ ] No inline `fontSize: NN`. All via type tokens. Grep for `fontSize:\s*[0-9]`.
- [ ] All spacing is a multiple of 8px. No 14, 18, 22, 30, 42px values.
- [ ] `npm run sync-palette` ran after any `design-system.json` edit. `palette.ts` regenerated; commit both.
- [ ] Fonts loaded via `loadFonts()` before first frame. Missing = silent system-font fallback.

## C. Visual Rules VB-1..7 (8 checks — critic agent)

- [ ] VB-1: Every scene ≥ 85% frame utilization (OpeningScene + ClosingScene excepted).
- [ ] VB-2: Value-to-color mapping is proportional, never binary. `interpolateColors()` used.
- [ ] VB-3: Bars share one baseline scale; no fake normalization. Corner radius = 0.
- [ ] VB-4: No text below 20px anywhere (including axis labels, citations, footnotes).
- [ ] VB-5: Gridlines ≤ 10% opacity. No decorative bars or shapes.
- [ ] VB-4+: Every number element has `font-variant-numeric: tabular-nums`.
- [ ] VB-6: Entrances complete by 30% of scene duration. Stagger ≤ 2s. No linear easing.
- [ ] VB-7: Template name reflects data shape, not topic.

## D. Layout Contracts LC-1..6 (6 checks — critic agent)

- [ ] LC-1: Titles anchor bottom-left (OpeningScene exception documented).
- [ ] LC-2: Citations anchor bottom-right on every data scene.
- [ ] LC-3: Hero numbers centered; no competing focal element at same y-position.
- [ ] LC-4: Chart canvas right 72%, title column left 24%.
- [ ] LC-5: Duels are 50/50 vertical split with proportional bar at base.
- [ ] LC-6: Ranked lists: rank-label-bar-value columns, 10f stagger.

## E. Render & Output (4 checks — pre-flight)

- [ ] Composition: 1920×1080 @ 30fps.
- [ ] Audio waveform skimmed for clips/pops.
- [ ] Thumbnail exported separately — not a frame grab.
- [ ] Critic agent run, PASS on every scene. Any FAIL blocks render.

## When a Check Fails

- **Do not patch at the scene level.** If 3 scenes fail VB-1, the template is wrong — fix the template once.
- **Never disable a critic rule to ship.** Document a named exception in `DESIGN-SYSTEM.md` or redesign the scene.
