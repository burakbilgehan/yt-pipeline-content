# QA Rules — The World With Numbers

Living document. Director reads at session start, updates when friction signals are detected.
Contains ONLY process rules + learned pitfalls. Does NOT duplicate brand-guide or DS docs.

---

## Process Rules

### PR-01: BGM is mandatory
Every video MUST have background music in `production/audio/bgm/` before upload. preflight script enforces this. Storyboard must include `backgroundMusic` config.
> Source: 5-chokepoints BGM-missing bug caught post-upload

### PR-02: Contact sheet before "done"
VP agent must generate and review contact-sheet.html before reporting completion. No exceptions.
> Source: fabric-health 98 test renders — agent took stills but never self-assessed holistically

### PR-03: Never run full render from agent
Only user runs `npm run render`. Agent provides the command. `remotion still` and `npm run preview` are fine.
> Source: Multiple long-running render failures in production sessions

### PR-04: preflight before upload
Always run `npm run preflight <slug>` before presenting upload command. All gates must pass.
> Source: Multiple post-upload issues (missing BGM, missing thumbnail)

### PR-05: Read channel DS docs before writing composition code
VP must read at minimum: README.md, colors.md, typography.md, visual-rules.md, templates.md, layout-contracts.md, agent-contracts.md from channel DS before any Remotion coding.
> Source: Repeated brand-inconsistent renders requiring multiple fix cycles

### PR-06: One version at a time
Never create a new version of a file without updating `activePath` in config.json first. Never allow two active files for the same stage.
> Source: Version confusion on time-vs-earnings (script-v6, storyboard-v5)

### PR-07: Validate storyboard timing before TTS
Run timing math check (total seconds = sum of scene durations, matches target length ±5%) before generating TTS audio.
> Source: Multiple TTS regenerations due to timing mismatches discovered post-generation

---

## Learned Pitfalls

### LP-01: Animated chart start frames look empty
Charts that animate in from zero show blank/near-blank on frame 0. When taking test stills, always check a mid-animation frame (e.g., 40-60% through the scene), not just the start.
> Source: 5-chokepoints scene-002 was ~95% empty in still check

### LP-02: Black frames from missing assets
If a scene references a visual asset that doesn't exist, Remotion renders a black frame. VP Katman 0 must `ls` every asset path before generating any stills.
> Source: 5-chokepoints scene-009 completely black

### LP-03: Scene iteration death spiral
If a single scene takes >3 fix attempts, STOP. Re-read the storyboard + DS template for that scene type. The approach is likely wrong, not the tweaks.
> Source: fabric-health scene-002 went through 8+ iterations

### LP-04: TTS generates but audio manifest not checked
After TTS generation, always read `audio-manifest.json` and verify: all scenes have audio, durations are within ±10% of target, no zero-length files.
> Source: Silent scenes discovered during render, requiring full TTS regeneration

### LP-05: Hex codes in code don't match DS
Easy to type `#1a1a2e` when DS says `#1B1F3B`. VP Katman 0 grep catches this, but it's the #1 visual inconsistency source.
> Source: Multiple color corrections across all videos

### LP-06: Safe zone violations with long text
Title scenes with long text frequently overflow the safe zone. Always test with the actual text from the script, not placeholder text.
> Source: Text truncation found in multiple test renders

---

## Escalation Triggers

### ET-01: Same pitfall hits 3rd time → create a script
If a learned pitfall occurs a 3rd time despite being documented here, it needs a validation script (like preflight) not just a rule.

### ET-02: User anger on visual issue → update DS checklist
If Burak is frustrated about a visual quality issue, the channel DS `checklist.md` likely needs a new check item.

### ET-03: New scene type not in templates → update templates.md
If storyboard uses a scene type not covered by DS `templates.md`, add the template spec before VP starts coding.
