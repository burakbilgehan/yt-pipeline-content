# Research: Shrinkflation Decoded — USA Market, 2000–2025

> version: 2
> based_on: research-v1
> changes_from_prev: Added full BLS average price data (2000-2025) for 6 products, computed real unit price indices, resolved BLS unit normalization insight, developed race chart data model, added narrative analysis, resolved 2020 wage anomaly, developed prediction segment plan
> date: 2026-03-26

---

## 1. US Median Weekly Earnings — Nominal (2000–2025)

**Source:** BLS Current Population Survey via FRED, Series LES1252881500Q (nominal). [FRED LES1252881500Q](https://fred.stlouisfed.org/series/LES1252881500Q)

Q2 values used as annual representatives.

| Year | Nominal Weekly ($) | Wage Index (2000 = 1.000) |
|------|-------------------|--------------------------|
| 2000 | 572 | 1.000 |
| 2001 | 594 | 1.038 |
| 2002 | 608 | 1.063 |
| 2003 | 619 | 1.082 |
| 2004 | 642 | 1.122 |
| 2005 | 647 | 1.131 |
| 2006 | 663 | 1.159 |
| 2007 | 693 | 1.212 |
| 2008 | 722 | 1.262 |
| 2009 | 737 | 1.288 |
| 2010 | 742 | 1.297 |
| 2011 | 754 | 1.318 |
| 2012 | 772 | 1.350 |
| 2013 | 777 | 1.358 |
| 2014 | 781 | 1.365 |
| 2015 | 803 | 1.404 |
| 2016 | 828 | 1.448 |
| 2017 | 863 | 1.509 |
| 2018 | 881 | 1.540 |
| 2019 | 914 | 1.598 |
| 2020 | 1008 | 1.762 |
| 2021 | 996 | 1.741 |
| 2022 | 1048 | 1.832 |
| 2023 | 1108 | 1.937 |
| 2024 | 1151 | 2.012 |
| 2025 | 1205 | 2.107 |

### 2020 Q2 Wage Anomaly — Resolution

**Decision: Use raw data + visual flag in race chart.**

The 2020 Q2 spike ($1,008 vs $914 in 2019 Q2) is real compositional bias — lower-wage workers disproportionately lost jobs during COVID, pushing the *remaining workers'* median upward. This creates a temporary dip in all RUPI values for 2020.

**Why NOT smooth:** Smoothing would be editorializing the data. The BLS published this number. For the race chart, we'll use the actual value but add a visual annotation (dotted line or callout) explaining the anomaly. This is more honest and more interesting for the viewer.

**Impact on race chart:** All products appear to "dip" in 2020 and "recover" in 2021. This is actually a wage artifact, not a food price artifact. The annotation reads: *"2020: Lower-wage workers lost jobs → median wage jumped → everything looks cheaper. The wages were fake; the prices were real."*

---

## 2. BLS Average Price Data (2000–2025)

### 2.1 Data Source & Methodology

**Source:** BLS Average Price Data, retrieved via BLS Public Data API v2. [BLS Average Price Data](https://www.bls.gov/data/#prices)

All prices are national urban averages (U.S. City Average, area code 0000), collected monthly by BLS field representatives in 75 urban areas for the CPI program.

**Critical insight: BLS prices are UNIT-NORMALIZED.** Each series reports price per standard unit (per pound, per gallon, per dozen, etc.) regardless of actual package size. When a 16oz coffee can shrinks to 10oz at the same sticker price, BLS calculates the effective per-pound price and records that. **This means BLS average price data already captures shrinkflation in the price numbers.** A shrinking package at constant sticker price shows up as a rising per-unit price.

### 2.2 Series Identification

| Product | BLS Series ID | Unit | Data Range | Gaps |
|---------|--------------|------|------------|------|
| Coffee, ground roast | APU0000717311 | per lb | 2000–2025 | 2008 (all), 2009 (partial), 2019 (partial) |
| Eggs, Grade A, large | APU0000708111 | per dozen | 2000–2025 | None |
| Potato chips | APU0000718311 | per 16 oz | 2000–2025 | None |
| Milk, whole, fortified | APU0000709112 | per gallon | 2000–2025 | None |
| Peanut butter, creamy | APU0000710211 | per lb | 2000–2025 | None |
| Ice cream, prepackaged | APU0000710212 | per ½ gallon | 2000–2025 | None |

**Coffee data gaps:**
- 2008: BLS returned "No Data Available" — series may have been temporarily discontinued or reclassified
- 2009: Only December data point ($3.669)
- 2019: Only Oct–Dec data ($4.174, $4.197, $4.053)

⚠️ ESTIMATED values for coffee gaps (used only in race chart, flagged visually):
- 2008: ~$3.80 (estimated; all other food commodities show 2008 spike)
- 2009: ~$3.67 (based on Dec 2009 data point $3.669)
- 2019: ~$4.14 (based on Q4 2019 average $4.141; consistent with 2018 and 2020 levels)

### 2.3 Annual Average Prices

Computed from monthly BLS data (arithmetic mean of available months per year; years with <6 months excluded).

| Year | Coffee $/lb | Eggs $/doz | Chips $/16oz | Milk $/gal | PB $/lb | Ice Cream $/½gal | Wage Index |
|------|------------|------------|-------------|------------|---------|------------------|------------|
| 2000 | 3.450 | 0.913 | 3.360 | 2.781 | 3.698 | 3.830 | 1.000 |
| 2001 | 3.093 | 0.929 | 3.426 | 2.884 | 3.871 | 4.027 | 1.038 |
| 2002 | 2.924 | 1.032 | 3.356 | 2.757 | 3.881 | 4.218 | 1.063 |
| 2003 | 2.916 | 1.244 | 3.499 | 2.761 | 3.771 | 3.948 | 1.082 |
| 2004 | 2.849 | 1.340 | 3.403 | 3.156 | 3.984 | 4.273 | 1.122 |
| 2005 | 3.262 | 1.218 | 3.368 | 3.187 | 3.881 | 4.381 | 1.131 |
| 2006 | 3.203 | 1.306 | 3.466 | 3.081 | 3.720 | 4.255 | 1.159 |
| 2007 | 3.469 | 1.676 | 3.530 | 3.503 | 3.839 | 4.230 | 1.212 |
| 2008 | ⚠️ ~3.80 | 1.987 | 4.021 | 3.795 | 4.042 | 4.725 | 1.262 |
| 2009 | ⚠️ ~3.67 | 1.664 | 4.569 | 3.109 | 3.903 | 4.669 | 1.288 |
| 2010 | 3.906 | 1.660 | 4.642 | 3.258 | 3.910 | 4.710 | 1.297 |
| 2011 | 5.191 | 1.769 | 4.968 | 3.572 | 4.066 | 5.419 | 1.318 |
| 2012 | 5.676 | 1.838 | 4.986 | 3.493 | 4.188 | 5.625 | 1.350 |
| 2013 | 5.453 | 1.910 | 4.665 | 3.462 | 4.175 | 5.558 | 1.358 |
| 2014 | 4.990 | 2.018 | 4.371 | 3.694 | 4.494 | 5.543 | 1.365 |
| 2015 | 4.720 | 2.469 | 4.408 | 3.419 | 4.456 | 5.379 | 1.404 |
| 2016 | 4.393 | 1.684 | 4.461 | 3.204 | 4.367 | 5.235 | 1.448 |
| 2017 | 4.453 | 1.467 | 4.409 | 3.226 | 4.248 | 4.895 | 1.509 |
| 2018 | 4.302 | 1.742 | 4.446 | 2.896 | 4.007 | 5.135 | 1.540 |
| 2019 | ⚠️ ~4.14 | 1.396 | 4.485 | 3.036 | 3.876 | 5.308 | 1.598 |
| 2020 | 4.433 | 1.506 | 4.922 | 3.318 | 4.104 | 5.496 | 1.762 |
| 2021 | 4.705 | 1.674 | 5.076 | 3.544 | 4.036 | 5.440 | 1.741 |
| 2022 | 5.891 | 2.857 | 5.827 | 4.091 | 4.401 | 5.762 | 1.832 |
| 2023 | 6.156 | 2.796 | 6.445 | 4.027 | 4.756 | 5.823 | 1.937 |
| 2024 | 6.322 | 3.171 | 6.455 | 3.984 | 4.893 | 5.664 | 2.012 |
| 2025 | 8.180 | 4.252 | 6.705 | 4.067 | 4.947 | 5.842 | 2.107 |

---

## 3. Real Unit Price Index (RUPI) — The Race Chart Data

### 3.1 Formula

```
RUPI_t = (nominal_unit_price_t / nominal_unit_price_2000) ÷ wage_index_t
```

- **RUPI = 1.000** → product costs the same fraction of your wage as in 2000
- **RUPI > 1.000** → product costs MORE relative to your wages than in 2000
- **RUPI < 1.000** → product costs LESS relative to your wages than in 2000

### 3.2 Computed RUPI Values

| Year | Coffee | Eggs | Chips | Milk | PB | Ice Cream |
|------|--------|------|-------|------|----|-----------|
| 2000 | 1.000 | 1.000 | 1.000 | 1.000 | 1.000 | 1.000 |
| 2001 | 0.864 | 0.980 | 0.982 | 0.999 | 1.008 | 1.013 |
| 2002 | 0.797 | 1.063 | 0.940 | 0.933 | 0.987 | 1.036 |
| 2003 | 0.781 | 1.259 | 0.962 | 0.918 | 0.942 | 0.953 |
| 2004 | 0.736 | 1.308 | 0.903 | 1.011 | 0.960 | 0.994 |
| 2005 | 0.836 | 1.180 | 0.886 | 1.013 | 0.928 | 1.011 |
| 2006 | 0.801 | 1.234 | 0.890 | 0.956 | 0.868 | 0.959 |
| 2007 | 0.830 | 1.515 | 0.867 | 1.039 | 0.857 | 0.911 |
| 2008 | ⚠️ ~0.87 | 1.725 | 0.948 | 1.081 | 0.866 | 0.978 |
| 2009 | ⚠️ ~0.83 | 1.415 | 1.056 | 0.868 | 0.819 | 0.946 |
| 2010 | 0.873 | 1.402 | 1.065 | 0.903 | 0.815 | 0.948 |
| 2011 | 1.142 | 1.470 | 1.122 | 0.975 | 0.834 | 1.074 |
| 2012 | 1.219 | 1.491 | 1.099 | 0.930 | 0.839 | 1.088 |
| 2013 | 1.164 | 1.541 | 1.022 | 0.917 | 0.831 | 1.069 |
| 2014 | 1.060 | 1.619 | 0.953 | 0.973 | 0.890 | 1.060 |
| 2015 | 0.974 | 1.926 | 0.934 | 0.876 | 0.858 | 1.000 |
| 2016 | 0.879 | 1.274 | 0.917 | 0.796 | 0.816 | 0.944 |
| 2017 | 0.855 | 1.065 | 0.870 | 0.769 | 0.761 | 0.847 |
| 2018 | 0.810 | 1.239 | 0.859 | 0.676 | 0.704 | 0.871 |
| 2019 | ⚠️ ~0.75 | 0.957 | 0.835 | 0.683 | 0.656 | 0.867 |
| 2020 | 0.729 | 0.936 | 0.831 | 0.677 | 0.630 | 0.814 |
| 2021 | 0.783 | 1.053 | 0.868 | 0.732 | 0.627 | 0.816 |
| 2022 | 0.932 | 1.708 | 0.947 | 0.803 | 0.650 | 0.821 |
| 2023 | 0.921 | 1.581 | 0.990 | 0.748 | 0.664 | 0.785 |
| 2024 | 0.911 | 1.726 | 0.955 | 0.712 | 0.658 | 0.735 |
| 2025 | 1.125 | 2.210 | 0.947 | 0.694 | 0.635 | 0.724 |

### 3.3 Sample Index Calculations (Shown Math)

**Eggs, 2025:**
```
Price_2025 = $4.252/doz, Price_2000 = $0.913/doz
Nominal ratio = 4.252 / 0.913 = 4.657
Wage index = 2.107
RUPI = 4.657 / 2.107 = 2.210
→ Eggs cost 2.21× as much of your wage as in 2000
```

**Coffee, 2025:**
```
Price_2025 = $8.180/lb, Price_2000 = $3.450/lb
Nominal ratio = 8.180 / 3.450 = 2.371
Wage index = 2.107
RUPI = 2.371 / 2.107 = 1.125
→ Coffee costs 12.5% more of your wage than in 2000
```

**Milk, 2025:**
```
Price_2025 = $4.067/gal, Price_2000 = $2.781/gal
Nominal ratio = 4.067 / 2.781 = 1.462
Wage index = 2.107
RUPI = 1.462 / 2.107 = 0.694
→ Milk costs 31% LESS of your wage than in 2000
```

**Chips, 2025:**
```
Price_2025 = $6.705/16oz, Price_2000 = $3.360/16oz
Nominal ratio = 6.705 / 3.360 = 1.996
Wage index = 2.107
RUPI = 1.996 / 2.107 = 0.947
→ Chips cost 5.3% less of your wage than in 2000 (per unit weight)
```

---

## 4. Race Chart Narrative Analysis

### 4.1 The Surprise Finding

The data tells a story that contradicts the popular narrative:

**Most grocery products are CHEAPER relative to wages than they were in 2000.** When you normalize for wage growth, only eggs and (recently) coffee actually cost more of your paycheck. Chips, ice cream, peanut butter, and milk have all become more affordable per unit.

But this misses the lived experience. Here's why:

### 4.2 The Shrinkflation Perception Gap

BLS prices are per standardized unit (per pound, per gallon). The unit prices haven't outpaced wages for most items. But shrinkflation means **you get fewer units per package**:

| Product | ~2000 Package | ~2025 Package | Size Change | Per-Unit RUPI |
|---------|--------------|--------------|-------------|---------------|
| Chips (Doritos) | ~12 oz bag @ ~$3.00 | ~9.25 oz bag @ ~$6.00 | −23% | 0.947 |
| Ice cream (Häagen-Dazs) | 16 oz @ ~$3.50 | 14 oz @ ~$6.50 | −12.5% | 0.724 |
| Coffee (Folgers) | 16 oz (1 lb) can @ ~$3.50 | 10.3 oz can @ ~$5.50 | −36% | 1.125 |
| Peanut butter (Skippy) | 18 oz jar @ ~$3.00 | 16.3 oz jar @ ~$5.00 | −9.4% | 0.635 |

**The key narrative:** The per-unit price is only part of the story. The other part is that each purchase event gets you less product. Your grocery bill goes up because (a) prices per unit rose modestly, AND (b) you need to buy more packages to get the same total quantity.

**For the video:** This is the "aha" moment. Show the race chart with per-unit RUPIs (most hovering near or below 1.0), then reveal: "But wait — here's what your actual bag looks like..."

### 4.3 Category Narratives

**🥚 Eggs — The Runaway Leader**
- RUPI 2025: **2.210** (cost 121% more of your wage than in 2000)
- This is NOT shrinkflation — a dozen is still a dozen
- Driven entirely by supply shocks: avian flu epidemics (2003-04, 2015, 2022-23, 2024-25)
- Eggs are the purest "real price inflation" case — no size games, just biology and disease
- Eggs serve as the dramatic visual "villain" in the race chart, pulling away from the pack

**☕ Coffee — The Slow Boil (Now Erupting)**
- RUPI 2025: **1.125** (13% more of your wage than in 2000)
- Was actually CHEAPER relative to wages from 2001-2020 (dipped as low as 0.73)
- Massive surge 2024-2025 due to Brazilian drought + Vietnamese crop failure + global demand
- Crossed back above 1.0 in 2025 — the first time since ~2014
- **Also** the longest shrinkflation journey: 16 oz → 10.3 oz over 35 years (−36%)
- Coffee has BOTH real price inflation AND heavy shrinkflation

**🥔 Chips — The Stealth Fighter**
- RUPI 2025: **0.947** (5% cheaper per unit weight than in 2000)
- Per-unit price barely moved vs wages over 25 years!
- But BLS's second-most-impacted shrinkflation category (+2.64% cumulative 2015-19)
- Package went from ~12 oz to ~9.25 oz (−23%)
- This is PURE shrinkflation — the unit price is fine, the package is shrinking

**🥛 Milk — Wages Won**
- RUPI 2025: **0.694** (31% cheaper relative to wages)
- Steady decline since 2014. Milk has genuinely become more affordable
- No significant shrinkflation (a gallon is still a gallon)
- Serves as a "control product" in the race chart

**🥜 Peanut Butter — The Steepest Decline**
- RUPI 2025: **0.635** (37% cheaper relative to wages)
- Despite the famous Skippy 18→16.3 oz shrink in 2009
- Per-pound prices simply haven't kept up with wage growth
- Another good control product

**🍦 Ice Cream — Size Change Absorbed**
- RUPI 2025: **0.724** (28% cheaper relative to wages per ½ gallon)
- Even WITH the Häagen-Dazs 16→14 oz shrink in 2009
- BLS normalizes to per-½-gallon, so the shrinkflation is already in the data
- The price per ½ gallon has been declining relative to wages since 2014

### 4.4 Three-Act Race Chart Structure

**Act 1 (2000-2009): The Great Divergence**
- Most products hover near 1.0 or drift down
- Eggs spike during 2003-2004 and 2007-2008 (early avian flu + commodity crisis)
- Chips jump above 1.0 in 2009 (post-recession price adjustments)
- Coffee drops to 0.73-0.80 range (cheap coffee era)

**Act 2 (2010-2019): The Shrinkflation Decade**
- Eggs remain volatile but elevated (1.0-1.9 range)
- Coffee spikes to 1.22 in 2012 (coffee commodity boom) then falls back
- Everything else slowly drifts downward
- By 2019, most items at 0.65-0.87 — wages clearly winning
- The "calm before the storm" — this is when most shrinkflation was happening quietly

**Act 3 (2020-2025): Chaos and Bifurcation**
- 2020: COVID wage anomaly → everything dips (annotation needed)
- 2022: Inflation surge → eggs explode to 1.71, everything rises
- 2023-2024: Most items stabilize or decline; eggs stay high
- 2025: Eggs hit 2.21 (avian flu), coffee crosses back above 1.0
- Final frame: two products above the line, four below

---

## 5. BLS Shrinkflation Methodology (From v1, Updated)

### 5.1 Official BLS Assessment

"The impact of product downsizing at the all commodity and services level is minimal, with an average annual effect of 0.01 percent per year." [BLS BTN Feb 2023](https://www.bls.gov/opub/btn/volume-12/measuring-shrinkflation-and-its-impact-on-inflation.htm)

But at the individual category level:

| Category | Cumulative CPI Impact from Downsizing (2015-19) | Annual Rate |
|----------|--------------------------------------------------|-------------|
| Baby food | +2.82% | 0.56%/yr |
| Snacks | +2.64% | 0.53%/yr |
| Fresh biscuits/rolls | +1.59% | 0.32%/yr |
| Candy & chewing gum | +1.35% | 0.27%/yr |
| Household paper products | +1.21% | 0.24%/yr |
| **All Food & Beverages** | **+0.21%** | **0.04%/yr** |
| **All Commodities & Services** | **+0.05%** | **0.01%/yr** |

Source: [BLS BTN Feb 2023](https://www.bls.gov/opub/btn/volume-12/measuring-shrinkflation-and-its-impact-on-inflation.htm)

### 5.2 How CPI Captures Shrinkflation

BLS data collectors track both price AND quantity:
1. For weight/volume products → calculate effective price per standard unit
2. A 64oz ice cream at $5.99 shrinking to 60oz at $5.99 → BLS records 6.7% price increase
3. For count products (toilet paper sheets) → economists adjust for count changes
4. **This is captured in our BLS average price data** — the unit-normalized prices already include shrinkflation effects

What CPI does NOT capture: **"Skimpflation"** (quality reduction at same price/size). [NYT, March 2024](https://www.nytimes.com/2024/03/01/business/economy/shrinkflation-groceries.html)

---

## 6. Product Size Change Histories

These size changes are ALREADY reflected in the BLS per-unit prices above. They're documented here as narrative overlay for the race chart.

### 6.1 Coffee (Ground, Standard Can)

| Year | Size | Change | Source |
|------|------|--------|--------|
| Pre-1988 | 16 oz (1 lb) | Traditional | [Wikipedia: Shrinkflation](https://en.wikipedia.org/wiki/Shrinkflation) |
| ~1988 | 13 oz | −18.75% (Chock Full o'Nuts first) | [NYT 2024](https://www.nytimes.com/2024/03/01/business/economy/shrinkflation-groceries.html); [HBS Alumni](https://www.alumni.hbs.edu/stories/Pages/story-bulletin.aspx?num=8743) |
| ~2003 | 11.5 oz | Further reduction | ⚠️ UNVERIFIED — trade press |
| ~2011 | 10.3 oz (Folgers Classic Roast) | Additional shrink | ⚠️ UNVERIFIED |
| ~2022 | 9.6 oz (some products) | Latest shrink | ⚠️ UNVERIFIED |

**Cumulative from 1 lb standard: −40% over 35 years**

### 6.2 Ice Cream (Häagen-Dazs)

| Year | Size | Change | Source |
|------|------|--------|--------|
| Pre-2009 | 16 oz (1 pint) | Original | [Wikipedia: Shrinkflation](https://en.wikipedia.org/wiki/Shrinkflation) |
| Jan 2009 | 14 oz | −12.5% | [NY Daily News / Emily York, Jan 2009](https://en.wikipedia.org/wiki/Shrinkflation#cite_note-York-26) |
| 2009–present | 14 oz (held) | No further change | Industry tracking |

**Note:** Ben & Jerry's maintained 16 oz in US — competitive differentiation. [Wikipedia](https://en.wikipedia.org/wiki/Shrinkflation)

### 6.3 Chips (Doritos Standard Bag)

| Year | Size | Change | Source |
|------|------|--------|--------|
| Pre-2014 | ~12 oz | Original | [BLS BTN Feb 2023](https://www.bls.gov/opub/btn/volume-12/measuring-shrinkflation-and-its-impact-on-inflation.htm) (snack category) |
| ~2014-2016 | 11 oz → 10.5 oz → 9.75 oz | Stepped reductions | News investigations |
| ~2022 | 9.25 oz | Further reduction | News reports |

**Cumulative: −23% over ~10 years**

### 6.4 Peanut Butter (Skippy)

| Year | Size | Change | Source |
|------|------|--------|--------|
| Traditional | 18 oz | Standard jar | Consumer memory |
| ~2009 | 16.3 oz | −9.4% (deeper bottom indent, same jar height) | Multiple investigative reports |

### 6.5 Gatorade (Standard Bottle)

| Year | Size | Change | Source |
|------|------|--------|--------|
| Pre-2014 | 32 oz | Standard quart | Consumer/retail archives |
| ~2014 | 28 oz | −12.5% | Multiple news reports |

### 6.6 General Mills Cereal (Family Size)

| Year | Size | Price | Source |
|------|------|-------|--------|
| Pre-2021 | 19.3 oz | ~$2.99 | [Wikipedia: Shrinkflation](https://en.wikipedia.org/wiki/Shrinkflation) |
| 2021 | 18.1 oz | ~$2.99 (held) | [Wikipedia](https://en.wikipedia.org/wiki/Shrinkflation) |

---

## 7. Prediction Segment Plan

### 7.1 Concept

Show the historical RUPI trajectory for 1-2 products up to ~2015, then:
1. Fit a simple trend model on 2000-2015 data
2. Show the model's "prediction" for 2016-2025
3. Reveal actual 2016-2025 data
4. Show where the model was right and where reality diverged

### 7.2 Best Candidate: Eggs

**Why eggs:** Most dramatic trajectory with clear regime changes.

- **2000-2015 trend:** Volatile but upward. Linear trend from 1.0 to ~1.9, with spikes every 3-5 years
- **Simple model:** Linear regression on annual RUPI gives slope ≈ +0.06/year
- **Model prediction 2016-2025:** Steady climb from ~2.0 to ~2.5
- **Reality 2016-2021:** Dropped dramatically to 0.94 in 2020 (avian flu subsided, wages jumped)
- **Reality 2022-2025:** Exploded to 2.21 (avian flu returned, worse than ever)
- **Insight:** Linear models fail for supply-shock-driven commodities. The egg market is biological, not economic.

### 7.3 Alternative Candidate: Coffee

**Why coffee:** Long-term shrinkflation story + 2024-2025 price explosion.

- **2000-2017 trend:** Downward RUPI (from 1.0 to 0.85). Coffee was getting cheaper relative to wages.
- **Model prediction:** Continue declining to ~0.70 by 2025
- **Reality:** Surged to 1.125 by 2025 (global crop failures, climate change impact)
- **Insight:** Coffee's "cheap era" was subsidized by favorable growing conditions that are now ending

### 7.4 Implementation

For the race chart animation:
1. Run the chart normally from 2000 to 2015
2. Pause. Show fitted trend lines extending to 2025
3. "Here's what simple economics would predict..."
4. Resume the chart from 2016 to 2025 with actual data
5. Show divergence — eggs collapse then explode; coffee stays flat then surges
6. Caption: "Reality doesn't follow trendlines when biology and climate get involved"

---

## 8. Race Chart Technical Specifications

### 8.1 Data Model

For Remotion race chart component:

```typescript
interface RaceChartDataPoint {
  year: number;
  products: {
    id: string;
    name: string;
    rupiValue: number;
    isEstimated: boolean; // true for coffee 2008, 2009, 2019
  }[];
  wageAnomaly: boolean; // true for 2020
}
```

### 8.2 Visual Design Notes

- **Y-axis:** RUPI value (0.5 to 2.5 range to accommodate eggs)
- **Baseline:** Horizontal line at RUPI = 1.000 ("2000 affordability")
- **Color coding:**
  - 🟢 Below 1.0: "Getting cheaper relative to wages"
  - 🔴 Above 1.0: "Getting more expensive relative to wages"
- **Annotations:** 
  - 2009: "Häagen-Dazs shrinks 16→14 oz"
  - 2015: "First avian flu spike"
  - 2020: "⚠️ COVID wage anomaly"
  - 2022: "Inflation surge"
  - 2025: "Eggs 2.21× — Coffee crosses 1.0"

### 8.3 Products for Final Race Chart

**Primary 6 (all with BLS data):**
1. ☕ Coffee (per lb) — shrinkflation + recent price explosion
2. 🥚 Eggs (per dozen) — pure price inflation, dramatic leader
3. 🥔 Chips (per 16 oz) — quintessential shrinkflation story
4. 🥛 Milk (per gallon) — stable control product
5. 🥜 Peanut Butter (per lb) — stealth shrinkflation
6. 🍦 Ice Cream (per ½ gal) — Biden's favorite example

**Dropped from v1 recommendations:**
- Charmin/Bounty: No BLS average price series available at product level
- Gatorade: No BLS average price series for sports drinks
- General Mills Cereal: No BLS average price series for cereal (⚠️ could search further)
- Toblerone: UK-focused, dropped

### 8.4 Missing BLS Data — Search Summary

| Product | Series Tried | Result |
|---------|-------------|--------|
| Ice cream, prepackaged | APU0000SS2011, APU0000SS2012, APU0000SS2013, APU0000SS2001 | All "Series does not exist" |
| Ice cream, prepackaged | APU0000710212 | ✅ Works — per ½ gallon |
| Peanut butter, creamy | APU0000710211 | ✅ Works — per lb |
| Peanut butter | APU0000715111 | No data 2020+ |
| Cookies, chocolate chip | APU0000715211 | Has data but not relevant |

---

## 9. Data Quality Assessment (Updated)

| Product | BLS Series | Date Range | Gaps | Annual Avg Quality | RUPI Reliability |
|---------|-----------|------------|------|--------------------|------------------|
| Coffee | APU0000717311 | 2000-2025 | 2008 (full), 2009 (11 months), 2019 (9 months) | MEDIUM — 3 gaps | MEDIUM — gaps interpolated |
| Eggs | APU0000708111 | 2000-2025 | None | HIGH — complete | HIGH |
| Chips | APU0000718311 | 2000-2025 | None | HIGH — complete | HIGH |
| Milk | APU0000709112 | 2000-2025 | None | HIGH — complete | HIGH |
| Peanut Butter | APU0000710211 | 2000-2025 | 2018 Nov | HIGH — 1 month gap | HIGH |
| Ice Cream | APU0000710212 | 2000-2025 | None | HIGH — complete | HIGH |

**Overall data reliability: HIGH.** 5 of 6 products have complete or near-complete BLS data for the full 2000-2025 range. Coffee has 3 gap years but with reasonable interpolation. All data is from a single government statistical source (BLS Average Price program), ensuring methodological consistency.

---

## 10. Remaining Unverified Claims

| Claim | Status | Path to Resolution |
|-------|--------|--------------------|
| Doritos standard bag was 12 oz pre-2014 | ⚠️ UNVERIFIED | Need retail archive or news source with specific pre-2014 size |
| Folgers can shrink timeline (11.5 oz in 2003, 10.3 oz in 2011, 9.6 oz in 2022) | ⚠️ UNVERIFIED | Each step needs individual sourcing |
| Skippy additional shrink to 15 oz in ~2022 | ⚠️ UNVERIFIED | Need retail confirmation |
| Senator Casey's 2024 shrinkflation report details | ⚠️ UNVERIFIED | PDF not accessible during research |
| Coffee 2008 annual average ~$3.80 | ⚠️ ESTIMATED | BLS has no data for this series/year |
| Coffee 2009 annual average ~$3.67 | ⚠️ ESTIMATED | Only Dec data point available |
| Coffee 2019 annual average ~$4.14 | ⚠️ ESTIMATED | Only Oct-Dec data available |

**None of these unverified claims affect the race chart computations** — the RUPI is based entirely on verified BLS data (with coffee gap estimates clearly flagged). The unverified claims are narrative overlay about package sizes.

---

## 11. Sources

### Primary Data Sources

1. [BLS — Average Price Data (via API v2)](https://api.bls.gov/publicAPI/v2/timeseries/data/) — All 6 product price series, 2000-2025. Series: APU0000717311, APU0000708111, APU0000718311, APU0000709112, APU0000710211, APU0000710212.

2. [FRED — Median Usual Weekly Nominal Earnings (LES1252881500Q)](https://fred.stlouisfed.org/series/LES1252881500Q) — U.S. Bureau of Labor Statistics via Federal Reserve Bank of St. Louis. Quarterly, 2000-2025.

3. [BLS — "Getting less for the same price? Explore how the CPI measures 'shrinkflation' and its impact on inflation"](https://www.bls.gov/opub/btn/volume-12/measuring-shrinkflation-and-its-impact-on-inflation.htm) — *Beyond the Numbers*, Vol. 12 No. 2, February 2023, by Kari McNair.

### Narrative & Context Sources

4. [Wikipedia — Shrinkflation](https://en.wikipedia.org/wiki/Shrinkflation) — Sourced examples: Häagen-Dazs 16→14 oz (2009), General Mills cereal 19.3→18.1 oz (2021), P&G paper products, Toblerone.

5. [NYT — "Shrinkflation 101"](https://www.nytimes.com/2024/03/01/business/economy/shrinkflation-groceries.html) — Jeanna Smialek, March 2024. Historical coffee can shrinkage, skimpflation definition.

6. [HBS Alumni — Coffee shrinkflation history](https://www.alumni.hbs.edu/stories/Pages/story-bulletin.aspx?num=8743) — 1988 Chock Full o'Nuts precedent.

7. [St. Louis Fed — "Beyond Inflation Numbers"](https://www.stlouisfed.org/publications/page-one-economics/2022/12/01/beyond-inflation-numbers-shrinkflation-and-skimpflation) — Jeannette Bennett, December 2022.

8. [ProMarket — "Do Antitrust Enforcers Know They Induce Shrinkflation?"](https://www.promarket.org/2023/08/18/do-antitrust-enforcers-know-they-induce-shrinkflation/) — Barak Orbach, August 2023.

9. [BBC News — Toblerone 2016 size change](https://www.bbc.com/news/uk-37904703) — November 2016.

10. [UK ONS — Shrinkflation Study 2019](https://www.ons.gov.uk/economy/inflationandpriceindices/articles/theshrinkingcontentsofgroceryproductsisthisshrinkflation/2019-01-21) — Referenced for UK context.

---

## 12. Summary for Approval

### What this research delivers:

1. **Complete RUPI data for 6 products, 2000-2025** — sufficient to build the race chart immediately
2. **All data from a single government source (BLS)** — methodologically consistent, defensible
3. **Three-act narrative structure** with identified surprise finding (most items cheaper relative to wages)
4. **Prediction segment plan** using eggs or coffee as candidates
5. **2020 wage anomaly resolved** — use raw data with visual annotation
6. **Shrinkflation overlay** documented separately from price data (narrative enrichment, not computation)

### Race chart ready to build?

**YES** — for the 6 BLS-sourced products. Data gaps in coffee (2008, 2009, 2019) are interpolated and flagged. All other products have complete 26-year coverage.

### Key editorial decision needed:

The data shows most products are cheaper relative to wages. The video's thesis ("shrinkflation hurts consumers") needs to be reframed. Suggested angle:

> "The real cost per ounce hasn't outpaced your wage for most items. But the PACKAGE keeps shrinking — so you're buying the same number of trips to the store, paying the same at checkout, and getting less in your bag. The economics say you're fine. Your fridge disagrees."
