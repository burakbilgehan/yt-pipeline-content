# Research v2: Time vs Earnings — The 4-Quadrant Matrix (PPP-Only)

> Version: research-v2
> Based on: research-v1, methodology-analysis-double-adjustment.md, fte-hours-research.md
> Date: 2026-03-22
> Status: Complete — PPP pivot applied, Big Mac dropped
> Sources: OECD Average Wages (2024 PPP), OECD Hours Worked (2022)

---

## 1. Methodology Change from v1

**v1 used:** `Big Macs/hr = (PPP Annual Wage ÷ Annual Hours) ÷ Big Mac Price USD`
**v2 uses:** `PPP Annual Salary ($)` as Y-axis directly, `Annual Hours Worked` as X-axis

### Why Big Mac Was Dropped

Dividing PPP-adjusted wages by Big Mac USD prices creates a **double adjustment problem**:
- PPP already adjusts for local price levels using a ~3,000 item basket
- Big Mac price applies a SECOND local-price adjustment on top
- Result: countries with cheap currencies (Japan, Mexico) get overstated; expensive currencies (Switzerland, Norway) get understated
- The distortion factor is `E / PPP_factor` (market exchange rate ÷ PPP rate) — up to 68% for Mexico, 35% for Japan

Full analysis: `research/data/methodology-analysis-double-adjustment.md`

### Why PPP Salary Works

PPP-adjusted annual salary answers: "How much purchasing power does this worker's salary represent in US-dollar-equivalent terms?" It's the gold standard for cross-country wage comparison. Combined with hours worked, it reveals which countries get the most value per hour of life spent working.

The video's Phase 1 now explains **what PPP is and why raw salary numbers are misleading** — replacing the Big Mac explainer with a more robust economic concept.

---

## 2. Data Sources

| Dataset | Source | Year | Coverage |
|---------|--------|------|----------|
| Average Annual Wages (PPP $) | OECD via Wikipedia | 2024 | 34 OECD members |
| Average Annual Hours Worked | OECD via Wikipedia | 2022 | 38 OECD members |

**Year mismatch caveat:** Wages are 2024, hours are 2022. ±2 year spread — acceptable for macro comparison. OECD hours data lags because it requires national accounts compilation. Relative rankings are stable year-over-year.

**Hours methodology note:** OECD "Average annual hours actually worked" (ANHRS) includes ALL workers — full-time and part-time. This is the only consistent dataset covering all 34 countries. Countries with high part-time rates (Netherlands ~50%, Germany ~27%, Japan rising) show lower averages. The PPP wage figure is full-time equivalent. This methodological tension is acknowledged in the video. Full analysis: `research/data/fte-hours-research.md`

---

## 3. The Complete Data Table

34 OECD countries, sorted by PPP annual wage (descending):

| Rank | Country | Code | PPP Wage ($) | Hours/yr | $/hr | Quadrant |
|------|---------|------|------------:|--------:|-----:|----------|
| 1 | Luxembourg | LUX | 94,447 | 1,473 | 64.12 | DREAM |
| 2 | Iceland | ISL | 89,947 | 1,449 | 62.08 | DREAM |
| 3 | Switzerland | CHE | 87,468 | 1,528 | 57.24 | DREAM |
| 4 | United States | USA | 82,933 | 1,810 | 45.82 | GRIND |
| 5 | Belgium | BEL | 76,109 | 1,525 | 49.91 | DREAM |
| 6 | Austria | AUT | 75,767 | 1,443 | 52.51 | DREAM |
| 7 | Netherlands | NLD | 75,370 | 1,427 | 52.82 | DREAM |
| 8 | Norway | NOR | 74,864 | 1,424 | 52.57 | DREAM |
| 9 | Denmark | DNK | 74,022 | 1,371 | 53.99 | DREAM |
| 10 | Australia | AUS | 70,763 | 1,707 | 41.45 | GRIND |
| 11 | Germany | DEU | 69,433 | 1,340 | 51.82 | DREAM |
| 12 | Canada | CAN | 69,417 | 1,686 | 41.17 | GRIND |
| 13 | United Kingdom | GBR | 63,691 | 1,531 | 41.60 | DREAM |
| 14 | New Zealand | NZL | 62,437 | 1,748 | 35.72 | GRIND |
| 15 | Slovenia | SVN | 61,776 | 1,619 | 38.16 | DREAM |
| 16 | France | FRA | 60,608 | 1,511 | 40.11 | DREAM |
| 17 | Ireland | IRL | 60,431 | 1,657 | 36.47 | GRIND |
| 18 | Finland | FIN | 59,597 | 1,498 | 39.78 | DREAM |
| 19 | Sweden | SWE | 59,058 | 1,440 | 41.01 | CHILL |
| 20 | Israel | ISR | 54,736 | 1,891 | 28.95 | TRAP |
| 21 | Spain | ESP | 54,564 | 1,643 | 33.21 | TRAP |
| 22 | Lithuania | LTU | 52,898 | 1,624 | 32.57 | CHILL |
| 23 | Italy | ITA | 51,019 | 1,694 | 30.12 | TRAP |
| 24 | South Korea | KOR | 50,947 | 1,901 | 26.80 | TRAP |
| 25 | Japan | JPN | 49,446 | 1,607 | 30.77 | CHILL |
| 26 | Latvia | LVA | 45,567 | 1,553 | 29.34 | CHILL |
| 27 | Poland | POL | 44,211 | 1,814 | 24.37 | TRAP |
| 28 | Portugal | PRT | 40,002 | 1,635 | 24.47 | TRAP |
| 29 | Estonia | EST | 38,975 | 1,770 | 22.02 | TRAP |
| 30 | Czech Republic | CZE | 38,489 | 1,754 | 21.94 | TRAP |
| 31 | Slovakia | SVK | 36,105 | 1,622 | 22.26 | CHILL |
| 32 | Hungary | HUN | 34,996 | 1,699 | 20.60 | TRAP |
| 33 | Greece | GRC | 32,257 | 1,886 | 17.10 | TRAP |
| 34 | Mexico | MEX | 20,433 | 2,226 | 9.18 | TRAP |

### Excluded Countries
- **Turkey:** Not in OECD average wage PPP table (2024). Hours available (1,732).
- **Chile:** Hours (1,962) available but no 2024 PPP wage in OECD dataset.
- **Colombia, Costa Rica:** Newer OECD members, incomplete data.

---

## 4. The 4-Quadrant Matrix

### Origin Point

- **Mean PPP Wage:** $59,200 (arithmetic mean of 34 countries)
- **Mean Hours:** 1,633 hrs/yr (arithmetic mean of 34 countries)

### Axis Definitions

- **X-axis:** Annual Hours Worked (OECD 2022) — more hours = further right
- **Y-axis:** PPP-Adjusted Annual Salary ($) — higher salary = higher up
- **Origin crosshair:** ($59,200, 1,633 hours)

### Quadrant Distribution

| Quadrant | Position | Count | Countries |
|----------|----------|------:|-----------|
| DREAM | Top-left: high salary, low hours | 13 | LUX, ISL, CHE, BEL, AUT, NLD, NOR, DNK, DEU, GBR, SVN, FRA, FIN |
| GRIND | Top-right: high salary, high hours | 5 | USA, AUS, CAN, NZL, IRL |
| CHILL | Bottom-left: low salary, low hours | 5 | SWE, LTU, JPN, LVA, SVK |
| TRAP | Bottom-right: low salary, high hours | 11 | ISR, ESP, ITA, KOR, POL, PRT, EST, CZE, HUN, GRC, MEX |

### DREAM (13 countries) — "Work less, earn more"
*Salary > $59,200 AND Hours < 1,633*

The largest quadrant. Western/Northern Europe dominates. These countries have solved the equation: high hourly productivity translates into high salaries WITHOUT requiring long hours.

**Standout stories:**
- **Luxembourg** ($94,447, 1,473h) — Highest salary, moderate hours. Financial sector + small population.
- **Iceland** ($89,947, 1,449h) — #2 salary, tiny economy punching way above weight.
- **Germany** ($69,433, 1,340h) — FEWEST hours in entire dataset. Strong manufacturing + unions + robust labor law.
- **Denmark** ($74,022, 1,371h) — Second-fewest hours, flexicurity model.
- **Switzerland** ($87,468, 1,528h) — Third-highest salary. Often perceived as expensive, but PPP already accounts for that.

**Note:** 13 of 34 countries in DREAM (~38%). The narrative should spotlight 4-5 standouts rather than listing all 13.

### GRIND (5 countries) — "Work a lot, but at least it pays well"
*Salary > $59,200 AND Hours ≥ 1,633*

The Anglosphere quadrant. Every country here is English-speaking (USA, Australia, Canada, New Zealand, Ireland).

**Standout stories:**
- **USA** ($82,933, 1,810h) — Highest salary in GRIND, but works 470 more hours than Germany for only 19% more total salary. Per hour: Germany earns 13% MORE.
- **Ireland** ($60,431, 1,657h) — Closest to origin in GRIND — just $1,231 above the wage mean and 24 hours over the hours mean. Multinational HQ effect (Apple, Google, Meta) inflates national average.
- **New Zealand** ($62,437, 1,748h) — Moderate salary, near the hours boundary.

### CHILL (5 countries) — "Work less, earn less"
*Salary < $59,200 AND Hours < 1,633*

**Standout stories:**
- **Sweden** ($59,058, 1,440h) — Just $142 below the wage mean. Hourly rate ($41.01) is neck-and-neck with Canada ($41.17/hr) and Australia ($41.45/hr), both in GRIND — and well above New Zealand ($35.72/hr). Sweden's placement is a statistical artifact of the binary cutoff — functionally a DREAM country.
- **Japan** ($49,446, 1,607h) — The surprise. Known for karoshi (death from overwork), yet shows below-average hours. Explanation: OECD counts ALL workers including Japan's large part-time workforce. Full-time workers still work extreme hours. See `research/data/fte-hours-research.md`.
- **Slovakia** ($36,105, 1,622h) — Low wages but also moderate hours by Eastern European standards.

### TRAP (11 countries) — "Work the most, earn the least"
*Salary < $59,200 AND Hours ≥ 1,633*

The largest "bad" quadrant. Southern Europe, Eastern Europe, plus outliers.

**Standout stories:**
- **Greece** ($32,257, 1,886h) — Works the most hours in the EU, earns the lowest among EU members in this dataset. A German earns 3.0× more per hour while working 29% fewer hours.
- **Mexico** ($20,433, 2,226h) — The extreme. Works 886 more hours than Germany per year (111 extra 8-hour workdays). Earns 5.6× LESS per hour.
- **South Korea** ($50,947, 1,901h) — High-tech economy trapped by long hours culture. Similar annual salary to Italy ($51,019) but works 207 more hours for it.
- **Italy** ($51,019, 1,694h) — G7 economy with near-stagnant real wages over two decades.
- **Israel** ($54,736, 1,891h) — Surprising for a tech-economy reputation. Long hours + moderate wage = TRAP.
- **Spain** ($54,564, 1,643h) — Just 10 hours over the mean. Youth unemployment legacy.
- **Portugal** ($40,002, 1,635h) — Also barely over the hours mean (2 hours). Western European cost of living, Eastern European wages.

---

## 5. Killer Stats for the Video

### The Headline Comparisons

1. **Germany vs USA — the hourly rate flip:**
   - USA earns $82,933/yr. Germany earns $69,433/yr. On paper, USA wins by 19%.
   - But Germany works 1,340 hours. USA works 1,810 hours. That's **470 extra hours** — **59 extra 8-hour workdays**.
   - Per hour: Germany $51.82, USA $45.82. **Germany earns 13% more per hour.**
   - An American works almost 3 extra months per year for a salary that's only 19% higher.

2. **USA vs Denmark — the 439-hour question:**
   - USA: $82,933/yr at 1,810 hrs. Denmark: $74,022/yr at 1,371 hrs.
   - USA earns 12% more total. Denmark earns 18% more per hour ($53.99 vs $45.82).
   - The American works **439 extra hours** — **55 eight-hour days** — nearly **11 extra work weeks** per year.
   - For 12% more annual salary.

3. **Germany vs Greece — same continent, different planet:**
   - Both EU members. Germany: $69,433 at 1,340h. Greece: $32,257 at 1,886h.
   - Germany earns **3.0× more per hour** ($51.82 vs $17.10).
   - Greece works **546 more hours** per year.
   - Germany earns 2.2× more total while working 29% fewer hours.

4. **Germany vs Mexico — the extreme:**
   - Germany: $51.82/hr. Mexico: $9.18/hr. Germany earns **5.6× more per hour**.
   - Mexico works **886 more hours** per year — **111 extra 8-hour days**.
   - In total salary, Germany earns 3.4× more ($69,433 vs $20,433).

5. **Luxembourg vs Mexico — the poles:**
   - Luxembourg: $64.12/hr at 1,473h. Mexico: $9.18/hr at 2,226h.
   - Luxembourg earns **7.0× more per hour** while working **753 fewer hours**.

6. **South Korea vs Italy — same salary, different life:**
   - KOR: $50,947/yr at 1,901h. ITA: $51,019/yr at 1,694h.
   - Nearly identical annual salary (~$72 difference).
   - Korea works **207 more hours** — **26 extra workdays** — for the same paycheck.

7. **Sweden — the statistical anomaly:**
   - $59,058/yr — just $142 below the $59,200 wage mean.
   - Hourly rate: $41.01 — neck-and-neck with Canada ($41.17) and Australia ($41.45), both in GRIND. Well above New Zealand ($35.72).
   - CHILL by the numbers, DREAM in spirit.

8. **Japan — the karoshi paradox:**
   - Japan at 1,607 hours — below USA (1,810), below OECD mean (1,633).
   - A country known for death from overwork shows below-average hours.
   - Reason: OECD counts all workers. Japan's rising part-time workforce (freeters, part-time women, retired part-timers) pulls the average down.
   - Full-time workers still work extreme hours. The statistic is correct — it just measures something different than what people expect.

### The Hook Number

**Opening stat:** "The average American earns $82,933 a year. The average German earns $69,433. On paper, the American earns 19% more. But the German earns more for every hour they work — and works 470 fewer hours a year to do it."

---

## 6. Phase 1 Content: "What is PPP?"

Phase 1 (~5 min) now explains Purchasing Power Parity instead of the Big Mac Index.

### Core Concept
$50,000 in New York ≠ $50,000 in Warsaw ≠ $50,000 in Tokyo. PPP adjusts for local price levels so we can compare apples to apples.

### Teaching Sequence
1. **The problem:** Raw salary numbers are meaningless across borders. A $3,000/month salary is luxury in Hanoi, poverty in Zurich.
2. **The fix:** Economists use PPP — they calculate what a "basket" of ~3,000 goods and services costs in each country, then convert all salaries to a common unit ("PPP dollars" or "international dollars").
3. **What PPP dollars mean:** When OECD says a Swiss worker earns $87,468 PPP, it means their salary buys the same amount of stuff as $87,468 would buy in the USA.
4. **The reveal:** Now that we have apples-to-apples salary numbers... the real question is: how many hours do people WORK for that salary?

### Visual Ideas for Phase 1
- Same apartment/grocery cart priced in different cities
- Bar chart: nominal salary vs PPP salary for 5-6 countries (show how PPP reorders the ranking)
- Simple animation: a basket of goods, same contents, different price tags

---

## 7. Phase 2 Content: The Quadrant Matrix

Phase 2 (~7 min) reveals and explores the 4-quadrant matrix.

### Reveal Sequence
1. Start with a blank scatter plot — just axes labeled
2. Plot the OECD mean crosshair ($59,200, 1,633h)
3. Label the four quadrants: DREAM, GRIND, CHILL, TRAP
4. Countries appear one by one or in clusters by quadrant
5. Spotlight comparisons with connector lines

### Quadrant Narrative Order
1. **DREAM** first — establish what "winning" looks like
2. **GRIND** — "but what if you earn well AND work a lot?"
3. **TRAP** — "and what if you work a lot and DON'T earn well?"
4. **CHILL** — "and then there are the quiet ones"
5. **Japan anomaly** — "wait, Japan is in CHILL? Here's why."
6. **Closing comparison** — Germany vs USA vs Greece (triangle of extremes)

---

## 8. Data Integrity Notes

### What's Solid
- OECD PPP wages are the gold standard for cross-country wage comparison
- OECD hours are from national accounts — the most reliable hours data available
- 34 countries with complete, consistent data from the same source

### Known Limitations

1. **Part-time distortion:** Countries with high part-time rates (NLD, DEU, JPN) show lower average hours, but PPP wages are FTE-adjusted. This structurally favors these countries in the matrix. Acknowledged in video.

2. **Hours data 2 years older than wages:** Hours 2022, wages 2024. Post-COVID hours recovery may not be fully captured. Rankings stable enough.

3. **Mean vs median wages:** OECD reports arithmetic means. Countries with high income inequality (USA, MEX, ISR) have means pulled up by high earners. The median worker earns less. This slightly overstates purchasing power for unequal countries.

4. **Informal economy:** Mexico, Greece, some Eastern European countries have significant informal economic activity not captured in official stats. Real earnings may differ.

5. **Taxes and benefits not captured:** A Dane pays ~45% marginal tax but gets free healthcare and university. An American keeps more gross pay but spends heavily on insurance/tuition. Our metric is gross PPP salary, not disposable income.

### Transparency Statement for Video
"All wage data is OECD 2024, PPP-adjusted. Hours from OECD 2022. PPP means salaries are adjusted for local purchasing power — one PPP dollar buys the same amount everywhere. This is a simplified comparison — real life includes taxes, benefits, and cost variations within countries."

---

## 9. Preemptive Rebuttals

**Q1: "Why not use take-home pay after taxes?"**
A: After-tax comparison would be ideal but requires modeling tax brackets, social contributions, and in-kind benefits (healthcare, education) for 34 countries — beyond scope. Gross PPP is the standard OECD comparison metric. We note the limitation.

**Q2: "These are MEAN wages, not MEDIAN. Rich people skew the average."**
A: Correct. OECD reports means. Countries with high inequality (USA) have means pulled up. Median data isn't available on a consistent cross-country basis. The relative rankings don't change dramatically.

**Q3: "Part-time work skews the hours. Netherlands/Germany have lots of part-timers."**
A: Yes. Hours data includes part-timers, wages are FTE-adjusted. This favors high-part-time countries. We acknowledge this in the video — it's actually a good story (these societies enable part-time work with high hourly pay).

**Q4: "Japan has karoshi — how can hours be low?"**
A: OECD counts ALL workers. Japan's large and growing part-time workforce pulls the average down. Full-time workers still work extreme hours. The number is correct for what it measures. We explain this explicitly in the video.

**Q5: "This is OECD only. You're ignoring most of the world."**
A: Deliberately. OECD has standardized, comparable data. Adding non-OECD countries requires mixing sources with different definitions. Saved for Part 2.

**Q6: "Sweden in CHILL? That's wrong."**
A: Sweden is $142 below the wage mean — a rounding error. Its hourly rate ($41.01) is competitive with GRIND countries. The quadrant boundary is an arbitrary line. We acknowledge this.

---

## 10. Competitive Landscape

- "Countries ranked by salary" — many listicle videos, none combine with hours worked
- "Working hours by country" — common topic, never paired with PPP salary in a matrix
- "PPP explained" — educational videos exist, but none use it as setup for a comparative matrix reveal

**Our angle remains unique:** The 4-quadrant matrix (PPP salary × hours worked) does not appear to exist on YouTube.

---

## 11. Summary for Content Writer

**Video concept:** 10-15 minute data visualization video. Two-phase structure.

**Phase 1 (~5 min):** Explain that raw salary numbers are meaningless across borders. Introduce PPP — what it is, why it matters. Show how PPP reorders salary rankings. Build to the transition: "Now you know what people actually earn. But how long do they work for it?"

**Phase 2 (~7 min):** Reveal the 4-quadrant matrix. Walk through each quadrant. Spotlight Germany vs USA, Germany vs Greece, Japan anomaly, South Korea vs Italy. Close with the philosophical question: "Is it better to earn $51.82/hr and work 1,340 hours, or earn $45.82/hr and work 1,810 hours?"

**Key emotional beats:**
1. "You think you know who earns the most? You don't." (Hook)
2. "A $50,000 salary means completely different things in different countries" (Phase 1 setup)
3. "Now that you know what people earn... how long do they work for it?" (Phase 2 reveal)
4. "A Greek worker works 546 more hours than a German and earns 3× less per hour" (Shock stat)
5. "Japan — the country of karoshi — shows BELOW-average working hours. Here's why." (Surprise)
6. "Americans work 59 extra 8-hour days per year compared to Germans. For 19% more salary." (Closer)

**Tone:** Numbers speak. No editorializing. Let the viewer draw their own conclusions.
