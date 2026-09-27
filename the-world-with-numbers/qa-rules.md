# QA Rules: The World With Numbers

Channel-specific visual pitfalls learned in production. Process rules (stages, approvals, TTS, timing, regression checks, fix loop) are owned by the framework: `yt-pipeline/AGENTS.md` and its skills. Do not restate them here.

Rewritten 26.09.2026: PR-01 to PR-07, LP-03, LP-04 and ET-01 to ET-03 moved into the framework (hooks, scripts, `fix`/`produce`/`storyboard` skills, AGENTS.md "Learning from the user").

## Visual pitfalls

### LP-01: Animated chart start frames look empty
Charts that animate in from zero show a blank or near-blank first frame. Check a mid-animation frame (40 to 60% into the scene), not only the start.
> Source: 5-chokepoints scene-002 was ~95% empty in a still check

### LP-02: Black frames from missing assets
A scene that references a missing visual asset renders black. Every asset path in a visual file must exist before previewing.
> Source: 5-chokepoints scene-009 completely black

### LP-05: Hex codes in code do not match the design system
Near-miss colors (`#1a1a2e` instead of `#1B1F3B`) are the most common visual inconsistency. Colors come from the design tokens only.
> Source: multiple color corrections across all videos

### LP-06: Safe zone violations with long text
Title scenes with long text overflow the safe zone. Test with the real script text, never placeholder text.
> Source: text truncation in multiple test renders
