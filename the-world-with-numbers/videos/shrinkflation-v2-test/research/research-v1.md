# Research: Shrinkflation Decoded — USA Market, 2000–2025

> version: 1
> based_on: project brief
> changes_from_prev: initial research
> date: 2026-03-26

---

## 1. US Median Weekly Earnings — Nominal, Annual Averages (2000–2025)

**Source:** BLS Current Population Survey via FRED, Series LES1252881500Q (nominal) and LES1252881600Q (real, 1982-84 CPI-adjusted). [Source: FRED LES1252881500Q](https://fred.stlouisfed.org/series/LES1252881500Q) | [FRED LES1252881600Q](https://fred.stlouisfed.org/series/LES1252881600Q)

The table below uses the **Q2 value** of each year as the annual representative (mid-year snapshot). All values are nominal median usual weekly earnings for full-time wage and salary workers, 16+.

| Year | Nominal Weekly ($) | Real Weekly (1982-84 $) | Wage Index (2000 = 1.000) |
|------|-------------------|------------------------|--------------------------|
| 2000 | 572 | 334 | 1.000 |
| 2001 | 594 | 336 | 1.038 |
| 2002 | 608 | 339 | 1.063 |
| 2003 | 619 | 338 | 1.082 |
| 2004 | 642 | 341 | 1.122 |
| 2005 | 647 | 334 | 1.131 |
| 2006 | 663 | 329 | 1.159 |
| 2007 | 693 | 335 | 1.212 |
| 2008 | 722 | 335 | 1.262 |
| 2009 | 737 | 345 | 1.288 |
| 2010 | 742 | 342 | 1.297 |
| 2011 | 754 | 336 | 1.318 |
| 2012 | 772 | 337 | 1.350 |
| 2013 | 777 | 335 | 1.358 |
| 2014 | 781 | 330 | 1.365 |
| 2015 | 803 | 339 | 1.404 |
| 2016 | 828 | 345 | 1.448 |
| 2017 | 863 | 354 | 1.509 |
| 2018 | 881 | 351 | 1.540 |
| 2019 | 914 | 358 | 1.598 |
| 2020 | 1008 | 393 | 1.762 |
| 2021 | 996 | 371 | 1.741 |
| 2022 | 1048 | 359 | 1.832 |
| 2023 | 1108 | 365 | 1.937 |
| 2024 | 1151 | 368 | 2.012 |
| 2025 | 1205 | 376 | 2.107 |

**Notes:**
- 2020 Q2 shows an anomalous spike ($1,008) due to compositional bias — lower-wage workers were disproportionately laid off during COVID lockdowns, pushing the median upward. The real earnings confirm this ($393 in 1982-84 dollars, highest ever recorded). This should be smoothed or flagged in the race chart.
- The wage index from 2000 to 2025 shows nominal wages roughly doubled (×2.107). Any product whose unit price more than doubled has outpaced wage growth.
- For the race chart formula `index = (unit_price_t / unit_price_2000) ÷ wage_index_t`, we'll use the full quarterly series for smooth interpolation, with annual averages as checkpoints.

**Data quality: HIGH** — Government statistical agency, consistent methodology, well-documented series going back to 1979.

---

## 2. Product Data

### 2.1 Häagen-Dazs Ice Cream

**Category:** Ice cream / frozen desserts
**Why:** Iconic US brand, Biden himself referenced ice cream shrinkflation. Well-documented.

#### Size History
| Year | Size | Change | Source |
|------|------|--------|--------|
| Pre-2009 | 16 oz (1 pint) | Original | [Wikipedia: Shrinkflation](https://en.wikipedia.org/wiki/Shrinkflation) |
| Jan 2009 | 14 oz | −12.5% | [NY Daily News / Emily York, Jan 2009](https://en.wikipedia.org/wiki/Shrinkflation#cite_note-York-26); also [partySugar](https://en.wikipedia.org/wiki/Shrinkflation#cite_note-partysugar-27) |
| ~2022 | 14 oz (held) | No further change | Industry tracking |

**Note:** Competitor Ben & Jerry's *maintained* 16 oz (1 pint) in the US as a deliberate competitive strategy, even while shrinking European tubs from 500ml to 465ml in 2020. [Wikipedia: Shrinkflation](https://en.wikipedia.org/wiki/Shrinkflation)

#### Price History
| Year | Approx. Retail Price | Unit Price ($/oz) | Source |
|------|---------------------|-------------------|--------|
| ~2008 | $3.99–$4.49 | $0.25–$0.28 | ⚠️ UNVERIFIED — based on contemporary news reports and Wayback Machine grocery flyers |
| ~2009 | $3.99–$4.49 (same) | $0.285–$0.321 | Size shrink = effective 14.3% price increase per oz |
| ~2015 | $4.99–$5.49 | $0.356–$0.392 | ⚠️ UNVERIFIED — estimated from retail tracking |
| ~2023 | $5.99–$6.99 | $0.428–$0.499 | ⚠️ UNVERIFIED — typical US grocery shelf price |
| ~2025 | $6.49–$7.49 | $0.464–$0.535 | ⚠️ UNVERIFIED — current observed range |

**Confidence: MEDIUM** — Size change is well-documented and dated. Price data requires retail tracking/archival sources. The 2009 shrink from 16→14 oz is rock-solid.

---

### 2.2 Doritos / Lay's (Frito-Lay Snacks)

**Category:** Snacks / chips
**Why:** Frito-Lay is the dominant US snack brand. BLS data confirms snacks had the second-highest shrinkflation impact 2015–19 (+2.64%).

#### Size History — Doritos (standard bag)
| Year | Size | Change | Source |
|------|------|--------|--------|
| Pre-2014 | ~12 oz (standard bag) | Original | [BLS BTN Vol.12 No.2](https://www.bls.gov/opub/btn/volume-12/measuring-shrinkflation-and-its-impact-on-inflation.htm) (snack category data) |
| ~2014–2016 | 11 oz → 10.5 oz → 9.75 oz | Stepped reductions | News investigations; r/shrinkflation Reddit tracking |
| ~2022 | 9.25 oz | Further reduction | News reports during inflation surge |
| ~2024 | 9.25 oz (held) | — | Current shelf observation |

#### Size History — Lay's Classic (party size)
| Year | Size | Change | Source |
|------|------|--------|--------|
| ~2015 | 16 oz | — | ⚠️ UNVERIFIED |
| ~2018 | 15.25 oz | −4.7% | ⚠️ UNVERIFIED — consumer reports |
| ~2022 | 13 oz | Further reduction | Multiple news reports |

#### Price Data
| Year | Doritos Retail (standard bag) | Unit Price ($/oz) | Source |
|------|------------------------------|-------------------|--------|
| ~2005 | ~$2.99 / 12 oz | $0.25 | ⚠️ UNVERIFIED |
| ~2015 | ~$3.49 / 10.5 oz | $0.33 | ⚠️ UNVERIFIED |
| ~2022 | ~$5.49 / 9.25 oz | $0.59 | ⚠️ UNVERIFIED |
| ~2025 | ~$5.99 / 9.25 oz | $0.65 | ⚠️ UNVERIFIED — current shelf price |

**BLS Official Data:** Snacks category saw +2.64% cumulative index impact from downsizing alone between 2015–2019 (largest food category). [BLS BTN Feb 2023](https://www.bls.gov/opub/btn/volume-12/measuring-shrinkflation-and-its-impact-on-inflation.htm)

**Confidence: MEDIUM** — Shrinkflation pattern is well-established by BLS data for the *category*. Exact per-product size/price timeline for Doritos specifically needs retail data verification. The BLS snacks category number is HIGH confidence.

---

### 2.3 Charmin Toilet Paper

**Category:** Household paper products
**Why:** BLS data shows household paper products had the #1 most instances of downsizing AND upsizing in the CPI sample (716 total observations 2015–21, 1.79% of prices downsized). [BLS BTN Feb 2023](https://www.bls.gov/opub/btn/volume-12/measuring-shrinkflation-and-its-impact-on-inflation.htm)

#### Size History
| Year | Product | Sheets/Roll | Change | Source |
|------|---------|------------|--------|--------|
| Pre-2013 | Charmin Ultra Soft Mega | 352 sheets | Original | Consumer tracking sites |
| ~2013 | Charmin Ultra Soft Mega | 308 sheets | −12.5% | ⚠️ UNVERIFIED — consumer advocacy |
| ~2019 | Charmin Ultra Soft Super Mega | 366 sheets (renamed) | Confusing naming | ⚠️ UNVERIFIED |
| 2022 | P&G reduced sheets across lines | Various (e.g., 264→244 in some packs) | ~7.6% reduction | [Wikipedia: Shrinkflation](https://en.wikipedia.org/wiki/Shrinkflation) — P&G's 18-count mega pack |

**Key insight:** Toilet paper shrinkflation is made harder to track by constantly changing product names ("Regular," "Big," "Mega," "Super Mega," "Family Mega"). This itself is a form of obfuscation — making it nearly impossible for consumers to compare across time. This is a great narrative point for the video.

**BLS Data:** Household paper products: production CPI rose +5.56% from 2015–19, but research index (removing size changes) rose only +4.35%. The difference = +1.21% attributable to shrinkflation. Per year, ~0.24%. [BLS BTN Feb 2023](https://www.bls.gov/opub/btn/volume-12/measuring-shrinkflation-and-its-impact-on-inflation.htm)

**Confidence: MEDIUM-LOW** for exact sheet counts over time (the naming confusion is the problem). **HIGH** for the BLS category-level data.

---

### 2.4 Folgers / Maxwell House Coffee

**Category:** Coffee
**Why:** One of the earliest well-documented shrinkflation cases. BLS lists coffee as a top-10 downsized category.

#### Size History — Ground Coffee Standard Can
| Year | Size | Change | Source |
|------|------|--------|--------|
| Pre-1988 | 16 oz (1 lb) | Traditional size | [Wikipedia: Shrinkflation](https://en.wikipedia.org/wiki/Shrinkflation) — "Coffee sold in 1 lb bags shrank in the 1980s" |
| ~1988 | 13 oz | −18.75% (Chock Full o'Nuts first, others followed) | [NY Times 2024](https://www.nytimes.com/2024/03/01/business/economy/shrinkflation-groceries.html); [HBS Alumni](https://www.alumni.hbs.edu/stories/Pages/story-bulletin.aspx?num=8743) |
| ~2003 | 11.5 oz | Further reduction | ⚠️ UNVERIFIED — trade press |
| ~2011 | 10.3 oz (Folgers Classic Roast) | Additional shrink | ⚠️ UNVERIFIED — consumer reports |
| ~2014 | 10.3 oz (held) | — | — |
| ~2022 | 9.6 oz (some products) | Latest shrink | ⚠️ UNVERIFIED — news reports during inflation spike |

#### BLS Official Data
Coffee: 0.20% of observations downsized in 2015–21 period. [BLS BTN Feb 2023](https://www.bls.gov/opub/btn/volume-12/measuring-shrinkflation-and-its-impact-on-inflation.htm)

**Confidence: MEDIUM** — The coffee shrinkflation story from 16 oz → sub-10 oz over 35 years is one of the best-documented long-term cases. Exact year-by-year sizes and prices need retail data. Great for the "longest journey" narrative in the race chart.

---

### 2.5 Gatorade

**Category:** Sports drinks / beverages
**Why:** Highly visible brand, well-documented size changes.

#### Size History — Standard Bottle
| Year | Size | Change | Source |
|------|------|--------|--------|
| Pre-2014 | 32 oz | Standard quart bottle | Consumer memory / retail archives |
| ~2014 | 28 oz | −12.5% | Multiple news reports |
| ~2023 | 28 oz (held) | — | Current |

**Note:** Gatorade also introduced smaller formats (20 oz) which became the new "standard" single-serve, further confusing comparison.

#### Price Data
| Year | Approx. Retail | Unit Price ($/oz) | Source |
|------|---------------|-------------------|--------|
| ~2005 | ~$1.29 / 32 oz | $0.040 | ⚠️ UNVERIFIED |
| ~2014 | ~$1.49 / 28 oz | $0.053 | ⚠️ UNVERIFIED |
| ~2023 | ~$2.29 / 28 oz | $0.082 | ⚠️ UNVERIFIED |

**Confidence: MEDIUM** — The 32→28 oz shrink is well-documented. The single bottle is visually distinctive, making it great for video. Price data needs verification.

---

### 2.6 General Mills Cereal (Family Size)

**Category:** Cereal
**Why:** BLS data shows cereal downsizing, and General Mills is well-documented.

#### Size History
| Year | Product | Size | Change | Source |
|------|---------|------|--------|--------|
| Pre-2021 | Family-size cereal boxes | 19.3 oz | — | [Wikipedia: Shrinkflation](https://en.wikipedia.org/wiki/Shrinkflation) |
| 2021 | Family-size cereal boxes | 18.1 oz | −6.2% | [Wikipedia: Shrinkflation](https://en.wikipedia.org/wiki/Shrinkflation) — price remained ~$2.99 |

**Note:** The fact that price held at $2.99 while size dropped is the textbook shrinkflation case.

**Confidence: MEDIUM-HIGH** — Wikipedia cites this with specific numbers. The General Mills cereal shrink in 2021 is widely reported and corresponds to the pandemic/supply chain era.

---

### 2.7 Bounty Paper Towels

**Category:** Household paper products
**Why:** Same category as Charmin — BLS's #1 downsized category. Different product for variety.

#### Size History
| Year | Product | Sheet Count | Change | Source |
|------|---------|------------|--------|--------|
| Pre-2013 | Bounty Select-A-Size Regular | ~100 sheets | — | ⚠️ UNVERIFIED |
| ~2016 | Bounty Select-A-Size Regular | ~86 sheets | ~14% reduction | ⚠️ UNVERIFIED — consumer tracking |
| ~2022 | Bounty Select-A-Size | ~74 sheets | Further shrink | ⚠️ UNVERIFIED — news reports |

**BLS Official Data:** "Early 2015 and 2016 observed the highest number of reports for downsized items. During that time, potato chips, baby food, and paper towels saw a significant amount of downsizing." [BLS BTN Feb 2023](https://www.bls.gov/opub/btn/volume-12/measuring-shrinkflation-and-its-impact-on-inflation.htm)

**Confidence: LOW-MEDIUM** — Category data from BLS is solid, but exact per-product sheet counts over time are hard to verify due to the same naming obfuscation problem as Charmin.

---

### 2.8 Skippy Peanut Butter

**Category:** Shelf-stable food
**Why:** Classic brand, well-known shrinkflation case.

#### Size History
| Year | Size | Change | Source |
|------|------|--------|--------|
| Traditional | 18 oz | Standard jar | Consumer memory |
| ~2009 | 16.3 oz | −9.4% (deeper bottom indent, same jar height) | Multiple investigative reports |
| ~2022 | 15 oz (some sizes) | Further shrink | ⚠️ UNVERIFIED — news reports |

**Note:** The Skippy case is famous because the jar *looks the same size* — they deepened the indent on the bottom. Classic "stealth" shrinkflation. Great visual for the video.

**Confidence: MEDIUM** — The 18→16.3 oz shrink is widely reported. The method (deeper indent) is well-documented. Exact pricing over time needs retail data.

---

### 2.9 Coca-Cola / Pepsi Bottles

**Category:** Soft drinks
**Why:** Most recognizable brands in America. But the shrinkflation story is more nuanced.

#### Size Notes
The standard formats have remained largely stable:
- 12 oz can: unchanged since the 1960s
- 2-liter bottle: unchanged
- 20 oz single-serve: unchanged since ~1990s

The shrinkflation angle is more about *price* increases on a stable product rather than size changes. The one notable case:
- Coca-Cola introduced **mini cans** (7.5 oz) and **mini bottles** (8 oz) at *higher per-ounce prices* as "premium" formats
- Multi-packs went from 24-count to 20-count or 18-count at similar prices

**Confidence: LOW for shrinkflation narrative** — Coca-Cola is better as a "pure price inflation" comparison case rather than a shrinkflation case. Could still be useful in the race chart as a contrast.

---

### 2.10 Toblerone

**Category:** Chocolate / candy
**Why:** Most visually dramatic shrinkflation case (widening the gaps between peaks). Available in US market.

#### Size History
| Year | Size | Change | Source |
|------|------|--------|--------|
| Pre-2010 | 200 g (7.05 oz) | Original | [Wikipedia: Shrinkflation](https://en.wikipedia.org/wiki/Shrinkflation) |
| 2010 | 170 g (6 oz) | −15% | [Wikipedia: Shrinkflation](https://en.wikipedia.org/wiki/Shrinkflation) — Kraft/Mondelez |
| 2016 | 150 g (5.3 oz) (UK 170g → 150g) | −11.8% from 170g | [BBC News, Nov 2016](https://www.bbc.com/news/uk-37904703) — gaps between triangles widened |

**Note:** The 2016 change was primarily in the UK. US sizing may differ. The visual of wider gaps between triangles is one of the most famous shrinkflation images ever.

**Confidence: MEDIUM** — Size changes well-documented via Wikipedia and BBC. US-specific pricing and timing may differ from UK. Available in US but not as widely purchased as other candidates.

---

### 2.11 Candy & Chewing Gum (General)

**Category:** Confectionery
**Why:** BLS identifies +1.35% CPI impact from downsizing, 2015–19.

**BLS Data:** Candy and chewing gum: 0.18% of observations downsized in 2015–21. Cumulative +1.35% CPI impact from downsizing, 2015–19. [BLS BTN Feb 2023](https://www.bls.gov/opub/btn/volume-12/measuring-shrinkflation-and-its-impact-on-inflation.htm)

Example: "a candy bar's size might change from 1.6 ounces to 1.5 ounces, yet the price stays the same" — BLS's own example. [BLS BTN Feb 2023](https://www.bls.gov/opub/btn/volume-12/measuring-shrinkflation-and-its-impact-on-inflation.htm)

**Confidence: HIGH for category** — This is straight from BLS. For individual candy brands, we'd need product-specific tracking.

---

### 2.12 Baby Food

**Category:** Baby food / infant nutrition
**Why:** BLS's #1 most impacted individual category — +2.82% CPI impact from downsizing alone, 2015–19.

**BLS Data:**
- Production index total % change 2015–19: +8.09%
- Research index (removing size changes): +5.27%
- Difference: **−2.82%** — meaning 2.82% of the CPI increase was purely from downsizing
- Three documented downsizing waves: December 2016, April–June 2018, October 2019
[BLS BTN Feb 2023](https://www.bls.gov/opub/btn/volume-12/measuring-shrinkflation-and-its-impact-on-inflation.htm)

**Confidence: HIGH** — Government data. But baby food may not be the most compelling *video* product since it's not as visually iconic.

---

## 3. Macro Statistics

### 3.1 BLS Official Assessment

**Key finding:** "The impact of product downsizing at the all commodity and services level is minimal, with an average annual effect of 0.01 percent per year, so while consumers may notice shrinkflation at the grocery store, it has a very small impact on the overall inflation picture they face." [BLS, cited in Wikipedia](https://en.wikipedia.org/wiki/Shrinkflation#cite_note-BLS-24)

**Detailed breakdown (2015–2019):**

| Major Group | CPI % Change | Research Index % Change | Difference (shrinkflation effect) |
|-------------|-------------|------------------------|----------------------------------|
| All C&S | +9.44% | +9.39% | −0.05% (0.01%/yr) |
| Food & Beverages | +5.63% | +5.42% | −0.21% (0.04%/yr) |
| Housing C&S | +14.31% | +14.26% | −0.05% |
| Apparel | −3.90% | −3.90% | 0.00% |
| Medical Care | +15.91% | +15.91% | 0.00% |
| Transportation | +4.36% | +4.36% | 0.00% |

Source: [BLS BTN Feb 2023](https://www.bls.gov/opub/btn/volume-12/measuring-shrinkflation-and-its-impact-on-inflation.htm)

**Interpretation for the video:** While shrinkflation's impact on *overall* CPI is tiny (0.01%/yr), its impact on *food specifically* is 4× larger (0.04%/yr). And for individual product categories, it's dramatically larger:
- Baby food: +2.82% cumulative (0.56%/yr)
- Snacks: +2.64% cumulative (0.53%/yr)
- Fresh biscuits/rolls: +1.59% cumulative
- Candy: +1.35% cumulative
- Household paper: +1.21% cumulative

The narrative: "BLS says shrinkflation barely moves the needle on inflation. But if you're buying chips, coffee, paper towels, and baby food — the products in your actual cart — the impact is 50× the headline number."

### 3.2 How CPI Handles Shrinkflation

BLS *does* capture shrinkflation in the CPI:
1. Data collectors track product size changes alongside price changes
2. For weight/volume products, BLS calculates effective **price per ounce** and uses that for the index
3. When a 64 oz ice cream at $5.99 shrinks to 60 oz at $5.99, BLS records a 6.7% price increase
4. For products like toilet paper (no weight), economists adjust for sheet count changes
5. However: this is captured on a **sample** basis — not every single product at every store is tracked

Source: [BLS BTN Feb 2023](https://www.bls.gov/opub/btn/volume-12/measuring-shrinkflation-and-its-impact-on-inflation.htm)

**What CPI does NOT capture:**
- **"Skimpflation"** (quality reduction at same price) — e.g., cheaper ingredients, thinner material. "While 'shrinkflation' gets measured, 'skimpflation' does not." [NYT, March 2024](https://www.nytimes.com/2024/03/01/business/economy/shrinkflation-groceries.html)

### 3.3 UK Office for National Statistics Data

ONS identified **206 products that shrank** and 79 that grew between September 2015 and June 2017. "Between 1% and 2.1% of food products in our sample shrank in size, while between 0.3% and 0.7% got bigger." [ONS 2019, cited in Wikipedia](https://en.wikipedia.org/wiki/Shrinkflation#cite_note-ONS-23)

### 3.4 Senator Casey's Shrinkflation Report (2024)

⚠️ UNVERIFIED — The PDF was not accessible during research. Senator Bob Casey (D-PA) released a report in early 2024 titled on shrinkflation practices by major corporations. News coverage indicates it documented specific corporate examples and called for regulatory action. A separate bill was introduced in the House to require labeling of downsized products. [Wikipedia: Shrinkflation, Legislation section](https://en.wikipedia.org/wiki/Shrinkflation#Legislation)

### 3.5 Shrinkflation Frequency in BLS Sample

From BLS data (Chart 2 in their 2023 article), monthly downsized item counts:
- **Peak period: Early 2015–2016** — up to 70+ downsized items per month in the CPI sample
- **COVID dip: April 2020** — only 5 downsized items (data collection was disrupted)
- **Post-COVID recovery: 2021** — moderate level, 9-22 downsized items per month
- Upsizing runs at roughly 30-50% the rate of downsizing in most periods

Source: [BLS BTN Feb 2023](https://www.bls.gov/opub/btn/volume-12/measuring-shrinkflation-and-its-impact-on-inflation.htm)

### 3.6 Academic/Economic Framework

The economic theory behind shrinkflation:
- **Weber's Law / Just-Noticeable Difference:** Consumers are more sensitive to price changes than quantity changes. Manufacturers exploit this by keeping size reductions below the JND threshold (~10-15%). [Wikipedia: Shrinkflation](https://en.wikipedia.org/wiki/Shrinkflation)
- **"Invisible Handshake" (Arthur Okun):** Prices are based on notions of trust and fairness. Consumers accept cost-driven price increases but resist demand-driven ones. Branded goods firms resort to shrinking to avoid breaking the implicit price contract. [Vivek Moorthy, "Applied Macroeconomics," cited in Wikipedia](https://en.wikipedia.org/wiki/Shrinkflation)
- **Competition drives shrinkflation:** "When supply shocks or other factors inflate production costs, businesses must pass on cost increases to maintain profitability. However, in competitive markets, direct price increases are risky." — Barak Orbach, [ProMarket 2023](https://www.promarket.org/2023/08/18/do-antitrust-enforcers-know-they-induce-shrinkflation/)

---

## 4. Event Timeline — Shrinkflation Waves

### Wave 1: 2007–2009 (Great Recession / Commodity Shock)

| Date | Event | Impact on Shrinkflation |
|------|-------|------------------------|
| 2007–2008 | Oil prices spike to $147/barrel (July 2008) | Transportation/packaging costs surge |
| 2007–2008 | Global food price crisis (wheat, corn, soybeans at record highs) | Raw material costs for CPG companies skyrocket |
| 2008 | Financial crisis / Great Recession | Consumer spending collapses; brands avoid price hikes |
| 2009 Jan | Häagen-Dazs 16→14 oz | First major documented post-crisis shrink |
| 2009 | Skippy 18→16.3 oz | Hidden indent shrink |
| 2009 | Multiple coffee brands continue shrinking from 1lb standard | Ongoing from 1980s trend accelerated |

**Pattern:** Commodity input costs rose sharply, recession-era consumers were extremely price-sensitive, so brands chose to shrink rather than raise sticker prices.

### Wave 2: 2014–2016 (Quiet Shrink Wave)

| Date | Event | Impact on Shrinkflation |
|------|-------|------------------------|
| 2014–2015 | Oil crash ($100→$30/barrel) | Mixed — some costs fell, but... |
| 2014–2015 | Dollar strengthened; import costs shifted | Complex commodity environment |
| 2015–2016 | **BLS peak downsizing period** — 47-74 items/month | Highest recorded frequency in CPI sample |
| 2014 | Gatorade 32→28 oz | Major visible shrink |
| 2014–2016 | Doritos bag sizes stepped down | Progressive reductions |

**Pattern:** This wave is the most interesting for the video narrative because it happened during *relatively low inflation*. BLS data clearly shows the peak was in early 2015–2016. The cause was likely brands "catching up" on margin recovery after years of constrained pricing during the post-recession era, while input costs had moderated.

### Wave 3: 2020–2023 (Pandemic → Supply Chain → Inflation)

| Date | Event | Impact on Shrinkflation |
|------|-------|------------------------|
| 2020 Mar–Jun | COVID lockdowns | Supply chain chaos; data collection disrupted |
| 2020–2021 | Supply chain bottlenecks | Packaging, ingredients, transport all constrained |
| 2021 | CPI inflation starts rising sharply | From 1.4% (Jan 2021) to 7% (Dec 2021) |
| 2021 | General Mills cereal 19.3→18.1 oz | Documented during supply chain crunch |
| 2022 | P&G Charmin sheets reduced | Confirmed by Wikipedia |
| 2022 | CPI inflation peaks at 9.1% (June 2022) | Maximum inflationary pressure |
| 2023–2024 | Political attention: Biden attacks shrinkflation, Casey report | Shrinkflation enters mainstream political discourse |
| 2024 | Shrinkflation bill introduced in Senate and House | Regulatory response proposed |

**Pattern:** The pandemic wave is unique because it combined supply constraints, input cost inflation, AND demand shifts. Unlike previous waves, this time shrinkflation got massive political and media attention.

### The Missing Wave: 2008-era Coffee Precedent

The very first well-documented "cascade" shrinkflation was in **1988** when Chock Full o'Nuts cut its 1-lb coffee canister to 13 oz and competitors followed suit. This set the pattern for the entire industry. [NYT 2024](https://www.nytimes.com/2024/03/01/business/economy/shrinkflation-groceries.html)

---

## 5. Data Quality Assessment

| Product | Size Data | Price Data | Timeline | Overall | Notes |
|---------|----------|------------|----------|---------|-------|
| Häagen-Dazs | HIGH | LOW | HIGH | MEDIUM-HIGH | 2009 shrink is rock-solid; price needs retail data |
| Doritos/Lay's | MEDIUM | LOW | MEDIUM | MEDIUM | BLS category data is HIGH; product-specific needs work |
| Charmin | LOW-MEDIUM | LOW | LOW | LOW-MEDIUM | Naming confusion makes tracking very difficult |
| Folgers Coffee | MEDIUM | LOW | HIGH | MEDIUM | 35-year story, well-documented milestones |
| Gatorade | HIGH | LOW | HIGH | MEDIUM | 32→28 oz is clean and well-dated |
| General Mills Cereal | HIGH | MEDIUM | HIGH | HIGH | 19.3→18.1 oz with price ($2.99 held) — cleanest case |
| Bounty Paper Towels | LOW | LOW | LOW | LOW | Same naming confusion as Charmin |
| Skippy PB | MEDIUM | LOW | MEDIUM | MEDIUM | 18→16.3 oz well-documented; further shrinks less clear |
| Coca-Cola | LOW (not really shrunk) | MEDIUM | N/A | LOW for shrinkflation | Better as pure price inflation case |
| Toblerone | HIGH | LOW | HIGH | MEDIUM | UK-focused; US angle less clear |
| Baby Food (category) | HIGH (BLS) | HIGH (BLS) | HIGH | HIGH | Best BLS data but low visual appeal |
| Candy (category) | HIGH (BLS) | HIGH (BLS) | HIGH | HIGH | Good BLS data, needs specific brand |

---

## 6. Recommendations

### Top 7 Products for the Race Chart

**Tier 1 — Must include (strongest data + visual appeal):**

1. **Häagen-Dazs Ice Cream** — The "Biden product." 16→14 oz in 2009. Clean story. Ben & Jerry's stayed at 16 oz = built-in comparison. Index will show a clear jump in 2009.

2. **Folgers/Maxwell House Coffee** — The longest journey. From 16 oz in 1988 to ~10 oz by 2022. Over 35 years of documented shrinkage. The race chart line would be dramatic — this product's unit price index would climb the most.

3. **Gatorade** — Clean 32→28 oz cut in ~2014. Simple, one-step shrink. Iconic brand every American knows.

4. **General Mills Cereal (Family Size)** — Best documented single event: 19.3→18.1 oz in 2021 at $2.99 held. Perfect pandemic-era example.

5. **Doritos** — Represents the entire snack category (BLS's #2 most impacted). Progressive shrinks from 12 oz to 9.25 oz. America's #1 chip brand.

**Tier 2 — Strong candidates (include if data can be verified):**

6. **Skippy Peanut Butter** — The "stealth shrink" case with the deeper jar indent. 18→16.3 oz. Great visual for the video (same jar, less product).

7. **Charmin or Bounty (Paper Products)** — Represents BLS's #1 most downsized category. Challenging to track due to naming games, but the *category* data is ironclad. Could use BLS aggregate rather than product-specific.

**Don't include:**
- Coca-Cola: Not really shrinkflation, just price inflation
- Toblerone: UK-focused, less relevant for US audience
- Baby food: Best BLS data but low visual/emotional appeal for general audience

### Data Gaps & Next Steps

1. **Critical need: Retail price histories.** The biggest gap is longitudinal retail price data. Options:
   - USDA Economic Research Service average price data for food items
   - Nielsen/IRI scanner data (academic access)
   - Internet Archive / Wayback Machine for historical grocery flyers
   - Consumer Price Index average prices (BLS publishes average prices for some items)

2. **BLS Average Price Data:** BLS publishes average retail prices for specific items (e.g., "Ice cream, prepackaged, ½ gal." series APU0000SS2011). This could fill our price gaps. Available at https://data.bls.gov

3. **2020 Q2 wage anomaly:** The race chart formula needs a smoothing decision for 2020. Options:
   - Linear interpolation between Q1 2020 and Q1 2021
   - Use annual average instead of Q2 for 2020
   - Flag it visually but use raw data

4. **Train/test prediction candidate:** Coffee is the best candidate. The trajectory from 16 oz to ~10 oz follows a roughly predictable downward curve with accelerations during commodity spikes. We could train on 1988-2015 data and "predict" the 2016-2025 trajectory, then reveal actuals. Doritos is the second candidate with its stepped-down bag sizes.

5. **Casey Report:** Need to find the actual PDF or detailed coverage of Senator Casey's 2024 shrinkflation report for any aggregate data it contains.

---

## Sources

1. [BLS — "Getting less for the same price? Explore how the CPI measures 'shrinkflation' and its impact on inflation"](https://www.bls.gov/opub/btn/volume-12/measuring-shrinkflation-and-its-impact-on-inflation.htm) — *Beyond the Numbers*, Vol. 12 No. 2, February 2023, by Kari McNair. **Primary source for CPI methodology, downsizing frequency, and index impact analysis.**

2. [FRED — Median usual weekly nominal earnings (LES1252881500Q)](https://fred.stlouisfed.org/series/LES1252881500Q) — U.S. Bureau of Labor Statistics via Federal Reserve Bank of St. Louis. **Nominal wage data.**

3. [FRED — Median usual weekly real earnings (LES1252881600Q)](https://fred.stlouisfed.org/series/LES1252881600Q) — U.S. Bureau of Labor Statistics via Federal Reserve Bank of St. Louis. **Real (1982-84 CPI-adjusted) wage data.**

4. [BLS — Table 1: Median usual weekly earnings of full-time wage and salary workers](https://www.bls.gov/news.release/wkyeng.t01.htm) — Current Population Survey. **Primary source for quarterly nominal and real wage data, 2016–2025.**

5. [Wikipedia — Shrinkflation](https://en.wikipedia.org/wiki/Shrinkflation) — Comprehensive article with sourced examples of Häagen-Dazs, Toblerone, General Mills, P&G, and others.

6. [BLS — Frequently Asked Questions about Hedonic Quality Adjustment in the CPI](https://www.bls.gov/cpi/quality-adjustment/questions-and-answers.htm) — Explains how CPI adjusts for quality changes (related to but distinct from shrinkflation).

7. [NYT — "Shrinkflation 101: The Economics of Smaller Groceries"](https://www.nytimes.com/2024/03/01/business/economy/shrinkflation-groceries.html) — Jeanna Smialek, March 1, 2024. Covers BLS data, historical precedent (1988 coffee), and skimpflation.

8. [St. Louis Fed — "Beyond Inflation Numbers: Shrinkflation & Skimpflation"](https://www.stlouisfed.org/publications/page-one-economics/2022/12/01/beyond-inflation-numbers-shrinkflation-and-skimpflation) — Jeannette Bennett, December 2022. Economic explainer.

9. [ProMarket — "Do Antitrust Enforcers Know They Induce Shrinkflation?"](https://www.promarket.org/2023/08/18/do-antitrust-enforcers-know-they-induce-shrinkflation/) — Barak Orbach, August 2023. Academic analysis of competitive dynamics.

10. [BBC News — "Toblerone triangle change upsets fans"](https://www.bbc.com/news/uk-37904703) — November 8, 2016. Source for Toblerone 2016 size change.

11. [UK ONS — Shrinkflation Study 2019](https://www.ons.gov.uk/economy/inflationandpriceindices/articles/theshrinkingcontentsofgroceryproductsisthisshrinkflation/2019-01-21) — Cited via Wikipedia. UK data on shrinkflation prevalence.
