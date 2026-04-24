# Colors — The World With Numbers DS v6

> Source of truth: `channel-assets/design-system.json`
> Runtime import: `src/remotion/palette.ts` (auto-generated via `npm run sync-palette`)

## The Seven Tokens

| Token | Name | Hex | Role |
|:------|:-----|:----|:-----|
| `--bg` | Deep Base | `#2A2A32` | Background — solid, no gradient |
| `--text` | Warm Cream | `#F0EDE8` | All readable text — never `#FFF` |
| `--accent-pink` | Accent Pink | `#E88CA5` | Data Set A, highlights, logo mark |
| `--accent-blue` | Accent Blue | `#7BA7C9` | Data Set B, comparative/stable |
| `--positive` | Positive | `#5BBF8C` | Growth, upward trend |
| `--negative` | Negative | `#E06070` | Decline, downward trend |
| `--surface` | Surface | `#2E2E38` | Cards/panels (near-bg, border separates) |

## Text Opacity Tokens

| Token | Value | Use |
|:------|:------|:----|
| `--text` | `#F0EDE8` (100%) | Primary text, headings |
| `--text-secondary` | `rgba(240,237,232, 0.70)` | Body copy, descriptions |
| `--text-muted` | `rgba(240,237,232, 0.55)` | Citations, secondary labels |
| `--text-faint` | `rgba(240,237,232, 0.35)` | Axis labels, footnotes |

## Surface & Card Tokens

| Token | Value | Role |
|:------|:------|:-----|
| `--surface` | `#2E2E38` | Card/panel bg (1 step lighter than --bg) |
| `--surface-hover` | `#313140` | Hover state |
| `--card-bg` | `#2E2E38` | Alias for surface |
| `--card-border` | `rgba(240,237,232, 0.10)` | Card edge separation |

## Structural Colors

| Token | Value | Role |
|:------|:------|:-----|
| `--grid` | `rgba(240,237,232, 0.08)` | Chart gridlines |
| `--axis` | `rgba(240,237,232, 0.35)` | Axis labels, tick marks |
| `--track` | `rgba(240,237,232, 0.06)` | Bar track background |
| `--border-strong` | `rgba(240,237,232, 0.12)` | Dividers |
| `--border-subtle` | `rgba(240,237,232, 0.07)` | Subtle borders |
| `--border-width` | `1px` | Standard border width |

## Multi-series Ordered Palette (>2 series — avoid if possible)

`--data-1` through `--data-8`: Pink → Blue → Positive → Negative → `#7EC8E3` → `#F4A261` → `#C084FC` → `#FB923C`

## Absolute Rules

- **Max 2 data colors per chart.** Pink + Blue. Never add a third vivid color.
- **Sage removed (v6).** `#8A9A7A` is gone. Grid = `rgba(240,237,232,0.08)`, axis = `rgba(240,237,232,0.35)`.
- **No `#FFF`. Ever.** All text uses Warm Cream `#F0EDE8`.
- **No gradient text. No gradient backgrounds.** Background is solid `#2A2A32`.
- **Never hardcode hex in code.** Import from `src/remotion/palette.ts`.

## Color Role Map

| Scenario | Colors |
|:---------|:-------|
| Duel / 2-series | Pink + Blue |
| Value vs baseline | Pink (data) + grid-opacity (baseline) |
| Up / Down trend | Positive + Negative |
| Forced 3+ series | Ordered `--data-1..8` — avoid if possible |

## VB-2: Chromatic Scale Rule

When values represent a spectrum (cheap→expensive, short→long), colors **interpolate proportionally**. Never binary. A value at 30% of range gets a color 30% between `--negative` and `--positive`. Implementation: normalize to 0–1 range, use Remotion's `interpolateColors()`.
