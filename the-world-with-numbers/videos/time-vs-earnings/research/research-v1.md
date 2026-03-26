# Research v1: Time vs Earnings — The 4-Quadrant Matrix

> Version: research-v1
> Based on: pre-research-v1
> Date: 2026-03-21
> Status: Complete research with computed metrics
> Sources: OECD Average Wages (2024 PPP), OECD Hours Worked (2022), The Economist Big Mac Index (Jan 2025)

---

## 1. Core Metric: Big Macs Per Hour Worked

**Formula:** `Big Macs/hr = (Annual Wage PPP ÷ Annual Hours) ÷ Big Mac Price USD`

This metric answers: **"How many Big Macs can a worker in country X buy with one hour of work?"**

Why this metric:
- Raw salary numbers are meaningless across borders ($3,000/month means luxury in Vietnam, poverty in Zurich)
- PPP-adjusted wages correct for general price levels, but Big Mac Index makes it tangible and visual
- Dividing by hours worked reveals the TRUE earning power per unit of life spent working

### Data Sources & Year Alignment

| Dataset | Source | Year | Coverage |
|---------|--------|------|----------|
| Average Annual Wages (PPP) | OECD via Wikipedia | 2024 | 34 OECD members |
| Average Annual Hours Worked | OECD via Wikipedia | 2022 | 38 OECD members |
| Big Mac Price (USD) | The Economist GitHub | Jan 2025 | 54 countries |

**Year mismatch caveat:** Wages are 2024, hours are 2022, Big Mac prices are Jan 2025. This is a ±2 year spread — acceptable for a macro comparison video, but must be disclosed. OECD hours data lags because it requires national accounts compilation. The relative rankings are stable year-over-year.

**Euro area limitation:** The Big Mac Index reports a single price for the entire Euro area ($5.95). Individual Eurozone countries (Germany, France, Italy, Spain, Netherlands, Austria, Belgium, Finland, Ireland, Greece, Slovenia, Slovakia, Estonia, Latvia, Lithuania, Portugal) share this price. In reality, Big Mac prices vary within the Eurozone (e.g., cheaper in Lisbon than Munich), but this is the best available standardized data. Video should mention this.

---

## 2. The Complete Data Table

### 2a. Countries with All Three Data Points (OECD Wages + Hours + Big Mac)

Sorted by Big Macs per hour (descending):

| Rank | Country | Annual Wage (PPP $) | Hours/yr | $/hr | Big Mac $ | Big Macs/hr | Quadrant |
|------|---------|--------------------:|--------:|-----:|----------:|------------:|----------|
| 1 | Luxembourg | 94,447 | 1,473 | 64.12 | 5.95† | 10.78 | ★ DREAM |
| 2 | Japan | 49,446 | 1,607 | 30.77 | 3.11 | 9.89 | ★ DREAM |
| 3 | Denmark | 74,022 | 1,371 | 53.99 | 5.49 | 9.83 | ★ DREAM |
| 4 | Netherlands | 75,370 | 1,427 | 52.82 | 5.95† | 8.88 | ★ DREAM |
| 5 | Austria | 75,767 | 1,443 | 52.50 | 5.95† | 8.82 | ★ DREAM |
| 6 | Germany | 69,433 | 1,340 | 51.81 | 5.95† | 8.71 | ★ DREAM |
| 7 | Australia | 70,763 | 1,707 | 41.45 | 4.87 | 8.51 | ★ DREAM |
| 8 | Belgium | 76,109 | 1,525 | 49.91 | 5.95† | 8.39 | ★ DREAM |
| 9 | USA | 82,933 | 1,810 | 45.82 | 5.79 | 7.91 | GRIND |
| 10 | Norway | 74,864 | 1,424 | 52.57 | 6.67 | 7.88 | ★ DREAM |
| 11 | Canada | 69,417 | 1,686 | 41.17 | 5.43 | 7.58 | ★ DREAM |
| 12 | New Zealand | 62,437 | 1,748 | 35.72 | 4.77 | 7.49 | ★ DREAM |
| 13 | UK | 63,691 | 1,531 | 41.60 | 5.73 | 7.26 | ★ DREAM |
| 14 | Sweden | 59,058 | 1,440 | 41.01 | 5.67 | 7.23 | ★ DREAM |
| 15 | Switzerland | 87,468 | 1,528 | 57.24 | 7.99 | 7.16 | ★ DREAM |
| 16 | South Korea | 50,947 | 1,901 | 26.80 | 3.84 | 6.98 | GRIND |
| 17 | France | 60,608 | 1,511 | 40.11 | 5.95† | 6.74 | ★ DREAM |
| 18 | Finland | 59,597 | 1,498 | 39.78 | 5.95† | 6.69 | ★ DREAM |
| 19 | Slovenia | 61,776 | 1,619 | 38.16 | 5.95† | 6.41 | CHILL |
| 20 | Israel | 54,736 | 1,891 | 28.94 | 4.71 | 6.14 | ⚠ TRAP |
| 21 | Ireland | 60,431 | 1,657 | 36.47 | 5.95† | 6.13 | CHILL |
| 22 | Hungary | 34,996 | 1,699 | 20.60 | 3.65 | 5.64 | CHILL |
| 23 | Spain | 54,564 | 1,643 | 33.20 | 5.95† | 5.58 | CHILL |
| 24 | Lithuania | 52,898 | 1,624 | 32.57 | 5.95† | 5.47 | CHILL |
| 25 | Italy | 51,019 | 1,694 | 30.12 | 5.95† | 5.06 | CHILL |
| 26 | Latvia | 45,567 | 1,553 | 29.34 | 5.95† | 4.93 | CHILL |
| 27 | Czech Republic | 38,489 | 1,754 | 21.94 | 4.56 | 4.81 | ⚠ TRAP |
| 28 | Poland | 44,211 | 1,814 | 24.37 | 5.21 | 4.68 | ⚠ TRAP |
| 29 | Portugal | 40,002 | 1,635 | 24.47 | 5.95† | 4.11 | CHILL |
| 30 | Slovakia | 36,105 | 1,622 | 22.26 | 5.95† | 3.74 | CHILL |
| 31 | Estonia | 38,975 | 1,770 | 22.02 | 5.95† | 3.70 | ⚠ TRAP |
| 32 | Greece | 32,257 | 1,886 | 17.11 | 5.95† | 2.88 | ⚠ TRAP |
| 33 | Mexico | 20,433 | 2,226 | 9.18 | 4.60 | 2.00 | ⚠ TRAP |

† = Euro area price ($5.95) used. Individual country price not available.

**Chile excluded from final ranking:** Chile has OECD hours data (1,962) and Big Mac data ($4.55) but was not in the 2024 OECD wage table extracted. Can be added if wage data is found separately.

**Turkey excluded:** Has OECD hours (1,732) and Big Mac ($5.32) but not in the OECD average wage PPP dataset (2024).

**Iceland excluded:** Has OECD wage data ($89,947) and hours (1,449) but no Big Mac Index entry.

**Other OECD members excluded:** Colombia, Costa Rica, and other newer OECD members lack complete overlap across all three datasets (wages, hours, Big Mac price).

---

## 3. The 4-Quadrant Matrix

### Axis Definitions

- **X-axis:** Annual Hours Worked (OECD 2022) — more hours = further right
- **Y-axis:** Big Macs per Hour Worked — more purchasing power = higher up
- **Origin:** OECD average hours: 1,751 | Mean Big Macs/hr of 33 countries: 6.61

### OECD Average Calculation (Origin Point)

Using all 33 countries with complete data:

- **Average Hours:** 1,636 hrs/yr (mean of the 33 countries)
- **Average Big Macs/hr:** 6.61 (arithmetic mean of the 33 countries: sum 218.01 ÷ 33)

Note: The official OECD average hours for 2022 is 1,751. We use the official OECD figure for the X-axis origin since it's a recognized external benchmark that includes non-Big-Mac countries too. We compute BM/hr internally because no official OECD Big Mac metric exists — 6.61 is the only defensible origin for the Y-axis.

**Final Origin: (1,751 hours, 6.61 Big Macs/hr)**

### Quadrant Assignments

#### ★ TOP-LEFT: THE DREAM (Low hours, High purchasing power)
*"Work less, buy more" — Hours < 1,751 AND Big Macs/hr > 6.61*

| Country | Hours | Big Macs/hr | Story |
|---------|------:|------------:|-------|
| Luxembourg | 1,473 | 10.78 | Ultimate dream — fewest hours, highest purchasing power |
| Japan | 1,607 | 9.89 | SURPRISE — cheap Big Macs ($3.11) make purchasing power incredible despite "low" wages |
| Denmark | 1,371 | 9.83 | Second-fewest hours in dataset (after Germany), ~10 Big Macs per hour |
| Netherlands | 1,427 | 8.88 | Famous for part-time culture, still earns massively per hour |
| Austria | 1,443 | 8.82 | Quiet overachiever — rarely discussed |
| Germany | 1,340 | 8.71 | FEWEST hours in entire OECD, near top in purchasing power |
| Australia | 1,707 | 8.51 | Just under the hours line — high pay, moderate hours |
| Belgium | 1,525 | 8.39 | Strong unions, strong wages |
| Norway | 1,424 | 7.88 | Oil wealth + short hours |
| Canada | 1,686 | 7.58 | Anglosphere outlier — works less than USA, earns well |
| New Zealand | 1,748 | 7.49 | Barely under the 1,751 hours line — almost GRIND |
| UK | 1,531 | 7.26 | Post-Brexit still holds strong purchasing power |
| Sweden | 1,440 | 7.23 | Nordic model poster child |
| Switzerland | 1,528 | 7.16 | Second-highest PPP wage ($87,468, behind Luxembourg), but Big Mac costs $7.99 so purchasing power is "only" 7.16 |
| France | 1,511 | 6.74 | 35-hour workweek, still decent purchasing power |
| Finland | 1,498 | 6.69 | Just barely in Dream quadrant |

**16 countries — nearly half the dataset.** Western/Northern Europe dominates, but the biggest surprise is **Japan at #2** — cheap local prices make moderate wages go very far. The "lazy European" stereotype is actually "efficient European" — they earn more per hour of life spent working than almost anyone. The Anglosphere (Australia, Canada, NZ, UK) also sneaks in with hours just below the OECD average.

> **Note for scriptwriter:** 16 of 33 countries in DREAM may make the quadrant feel crowded. The narrative should acknowledge this imbalance — "most OECD countries have figured out the work-life balance equation; the real question is why some haven't." Focus spotlight on 4-5 standout stories (Luxembourg, Japan, Germany, Denmark, Switzerland) rather than listing all 16.

#### ↗ TOP-RIGHT: THE GRIND (High hours, High purchasing power)
*"Work a lot, but at least it pays well" — Hours ≥ 1,751 AND Big Macs/hr > 6.61*

| Country | Hours | Big Macs/hr | Story |
|---------|------:|------------:|-------|
| USA | 1,810 | 7.91 | High pay, but works 470 more hours/year than Germany for similar purchasing power |
| South Korea | 1,901 | 6.98 | Just above the BM/hr line — longest hours in the high-earning club |

**Only 2 countries.** This is the loneliest quadrant. The USA and South Korea are the only nations that combine above-average hours with above-average purchasing power. The American story is particularly compelling — working 32% more hours than a Dane for just 6% more Big Macs. South Korea barely qualifies at 6.98 BM/hr (origin = 6.61) — just 0.37 above the line.

> **Borderline watch:** New Zealand (1,748 hrs, 7.49 BM/hr) sits just 3 hours below the GRIND boundary — effectively straddling DREAM and GRIND. South Korea is only 0.37 BM/hr above the CHILL line. These near-misses make great narrative material.

#### ↙ BOTTOM-LEFT: THE CHILL (Low hours, Low purchasing power)
*"Don't work much, don't earn much either" — Hours < 1,751 AND Big Macs/hr ≤ 6.61*

| Country | Hours | Big Macs/hr | Story |
|---------|------:|------------:|-------|
| Slovenia | 1,619 | 6.41 | Borderline — close to average on both axes |
| Ireland | 1,657 | 6.13 | Multinational HQs inflate GDP; average wages may also be skewed upward by high-paying tech/pharma sectors concentrated in Dublin |
| Hungary | 1,699 | 5.64 | Cheap Big Mac ($3.65) helps, but still below average |
| Spain | 1,643 | 5.58 | Youth unemployment crisis legacy |
| Lithuania | 1,624 | 5.47 | Tripled wages since 2000 but still below average |
| Italy | 1,694 | 5.06 | STAGNANT wages — same as 2000! A G7 economy stuck |
| Latvia | 1,553 | 4.93 | Post-Soviet, developing |
| Portugal | 1,635 | 4.11 | Western European prices, Eastern European wages |
| Slovakia | 1,622 | 3.74 | Low wages, Euro area Big Mac prices |

**9 countries.** Southern/Eastern Europe. Italy is the shock story — a G7 economy with wages that haven't grown in 25 years, buying only 5 Big Macs per hour. Portugal is the squeeze within Europe — forced to pay Euro-area prices ($5.95) on a wage of just $40,002. Result: only 4.11 Big Macs/hr — less than Hungary (5.64), which earns a lower raw wage ($34,996 vs $40,002) but has much cheaper Big Macs ($3.65).

#### ↘ BOTTOM-RIGHT: THE TRAP (High hours, Low purchasing power)
*"Work the most, earn the least" — Hours ≥ 1,751 AND Big Macs/hr ≤ 6.61*

| Country | Hours | Big Macs/hr | Story |
|---------|------:|------------:|-------|
| Israel | 1,891 | 6.14 | Long hours, expensive city (Tel Aviv), moderate purchasing power — surprising for a high-tech economy |
| Czech Republic | 1,754 | 4.81 | Just over the hours line, Euro-priced Big Mac ($4.56) doesn't help |
| Poland | 1,814 | 4.68 | Long hours + expensive Big Mac ($5.21) crushes purchasing power |
| Estonia | 1,770 | 3.70 | High hours for a Baltic state, Euro area prices hurt |
| Greece | 1,886 | 2.88 | POSTER CHILD — most hours in EU, lowest purchasing power in OECD Europe |
| Mexico | 2,226 | 2.00 | Works 66% more hours than Germany, earns 77% fewer Big Macs per hour |

**6 countries.** These countries are caught in a trap — working more hours than average but earning below-average purchasing power. Greece is the ultimate example: works the most hours in the EU but can only buy 2.88 Big Macs per hour. A German worker (8.71 BM/hr, 1,340 hrs) earns 3× more purchasing power while working 29% fewer hours. Israel is the surprise entry — a tech-economy reputation but long working hours and middling purchasing power.

---

## 4. Killer Stats for the Video

### The Headline Numbers

1. **Germany vs Mexico:** A German worker earns **4.4× more Big Macs per hour** while working **40% fewer hours**. In a year, a German worker "earns" 11,671 Big Macs. A Mexican worker earns 4,452. The German works 886 fewer hours.

2. **Germany vs Greece:** Both EU members. Germany: 8.71 Big Macs/hr × 1,340 hrs = **11,671 Big Macs/year**. Greece: 2.88 × 1,886 = **5,432 Big Macs/year**. Germany earns 2.1× more while working 29% less.

3. **USA vs Denmark:** USA: 7.91 × 1,810 = **14,317 Big Macs/year**. Denmark: 9.83 × 1,371 = **13,477 Big Macs/year**. Americans earn only 6% more Big Macs per year but work **32% more hours** (439 extra hours = 55 extra 8-hour workdays per year).

4. **Japan surprise:** Despite having "low" wages by OECD standards ($49,446), Japan ranks **#2 in Big Macs/hr** (9.89) because a Big Mac costs only $3.11. Your money goes far.

5. **Switzerland paradox:** Second-highest PPP-adjusted wage in the dataset ($87,468 — behind Luxembourg at $94,447) but only **#15 in Big Macs/hr** (7.16) because a Big Mac costs $7.99. High salary ≠ high purchasing power.

6. **Portugal trap:** Portugal pays Euro-area Big Mac prices ($5.95) on a wage of $40,002. Result: only 4.11 Big Macs/hr — less than Hungary (5.64) which earns a lower raw wage ($34,996 vs $40,002) but has much cheaper Big Macs ($3.65).

7. **The 439-hour question:** An American works 439 more hours per year than a Dane. That's **55 eight-hour workdays**. Almost **11 extra work weeks**. For just 6% more Big Macs.

### Phase 1 → Phase 2 Transition (The Punchline)

**Phase 1 (first ~5 min):** "You think a $50,000 salary in Germany and a $50,000 salary in Mexico are the same? Let me show you what $50,000 actually BUYS." → Big Mac normalization → purchasing power explained → scatter plot of $/hr vs Big Macs/hr for a few countries.

**Phase 2 (remaining ~7 min):** "Now you understand what people actually EARN. But here's the question nobody asks: how long do they WORK for it?" → Matrix appears → quadrant reveal → country-by-country storytelling → killer comparisons → closing thought.

---

## 5. Potential Non-OECD Countries (Bonus Layer)

These countries have Big Mac data but NOT OECD wages. Could be added using UNECE or ILO data if we want to expand beyond OECD:

| Country | Big Mac $ | Hours (Our World in Data) | Missing |
|---------|----------:|-------------------------:|---------|
| China | 3.52 | 2,328 | Reliable PPP wage |
| India | 2.62 | 2,383 | Reliable PPP wage |
| Brazil | 4.03 | 1,708 | Reliable PPP wage |
| Thailand | 4.01 | 2,177 | Reliable PPP wage |
| Indonesia | 2.54 | 2,020 | Reliable PPP wage |
| Vietnam | 3.03 | 2,160 | Reliable PPP wage |
| Philippines | 2.89 | 2,096 | Reliable PPP wage |
| South Africa | 2.78 | 2,181 | Reliable PPP wage |
| Egypt | 2.69 | 2,369 | Reliable PPP wage |
| Pakistan | 3.77 | 2,471 | Reliable PPP wage |

**Decision:** Stick with OECD-only for Part 1 (clean, comparable data). Non-OECD countries could appear as "ghosts" on the matrix (approximate positions) or be saved for Part 2.

---

## 6. Data Integrity Notes

### What's Solid
- OECD wages are PPP-adjusted, full-time equivalent — the gold standard for cross-country wage comparison
- OECD hours are from national accounts — the most reliable hours data available
- Big Mac Index is from The Economist's maintained dataset with consistent methodology since 1986

### Known Limitations
1. **Euro area single price:** All Eurozone countries use $5.95. Real prices vary (a Big Mac in Lisbon ≈ €4.50, in Munich ≈ €5.50). This slightly **understates** purchasing power for low-wage Eurozone countries (Portugal, Slovakia, Latvia) — their real Big Mac prices are likely cheaper than €5.95, so dividing by the higher Eurozone average makes their BM/hr look worse. Conversely, it slightly **overstates** purchasing power for high-wage Eurozone countries (Germany, Netherlands, Austria, Belgium) — their real Big Mac prices are likely at or above €5.95.

2. **Part-time distortion:** Countries with high part-time rates (Netherlands, Germany) show lower average hours. This makes them look even better in the matrix because their PPP wages are full-time equivalent but hours include part-timers. Should mention this caveat.

3. **Hours data 2 years older than wages:** Hours from 2022, wages from 2024. Post-COVID hours recovery may not be fully captured. Rankings are stable enough for this purpose.

4. **Big Mac ≠ entire cost of living:** It's one product. Healthcare, housing, education costs vary enormously and aren't captured. The Big Mac is a proxy — a good one for tradeable goods, less good for services.

5. **Informal economy:** In Mexico, Greece, and some Eastern European countries, significant economic activity is informal and not captured in official wage statistics. Real purchasing power may be higher than reported.

6. **PPP vs market exchange rates:** OECD wages use PPP conversion, Big Mac uses market exchange rates. There's a conceptual tension here — we're double-adjusting somewhat. However, for the video's purpose (tangible comparison), this works because we're asking "how many actual Big Macs can you buy," not "what's the theoretical PPP-adjusted purchasing power."

### Transparency for Video
The video should include a brief disclaimer (5-10 seconds, lower third or spoken): "All wage data is OECD 2024, PPP-adjusted. Hours from OECD 2022. Big Mac prices from The Economist, January 2025. Euro area countries share a single Big Mac price. This is a simplified comparison — real life is more complex."

---

## 7. Preemptive Rebuttals (Anticipated Audience Questions)

**Q1: "Why use Big Macs? That's not a real measure of purchasing power."**
A: The Big Mac is intentionally simplified. It's a single product made with local labor, local ingredients, local rent — making it a surprisingly good proxy for local cost of living. Economists at The Economist have maintained this index since 1986 precisely because it captures price differences in an intuitive way. We're not claiming it's perfect — we're using it to make purchasing power *tangible*. Nobody intuitively understands PPP dollars; everyone understands "I can buy X burgers per hour."

**Q2: "Aren't you double-adjusting? PPP wages divided by USD Big Mac prices?"**
A: Yes, there is a conceptual tension. PPP wages already adjust for general price levels, and then we divide by a product that reflects local prices. However, the question we're answering is concrete: "How many actual Big Macs can a worker buy with one hour's wage?" PPP adjustment ensures we're starting from comparable wage levels across countries, and the Big Mac price gives us a tangible local price to divide by. The alternative — nominal wages ÷ Big Mac price — would be distorted by exchange rate fluctuations. Neither approach is perfect; we've chosen the one that produces the most meaningful ranking. The video should mention this caveat briefly.

**Q3: "These are MEAN wages, not MEDIAN. Rich people skew the average."**
A: Correct. OECD average wages are arithmetic means. Countries with high income inequality (USA, Mexico, Israel) have their means pulled up by high earners — the median worker earns less. Countries with compressed wage distributions (Nordics, Japan) have means closer to the median. This means our metric *slightly* overstates purchasing power for unequal countries. We acknowledge this but use means because: (a) OECD reports means consistently across all countries, (b) median wage data isn't available on a comparable cross-country basis, and (c) the relative rankings don't change dramatically.

**Q4: "Part-time work skews the hours data. Netherlands and Germany have lots of part-timers."**
A: The OECD hours data is per worker, not per full-time-equivalent. Countries with high part-time rates (Netherlands: ~50%, Germany: ~27%) show lower average hours partly because many workers work part-time by choice. Their PPP wages, however, are full-time equivalent. This means these countries look especially good in the matrix — but it's partly because the comparison is structurally favorable to them. We should call this out in the video. It's still meaningful: if a society enables part-time work with high hourly pay, that IS a real lifestyle advantage.

**Q5: "This is OECD only. You're ignoring most of the world."**
A: Deliberately. OECD countries have comparable, standardized data. Adding non-OECD countries (China, India, Brazil) would require mixing data sources with different definitions of "average wage" and "hours worked." The numbers wouldn't be apples-to-apples. We hint at where non-OECD countries would fall (Section 5) and save a deeper global comparison for Part 2.

**Q6: "What about taxes, healthcare, education costs? Gross wages don't tell the full story."**
A: Absolutely true. A Dane pays ~45% marginal tax but gets free healthcare and university. An American keeps more gross pay but spends heavily on insurance and tuition. Our metric measures *gross* purchasing power per hour, not *disposable* purchasing power after taxes and social services. A full analysis would need after-tax wages + in-kind benefits, which is beyond the scope of a 12-minute video. We note this limitation.

---

## 8. Visual Specs

### The Matrix Chart
- X-axis: Annual Hours (1,300 → 2,300), left = fewer hours
- Y-axis: Big Macs/hr (1 → 11), bottom = less purchasing power
- Origin crosshair at OECD average (1,751 hrs, 6.61 Big Macs/hr)
- Each country = circle with flag, sized by population or GDP (TBD)
- Quadrant labels: DREAM (top-left, green), GRIND (top-right, yellow), CHILL (bottom-left, blue), TRAP (bottom-right, red)
- Animate countries appearing one by one or by quadrant

### Phase 1 Visuals
- Side-by-side: "$3,000 salary" → what it buys in Switzerland vs Turkey vs India (Big Mac stacks)
- Bar chart: Big Mac prices across countries
- Simple scatter: raw salary vs Big Mac purchasing power

### Phase 2 Visuals
- The Matrix — main visual, builds over ~3 minutes
- Spotlight comparisons: Germany vs Greece, USA vs Denmark, Japan surprise
- Timeline: how countries have MOVED in the matrix over 20 years (if data allows)

---

## 9. Competitive Landscape

Searched YouTube for similar content:
- "Big Mac Index explained" — several videos, but none combine it with working hours
- "Countries ranked by working hours" — many listicle videos, but none normalize by purchasing power
- "Cost of living comparison" — Numbeo-style videos, not data-driven in this way

**Our angle is unique:** The 4-quadrant matrix (hours × Big Mac purchasing power) does not appear to exist on YouTube. This is a genuinely novel visualization.

---

## 10. Summary for Content Writer

**Video concept:** 10-15 minute data visualization video. Two-phase structure.

**Phase 1 (~5 min):** Explain that raw salaries are meaningless across borders. Use Big Mac Index to normalize. Show that a $50,000 salary buys very different things in different countries. Build intuition for purchasing power.

**Phase 2 (~7 min):** Add the time dimension. Reveal the 4-quadrant matrix. Walk through each quadrant with killer stats. Close with the philosophical question: "Is it better to earn 8.71 Big Macs per hour and work 1,340 hours (Germany) or earn 7.91 Big Macs per hour and work 1,810 hours (USA)?"

**Key emotional beats:**
1. "You think you know who earns the most? You don't." (Hook)
2. "$3,000 means nothing without context" (Phase 1 setup)
3. "Now that you know what people earn... how long do they work for it?" (Phase 2 reveal)
4. "A Greek worker works 546 more hours than a German and earns 3× fewer Big Macs per hour" (Shock stat)
5. "Japan — the country you thought was underpaid — actually ranks #2" (Surprise)
6. "Americans work 55 extra 8-hour days per year compared to Danes. For 6% more Big Macs." (Closer)

**Tone:** Numbers speak. No editorializing. Let the viewer draw their own conclusions about which quadrant they'd want to live in.
