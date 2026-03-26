# Storyboard v1: Time vs Earnings

> Version: storyboard-v1
> Based on: script-v1 (v2)
> Date: 2026-03-21
> Total scenes: 14
> Total duration: ~12:30 (750s)
> Resolution: 1920×1080, 30fps

---

## Scene 1: The Hook — Salary Shuffle
- **Time:** 0:00 – 0:30
- **Section:** Hook
- **Voiceover excerpt:** "The average American earns eighty-two thousand nine hundred thirty-three dollars a year..."
- **Visual:** Black screen (#1A1B22). "$82,933" fades in center-screen in large Montserrat Bold (#EAE0D5). After 1s, a USA flag + label appears beside it. Then Germany ($69,433), Denmark ($74,022), Japan ($49,446) stack below — each sliding in with flag. After "the German worker gets more for every hour," the numbers animate: a new column "BM/hr" appears, numbers re-sort. Germany rises, Japan rises, USA drops relatively. The visual tension between "paper salary" and "real value" is immediately visible.
- **Animation:** Staggered fade-ins (0.3s apart), then spring-animated re-sort at ~frame 60. Numbers glow briefly as they move.
- **Component:** Custom — `SalaryShuffleScene` (new, text + flag + spring re-sort)
- **Transition:** Crossfade to Scene 2
- **Assets needed:** Country flag icons (USA, Germany, Denmark, Japan) — SVG or emoji
- **Colors:** Text #EAE0D5, highlight accent #D8A7B1 for the "twist" moment

---

## Scene 2: The Salary Illusion — $3,000 Split Screen
- **Time:** 0:30 – 2:15
- **Section:** Phase 1 — The Salary Illusion
- **Voiceover excerpt:** "Three thousand dollars a month..."
- **Visual:** Split screen. Left: "$3,000" stack of bills (stylized illustration or stock). Right side splits into two vertical panels — top: Zurich skyline silhouette with prices floating in (rent: $2,800, groceries: $600). Bottom: Mexico City silhouette with lower prices (rent: $400, groceries: $150). The cash stack visually "shrinks" in Zurich (scale animation) and "grows" in Mexico City. Then transition to three horizontal bars: USA $82,933 / Germany $69,433 / Mexico $20,433 — labeled "PPP-Adjusted Wages."
- **Animation:** Cash stack scale tween (1.0 → 0.3 for Zurich, 1.0 → 2.5 for Mexico). Bars slide in from left with spring easing.
- **Component:** Custom — `SplitComparisonScene` + `BarChart` for the PPP wage bars
- **Transition:** Cut to Scene 3
- **Assets needed:** Zurich/Mexico City skyline silhouettes (AI-generated or stock), stylized cash illustration
- **Colors:** BG #1A1B22, bars use country-specific tints

---

## Scene 3: The Big Mac Lens — Price Tags
- **Time:** 2:15 – 3:20
- **Section:** Phase 1 — The Big Mac Lens (part 1)
- **Voiceover excerpt:** "This is where the Big Mac comes in..."
- **Visual:** Center: photorealistic Big Mac (AI-generated, dark moody lighting matching channel aesthetic). Price tags pop up radially around it: USA $5.79, Japan $3.11, Switzerland $7.99, Euro area $5.95. Tags appear one by one with spring bounce. Then the Big Mac shrinks to corner and prices morph into a horizontal bar chart sorted by price.
- **Animation:** Big Mac fade-in (0.5s), price tags spring in (staggered 0.2s), bar chart morph (1s smooth transition)
- **Component:** Custom intro → `BarChart` for price comparison
- **Transition:** Morph into Scene 4
- **Assets needed:** Big Mac image (AI-generated, dark bg, editorial style — use `npm run generate-image`)
- **Colors:** Price tags in #EAE0D5, bar fills by quadrant color of each country

---

## Scene 4: The Ranking Re-Sort — Switzerland Falls, Japan Rises
- **Time:** 3:20 – 4:30
- **Section:** Phase 1 — The Big Mac Lens (part 2)
- **Voiceover excerpt:** "Switzerland has the second-highest PPP-adjusted wage..."
- **Visual:** Two-column animated ranking. Left column: "PPP Wage Rank" (Luxembourg #1, Switzerland #2, USA #3... Japan mid-pack). Right column appears: "Big Macs/hr Rank." Countries slide and re-sort. Switzerland drops from #2 → #15 with a dramatic red downward trail. Japan jumps from mid-pack → #2 with a green upward trail. Luxembourg stays #1 (subtle gold glow). Each country shows its BM/hr value next to the rank.
- **Animation:** Spring-animated position changes. Switzerland gets a slow-motion spotlight as it drops. Japan gets ascending spotlight. Delay between the two moments for narrative impact.
- **Component:** Custom — `RankingResortScene` (animated rank list with trail effects)
- **Transition:** Morph bar chart into Y-axis of Scene 5
- **Colors:** Downward = #E06070 (negative), Upward = #5BBF8C (positive), Neutral = #EAE0D5

---

## Scene 5: Adding Time — The Matrix Appears
- **Time:** 4:30 – 5:45
- **Section:** Phase 1→2 Transition — Adding Time
- **Voiceover excerpt:** "But there's a second variable that changes everything..."
- **Visual:** The Big Macs/hr bar chart from Scene 4 rotates 90° to become the Y-axis of a scatter plot. A second axis (Annual Hours Worked) extends horizontally from left. Grid lines fade in. Dashed crosshairs appear at the OECD average origin (1,751 hrs, 6.61 BM/hr) with "OECD AVG" label. Quadrant background fills fade in: DREAM (green tint, top-left), GRIND (pink tint, top-right), CHILL (blue tint, bottom-left), TRAP (red tint, bottom-right). Watermark-style quadrant names appear.
- **Animation:** Bar-to-axis rotation (1.5s morph). Grid fade-in (0.5s). Crosshair draw-in (0.8s). Quadrant fills fade (0.5s). Quadrant labels fade (0.3s).
- **Component:** `QuadrantScatter` — initial state with grid/axes/quadrants visible but NO data points yet
- **Transition:** Seamless — dots begin appearing in Scene 6
- **Notes:** This is the "big reveal" moment. The matrix should feel like it's being constructed before the viewer's eyes. Music/sound cue: subtle low tone as the matrix materializes.

---

## Scene 6: DREAM Quadrant — The Lucky 16
- **Time:** 5:45 – 7:00
- **Section:** Phase 2 — The Dream Quadrant
- **Voiceover excerpt:** "Top left. The DREAM quadrant..."
- **Visual:** DREAM quadrant background brightens slightly. Countries appear one by one with spring animation (staggered): Luxembourg first (largest dot, pulsing), then Germany, Denmark (highlighted dots with connector labels). Counter in corner: "16 of 33 countries." Then a zoom-in callout for Japan: flag icon, wage ($49,446), Big Mac price ($3.11), result (9.89 BM/hr), rank badge "#2" — all in a floating card panel. Remaining DREAM countries (Netherlands, Norway, Canada, Austria, Belgium, Sweden, Australia, UK, France, Finland) fade in as a cluster of smaller dots.
- **Animation:** Dot entrance: spring with stagger (1.5 frames apart). Spotlight dots glow. Japan callout: slide-in card from right side. Cluster dots: simultaneous gentle fade-in.
- **Component:** `QuadrantScatter` (DREAM dots active) + custom overlay card for Japan spotlight
- **Transition:** Cross-dissolve — DREAM dims slightly, GRIND brightens
- **Colors:** DREAM dots #5BBF8C, Japan callout card bg rgba(91,191,140,0.15) border #5BBF8C

---

## Scene 7: GRIND Quadrant — The Lonely Two
- **Time:** 7:00 – 7:45
- **Section:** Phase 2 — The Grind Quadrant (intro)
- **Voiceover excerpt:** "Top right. The GRIND... Only two countries..."
- **Visual:** GRIND quadrant brightens. Only 2 dots appear — USA and South Korea. The emptiness is the visual story. A counter shows "2 of 33" with subtle emphasis. Camera slightly zooms into the GRIND quadrant to emphasize how lonely it is.
- **Animation:** USA dot appears with strong spring + glow. South Korea appears 1s later, smaller. "2 of 33" counter fades in bottom-right of quadrant.
- **Component:** `QuadrantScatter` (GRIND dots active)
- **Transition:** Seamless into Scene 8 (comparison overlay appears)

---

## Scene 8: USA vs Denmark — The 439-Hour Question
- **Time:** 7:45 – 9:15
- **Section:** Phase 2 — The Grind Quadrant (USA vs Denmark deep-dive)
- **Voiceover excerpt:** "The United States earns seven point nine one Big Macs per hour..."
- **Visual:** USA dot enlarges, Denmark dot in DREAM quadrant also enlarges. A dashed line connects them across the matrix. Side panel slides in from right: comparison card — USA (7.91 BM/hr, 1,810 hrs, 14,317 BM/yr) vs Denmark (9.83 BM/hr, 1,371 hrs, 13,477 BM/yr). Then the killer visual: a 12-month calendar grid appears below the matrix. 55 days highlighted in #E06070 (red). Label: "55 extra 8-hour workdays." Then: "≈ 11 extra work weeks." Then the punchline appears: "For 6% more."
- **Animation:** Connector line draws from USA → Denmark (1s). Comparison card slides in (spring). Calendar grid builds row by row (0.5s). Red days highlight with pulse. Text labels fade in sequentially with dramatic pauses.
- **Component:** `QuadrantScatter` (background) + custom `ComparisonOverlay` + custom `CalendarGrid`
- **Transition:** Overlay fades, South Korea gets a brief label, then crossfade to CHILL
- **Colors:** Connector line #D8A7B1 dashed. Calendar red days #E06070. "6% more" text #D8A7B1

---

## Scene 9: CHILL Quadrant — The Southern/Eastern Squeeze
- **Time:** 9:15 – 10:15
- **Section:** Phase 2 — The Chill Quadrant
- **Voiceover excerpt:** "Bottom left. The CHILL quadrant..."
- **Visual:** CHILL quadrant brightens. 9 country dots appear (staggered). Italy dot pulses — callout: "5.06 BM/hr | Wages stagnant 25 years." Then Portugal spotlight: a mini diagram shows Portugal wage ($40,002) → divided by Euro-area Big Mac ($5.95) → 4.11 BM/hr. Next to it, Hungary: wage ($34,996) → divided by local Big Mac ($3.65) → 5.64 BM/hr. An arrow or ">" symbol shows Hungary > Portugal despite lower wages. Label: "Shared currency, shared prices — but not shared wages."
- **Animation:** Dot cluster entrance (spring stagger). Italy callout fade-in. Portugal/Hungary comparison: division animations (numbers shrink into result). Greater-than reveal with spring bounce.
- **Component:** `QuadrantScatter` (CHILL dots active) + custom `DivisionComparison` overlay
- **Transition:** Crossfade — CHILL dims, TRAP brightens
- **Colors:** CHILL dots #90AFC5, Italy callout border #90AFC5, Portugal/Hungary comparison uses #E06070 for Portugal result, #5BBF8C for Hungary result

---

## Scene 10: TRAP Quadrant — Greece & Mexico
- **Time:** 10:15 – 11:30
- **Section:** Phase 2 — The Trap Quadrant
- **Voiceover excerpt:** "Bottom right. The TRAP..."
- **Visual:** TRAP quadrant brightens. 6 dots appear — Greece and Mexico at the extreme edges pulse strongly. Germany dot in DREAM also re-highlights for comparison. A connector line draws from Greece → Germany with stats: "3× more BM/hr, 546 fewer hours." Then Germany → Mexico connector: "4.4× more BM/hr, 40% fewer hours." Annual totals appear: Germany 11,671 | Greece 5,432 | Mexico 4,452. Israel gets a brief callout: "Tech hub, but 6.14 BM/hr" with a subtle "?" icon.
- **Animation:** Extreme dots pulse with outer ring. Connector lines draw with number labels appearing at midpoint. Annual totals stack vertically with bar proportions. Israel callout fades in last.
- **Component:** `QuadrantScatter` (all dots now visible, TRAP spotlighted) + comparison connector overlays
- **Transition:** Smooth — full matrix visible, overlays fade out
- **Colors:** TRAP dots #E06070, connector lines #E06070 (dashed), annual total bars proportional fill

---

## Scene 11: Data Disclaimer
- **Time:** 11:30 – 11:45
- **Section:** Data Source Attribution
- **Voiceover excerpt:** "A note on the data..."
- **Visual:** Full QuadrantScatter matrix in background (slightly dimmed). Lower-third overlay slides up with clean source text: "OECD Average Wages 2024 (PPP) · OECD Hours Worked 2022 · Big Mac Index Jan 2025 · The Economist." Second line: "Euro-area countries share a single Big Mac price ($5.95)."
- **Animation:** Lower-third slide-up (0.5s), text fade-in. Background dims to 60% opacity.
- **Component:** `QuadrantScatter` (dimmed) + custom lower-third overlay
- **Transition:** Lower-third slides down, matrix brightens
- **Colors:** Lower-third bg rgba(26,27,34,0.85), text #EAE0D5, source links #90AFC5

---

## Scene 12: Closing — The Full Matrix
- **Time:** 11:45 – 12:05
- **Section:** Closing Thought (part 1)
- **Voiceover excerpt:** "Thirty-three countries. Two axes. Four quadrants..."
- **Visual:** Full QuadrantScatter at 100% — all 33 dots visible, all quadrant labels, all spotlight labels. This is the "hero shot" — the complete picture the viewer has been building toward for 12 minutes. Brief wide-angle hold for 2-3 seconds to let it breathe.
- **Animation:** All elements at full opacity. Subtle ambient pulse on dots (very slow, 0.5% scale oscillation). Camera holds steady.
- **Component:** `QuadrantScatter` (full state)
- **Transition:** Slow zoom begins toward USA-Denmark gap

---

## Scene 13: Closing — The Gap Between USA and Denmark
- **Time:** 12:05 – 12:25
- **Section:** Closing Thought (part 2)
- **Voiceover excerpt:** "An American worker and a Danish worker end the year with roughly the same number of Big Macs..."
- **Visual:** Camera slowly zooms into the space between USA (GRIND) and Denmark (DREAM). Other dots fade to 20% opacity. The connector line between USA and Denmark reappears. The gap is labeled: "439 hours | 55 days | 6%." As voiceover continues, the numbers "439 hours" and "55 days" pulse. Then Greece and Mexico flash briefly in TRAP. The final line: "What is an hour of your life worth?" appears as subtle text below the matrix.
- **Animation:** Slow zoom (15s, smooth easing). Dots fade except USA + Denmark. Label fade-in (spring). Greece/Mexico brief flash (0.3s glow + fade). Final question text: slow fade-in over 2s.
- **Component:** `QuadrantScatter` (zoom + selective dimming) + text overlay
- **Transition:** Fade to black

---

## Scene 14: End Card
- **Time:** 12:25 – 12:36
- **Section:** End
- **Voiceover excerpt:** "And that's a number no index can measure."
- **Visual:** Fade to #1A1B22 black. Channel watermark appears subtly. The final sentence hangs in silence for 1-2 seconds. No "like and subscribe" — just the empty space. Optional: YouTube end screen area (last 20s) with subscribe button placement zone and next video suggestion zone.
- **Animation:** Fade to black (1.5s). Watermark fade-in (0.5s). Hold 3-5s silence.
- **Component:** Custom — `EndCardScene`
- **Transition:** End of video
- **Notes:** YouTube requires end screen elements to be in the last 5-20 seconds. Keep this area clean for the overlay.

---

## Production Notes

### Assets to Create/Collect
1. **Country flag icons** — 33 SVG flags (can use emoji fallback for prototype)
2. **Big Mac image** — AI-generated, dark moody bg, editorial style (`npm run generate-image`)
3. **Zurich + Mexico City silhouettes** — AI-generated or Pexels stock
4. **Calendar grid component** — new Remotion component for the 55-day visualization

### New Remotion Components Needed
| Component | Scene | Priority | Complexity |
|-----------|-------|----------|------------|
| `SalaryShuffleScene` | 1 | Medium | Medium — text + flag + re-sort animation |
| `RankingResortScene` | 4 | High | High — dual-column animated rank with trails |
| `CalendarGrid` | 8 | High | Medium — 12×31 grid with highlighted days |
| `DivisionComparison` | 9 | Medium | Low — animated division equation |
| `ComparisonOverlay` | 8, 10 | High | Medium — connector line + stat card |
| `EndCardScene` | 14 | Low | Low — fade + watermark |

### Existing Components Used
| Component | Scenes | Notes |
|-----------|--------|-------|
| `QuadrantScatter` | 5-13 | HERO — on screen for ~7 minutes. Needs zoom/dim capability |
| `BarChart` | 2-3 | PPP wages, Big Mac prices |

### QuadrantScatter Enhancements Needed
1. **Selective dimming** — ability to dim all dots except specified ones (for Scene 13 zoom)
2. **Camera zoom** — smooth zoom into a specific coordinate region
3. **Connector lines** — draw lines between two country dots with midpoint label
4. **Phased dot entrance** — ability to show dots by quadrant (DREAM first, then GRIND, etc.)

### Audio/TTS Notes
- TTS provider: ElevenLabs, voice: Maisie
- SSML breaks already embedded in script
- `[curious]` and `[thoughtful]` tags for voice direction
- Estimated TTS output: ~12:00-12:30
