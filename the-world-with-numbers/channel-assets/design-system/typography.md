# Typography — The World With Numbers DS v6

> Source of truth: `channel-assets/design-system.json → tokens.typography`
> Runtime: `src/fonts/font-registry.ts` + `load-fonts.ts`

## Two-Family System

| CSS Variable | Font | Weights | Notes |
|:-------------|:-----|:--------|:------|
| `--font-heading` | Montserrat | 600–800 | Titles, hooks |
| `--font-number` | Montserrat | 600–800 | All data values, counters (alias — same font as heading) |
| `--font-body` | Inter | 400–500 | Body copy, subtitles, labels, citations |
| `--font-mono` | JetBrains Mono | — | **Docs/code only — NOT used in video** |

JetBrains Mono removed from video (Burak, 2026-04-17). Montserrat handles tabular-nums natively.

## Type Scale — The Hierarchy

| Level | CSS Variable | Size | Font | Weight Variable | Weight |
|:------|:-------------|:-----|:-----|:----------------|:-------|
| **Hero** | `--size-hero` | 160px | Montserrat | `--weight-heading-max` | 800 |
| **H1** | `--size-h1` | 64px | Montserrat | `--weight-heading-max` | 800 |
| **H2** | `--size-h2` | 52px | Montserrat | `--weight-heading` | 700 |
| **H3** | `--size-h3` | 40px | Montserrat | `--weight-heading-mid` | 600 |
| **Body LG** | `--size-body-lg` | 36px | Inter | `--weight-body` | 400 |
| **Body** | `--size-body` | 32px | Inter | `--weight-body` | 400 |
| **Label** | `--size-label` | 24px | Inter | `--weight-body-emph` | 500 |
| **Cite** | `--size-cite` | 22px | Inter | `--weight-body` | 400 |
| **Floor** | `--size-floor` | 20px | — | — | **Absolute minimum. Never go below.** |

Also: `--weight-black: 900` (available but rarely used).

Hard floor: **20px**. If text can't fit at 20px, the layout is wrong — shrink the content, not the type.

## Spacing & Style

| CSS Variable | Headings | Body | Numbers |
|:-------------|:---------|:-----|:--------|
| `--lh-heading` / `--lh-body` | 1.15 | 1.55 | 1.0–1.2 |
| `--ls-heading` / `--ls-body` / `--ls-number` | -0.02em | 0 | -0.01em |
| text-transform | none | none | none (uppercase only for 11px labels) |
| color | `var(--text)` | `var(--text)` or `var(--text-secondary)` | `var(--text)` or accent when data |

## Tabular Numerals — Mandatory

Every number element MUST use:
```css
font-family: "Montserrat", sans-serif;
font-feature-settings: "tnum" 1, "lnum" 1;
font-variant-numeric: tabular-nums lining-nums;
```

Non-tabular numbers shift width during counter animations and make ranked lists stagger — instant amateur signal.

## Enforcement

- **JSON**: `design-system.json → tokens.typography`
- **Runtime**: `src/fonts/font-registry.ts` + `load-fonts.ts` loads fonts into Remotion
- **Critic check**: VB-4 font-size floor (20px) is a hard FAIL criterion
