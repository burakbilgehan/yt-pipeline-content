# Research: Shrinkflation Decoded — Cross-Validation with Alternative Deflators (Corrected)

> version: 4
> based_on: research-v3
> changes_from_prev: Fixed systematic RUPI computation errors in CPI/Gold/MinWage columns for all time series tables. Added full time series for milk, peanut butter, and ice cream. Neutralized editorial language in Section 4.4. Corrected coffee "~13 years" claim to "since ~2014" (inherited from v2 Section 4.3).
> date: 2026-03-26

---

## 1. Deflator Data — Annual Values (2000–2025)

### 1.1 CPI-U (All Items, U.S. City Average)

**Source:** BLS CPI-U series CUUR0000SA0, retrieved via BLS Public Data API v2. Annual averages computed from monthly data. [BLS CPI Data](https://www.bls.gov/cpi/)

| Year | CPI-U | CPI Index (2000 = 1.000) |
|------|-------|--------------------------|
| 2000 | 172.200 | 1.000 |
| 2001 | 177.067 | 1.028 |
| 2002 | 179.875 | 1.045 |
| 2003 | 183.958 | 1.068 |
| 2004 | 188.883 | 1.097 |
| 2005 | 195.292 | 1.134 |
| 2006 | 201.592 | 1.171 |
| 2007 | 207.342 | 1.204 |
| 2008 | 215.303 | 1.250 |
| 2009 | 214.537 | 1.246 |
| 2010 | 218.056 | 1.266 |
| 2011 | 224.939 | 1.306 |
| 2012 | 229.594 | 1.334 |
| 2013 | 232.957 | 1.353 |
| 2014 | 236.736 | 1.375 |
| 2015 | 237.017 | 1.376 |
| 2016 | 240.007 | 1.394 |
| 2017 | 245.120 | 1.423 |
| 2018 | 251.107 | 1.458 |
| 2019 | 255.657 | 1.485 |
| 2020 | 258.811 | 1.503 |
| 2021 | 270.970 | 1.574 |
| 2022 | 292.655 | 1.700 |
| 2023 | 304.702 | 1.770 |
| 2024 | 313.689 | 1.822 |
| 2025 | 321.943 | 1.870 |

**Note:** 2025 is the average of 11 months (Jan–Nov data available).

### 1.2 Gold Price (Annual Average, London PM Fix)

**Source:** LBMA London PM Fix annual averages, as published by Kitco/MeasuringWorth. Wikipedia "Gold as an investment" table confirms 5-year anchor points (2000: $273, 2005: $513, 2010: $1,410). ⚠️ 2025 is estimated based on published reporting: gold crossed $4,000 in Oct 2025 per WSJ; Q1-Q3 average lower. [Wikipedia Gold as an Investment](https://en.wikipedia.org/wiki/Gold_as_an_investment) [Kitco Historical Gold](https://www.kitco.com) [MeasuringWorth Gold](https://www.measuringworth.com/gold/)

| Year | Gold $/ozt | Gold Index (2000 = 1.000) |
|------|-----------|--------------------------|
| 2000 | 279 | 1.000 |
| 2001 | 271 | 0.971 |
| 2002 | 310 | 1.111 |
| 2003 | 363 | 1.301 |
| 2004 | 410 | 1.470 |
| 2005 | 445 | 1.595 |
| 2006 | 604 | 2.165 |
| 2007 | 695 | 2.491 |
| 2008 | 872 | 3.125 |
| 2009 | 972 | 3.484 |
| 2010 | 1,225 | 4.391 |
| 2011 | 1,572 | 5.634 |
| 2012 | 1,669 | 5.982 |
| 2013 | 1,411 | 5.057 |
| 2014 | 1,266 | 4.538 |
| 2015 | 1,160 | 4.158 |
| 2016 | 1,251 | 4.484 |
| 2017 | 1,258 | 4.509 |
| 2018 | 1,269 | 4.548 |
| 2019 | 1,393 | 4.993 |
| 2020 | 1,770 | 6.344 |
| 2021 | 1,799 | 6.448 |
| 2022 | 1,800 | 6.452 |
| 2023 | 1,940 | 6.953 |
| 2024 | 2,386 | 8.552 |
| 2025 | ⚠️ ~3,500 | ⚠️ ~12.545 |

**⚠️ NOTES on gold data quality:**
- 2000–2024 values are LBMA London PM Fix annual averages, widely published by Kitco, USGS, and MeasuringWorth. These are standard reference values used in financial analysis.
- Wikipedia confirms anchor points: 2000: $273 (close to $279 avg), 2005: $513 (close to $445 avg — note: Wikipedia uses year-end close, we use annual average), 2010: $1,410 (close to $1,225 avg).
- **2025 estimate:** Gold crossed $4,000/ozt in Oct 2025 (WSJ). Using a weighted estimate for full-year average with H1 ~$2,800-3,200 and H2 spike, we estimate ~$3,500 annual average. This is flagged as approximate.
- The Wikipedia table uses LBMA year-end close values, which differ from annual averages. Our data uses Kitco-sourced annual averages, which is the standard methodology.

### 1.3 Federal Minimum Wage

**Source:** U.S. Department of Labor, Wage and Hour Division. [DOL Minimum Wage History](https://www.dol.gov/agencies/whd/minimum-wage/history)

| Period | Fed Min Wage ($/hr) |
|--------|-------------------|
| Sep 1997 – Jul 2007 | $5.15 |
| Jul 2007 – Jul 2008 | $5.85 |
| Jul 2008 – Jul 2009 | $6.55 |
| Jul 2009 – present (2025) | $7.25 |

For annual index computation, we use the wage rate in effect for the majority of the year:

| Year | Min Wage $/hr | Min Wage Index (2000 = 1.000) |
|------|-------------|------------------------------|
| 2000 | 5.15 | 1.000 |
| 2001 | 5.15 | 1.000 |
| 2002 | 5.15 | 1.000 |
| 2003 | 5.15 | 1.000 |
| 2004 | 5.15 | 1.000 |
| 2005 | 5.15 | 1.000 |
| 2006 | 5.15 | 1.000 |
| 2007 | 5.15 | 1.000 |
| 2008 | 5.85 | 1.136 |
| 2009 | 6.55 | 1.272 |
| 2010 | 7.25 | 1.408 |
| 2011 | 7.25 | 1.408 |
| 2012 | 7.25 | 1.408 |
| 2013 | 7.25 | 1.408 |
| 2014 | 7.25 | 1.408 |
| 2015 | 7.25 | 1.408 |
| 2016 | 7.25 | 1.408 |
| 2017 | 7.25 | 1.408 |
| 2018 | 7.25 | 1.408 |
| 2019 | 7.25 | 1.408 |
| 2020 | 7.25 | 1.408 |
| 2021 | 7.25 | 1.408 |
| 2022 | 7.25 | 1.408 |
| 2023 | 7.25 | 1.408 |
| 2024 | 7.25 | 1.408 |
| 2025 | 7.25 | 1.408 |

**Key observation:** The federal minimum wage has been frozen at $7.25/hr since July 2009 — **16 consecutive years** with no increase. The minimum wage index is flat at 1.408 from 2010 onward, while all other deflators continue rising. This means minimum wage RUPI will show every price increase amplified after 2009.

**Note on 2007–2009:** The three-step increase ($5.15→$5.85→$6.55→$7.25) happened in July of each year. We use the rate in effect for the majority of the calendar year. For 2007 (increase in Jul), most of the year was $5.15, so we use $5.15. For 2008, the increase from $5.85 to $6.55 happened in Jul, so we use $5.85 (majority). For 2009, the increase from $6.55 to $7.25 happened in Jul, so we use $6.55.

### 1.4 Big Mac Price (USA)

**⚠️ DATA GAP — SKIPPED**

The Big Mac Index, published by The Economist since 1986, tracks Big Mac prices across countries for PPP comparison. However:
- The index is designed for **cross-country** comparison, not longitudinal US price tracking
- No publicly accessible time series of annual US Big Mac prices 2000–2025 was found
- The Economist's interactive tool provides current and recent data, but not a full 25-year history in downloadable form
- Wikipedia's Big Mac Index article confirms current prices (~$5.58 in Jul 2023) but lacks a US price history table
- Statista has Big Mac Index data but behind a paywall

**Recommendation:** Exclude Big Mac as a deflator. The three remaining deflators (CPI, gold, minimum wage) already provide dramatically different perspectives. Adding a fourth with incomplete data would weaken the analysis.

### 1.5 Deflator Summary — 2025 Index Values (2000 = 1.000)

| Deflator | 2025 Index | Growth Since 2000 | Interpretation |
|----------|-----------|-------------------|----------------|
| Median Wage | 2.107 | +111% | Median worker earns 2.1× more nominally |
| CPI-U | 1.870 | +87% | General prices up 87% |
| Gold | ⚠️ ~12.545 | +1,155% | Gold up ~12.5× in 25 years |
| Federal Min Wage | 1.408 | +41% | Min wage barely moved |

**Key insight:** These deflators tell RADICALLY different stories:
- **Median wage > CPI:** Real wages have grown — the median worker has more purchasing power in 2025 than 2000
- **Min wage << CPI:** Minimum wage workers have LOST purchasing power — prices up 87% but their wage only up 41%
- **Gold >> everything:** Gold has massively outperformed, making everything look cheap in gold terms

---

## 2. RUPI Cross-Validation — 2025 Snapshot

### 2.1 Formula Reminder

```
RUPI_t = (nominal_unit_price_t / nominal_unit_price_2000) ÷ deflator_index_t
```

Where `deflator_index_t` is one of: median wage index, CPI index, gold index, or min wage index.

### 2.2 Cross-Validation Table (All Products, 2025)

| Product | Nominal Ratio (2025/2000) | RUPI: Wage | RUPI: CPI | RUPI: Gold | RUPI: Min Wage |
|---------|--------------------------|-----------|-----------|------------|---------------|
| Coffee ($/lb) | 2.371 | **1.125** | **1.268** | ⚠️ **0.189** | **1.684** |
| Eggs ($/doz) | 4.657 | **2.210** | **2.490** | ⚠️ **0.371** | **3.308** |
| Chips ($/16oz) | 1.996 | **0.947** | **1.067** | ⚠️ **0.159** | **1.418** |
| Milk ($/gal) | 1.462 | **0.694** | **0.782** | ⚠️ **0.117** | **1.039** |
| Peanut Butter ($/lb) | 1.338 | **0.635** | **0.715** | ⚠️ **0.107** | **0.950** |
| Ice Cream ($/½gal) | 1.525 | **0.724** | **0.816** | ⚠️ **0.122** | **1.083** |

### 2.3 Sample Calculations (Shown Math)

**Eggs, 2025, CPI-deflated:**
```
Price_2025 = $4.252/doz, Price_2000 = $0.913/doz
Nominal ratio = 4.252 / 0.913 = 4.657
CPI index_2025 = 321.943 / 172.200 = 1.870
RUPI_CPI = 4.657 / 1.870 = 2.490
→ Eggs cost 2.49× their real 2000 price (CPI-adjusted)
```

**Chips, 2025, Min-Wage-deflated:**
```
Price_2025 = $6.705/16oz, Price_2000 = $3.360/16oz
Nominal ratio = 6.705 / 3.360 = 1.996
Min wage index_2025 = 7.25 / 5.15 = 1.408
RUPI_MinWage = 1.996 / 1.408 = 1.418
→ Chips cost 42% MORE of a minimum-wage hour than in 2000
```

**Coffee, 2025, Gold-deflated:**
```
Price_2025 = $8.180/lb, Price_2000 = $3.450/lb
Nominal ratio = 8.180 / 3.450 = 2.371
Gold index_2025 = ~3500 / 279 = ~12.545
RUPI_Gold = 2.371 / 12.545 = 0.189
→ Coffee costs only 19% of its 2000 gold-equivalent price
```

**Milk, 2025, CPI-deflated:**
```
Price_2025 = $4.067/gal, Price_2000 = $2.781/gal
Nominal ratio = 4.067 / 2.781 = 1.462
CPI index_2025 = 1.870
RUPI_CPI = 1.462 / 1.870 = 0.782
→ Milk is 22% cheaper in CPI-real terms than in 2000
```

### 2.4 Key Finding: Do Deflators Agree?

**YES on direction, NO on magnitude.** The deflators form a clear spectrum:

**1. Gold deflator (most optimistic):** Everything is dirt cheap. Gold rose ~12.5× while food prices rose 1.3–4.7×. Every single product has RUPI well below 1.0. If you'd stored wealth in gold, groceries are a bargain. But this is irrelevant for most people.

**2. Median wage deflator (v2 baseline, moderately optimistic):** 4 of 6 products below 1.0. Only eggs (2.21) and coffee (1.13) are more expensive. Wages outpaced most food prices.

**3. CPI deflator (neutral benchmark):** Shifts everything UP. Now only 3 products below 1.0 (milk 0.78, PB 0.72, ice cream 0.82). Chips cross to 1.07 — no longer "cheaper." Coffee jumps to 1.27. Eggs hit 2.49.

**4. Minimum wage deflator (most pessimistic):** Nearly everything above 1.0! Only peanut butter (0.95) stays below. Chips (1.42), milk (1.04), ice cream (1.08) — all MORE expensive. Coffee (1.68) and eggs (3.31) are dramatically worse. This is the world of a minimum-wage worker.

**The verdict: The v2 finding ("most things got cheaper") depends heavily on WHO you ask.** For the median worker, yes. For someone on minimum wage, almost everything got more expensive. The gold perspective is an outlier (irrelevant to grocery shoppers).

---

## 3. Full RUPI Time Series — All 6 Products Under All 4 Deflators

### v4 Computation Note

All RUPI values in this section were recomputed from scratch using the formula:

```
RUPI_t = (price_t / price_2000) ÷ deflator_index_t
```

Inputs: nominal prices from research-v2 Section 2.3, deflator indices from Section 1 / Appendix of this document. All values rounded to 3 decimal places. The Wage RUPI column was verified unchanged from v2/v3 (confirmed correct). The CPI, Gold, and Min Wage columns replace the v3 values, which contained systematic computation errors that grew with distance from the base year.

### 3.1 Eggs ($/dozen) — The Runaway Leader

| Year | Nominal $ | RUPI: Wage | RUPI: CPI | RUPI: Gold | RUPI: Min Wage |
|------|----------|-----------|-----------|------------|---------------|
| 2000 | 0.913 | 1.000 | 1.000 | 1.000 | 1.000 |
| 2001 | 0.929 | 0.980 | 0.990 | 1.048 | 1.018 |
| 2002 | 1.032 | 1.063 | 1.082 | 1.017 | 1.130 |
| 2003 | 1.244 | 1.259 | 1.276 | 1.047 | 1.363 |
| 2004 | 1.340 | 1.308 | 1.338 | 0.998 | 1.468 |
| 2005 | 1.218 | 1.180 | 1.176 | 0.836 | 1.334 |
| 2006 | 1.306 | 1.234 | 1.222 | 0.661 | 1.430 |
| 2007 | 1.676 | 1.515 | 1.525 | 0.737 | 1.836 |
| 2008 | 1.987 | 1.725 | 1.741 | 0.696 | 1.916 |
| 2009 | 1.664 | 1.415 | 1.463 | 0.523 | 1.433 |
| 2010 | 1.660 | 1.402 | 1.436 | 0.414 | 1.291 |
| 2011 | 1.769 | 1.470 | 1.484 | 0.344 | 1.376 |
| 2012 | 1.838 | 1.491 | 1.509 | 0.337 | 1.430 |
| 2013 | 1.910 | 1.541 | 1.546 | 0.414 | 1.486 |
| 2014 | 2.018 | 1.619 | 1.607 | 0.487 | 1.570 |
| 2015 | 2.469 | 1.926 | 1.965 | 0.650 | 1.921 |
| 2016 | 1.684 | 1.274 | 1.323 | 0.411 | 1.310 |
| 2017 | 1.467 | 1.065 | 1.129 | 0.356 | 1.141 |
| 2018 | 1.742 | 1.239 | 1.309 | 0.420 | 1.355 |
| 2019 | 1.396 | 0.957 | 1.030 | 0.306 | 1.086 |
| 2020 | 1.506 | 0.936 | 1.097 | 0.260 | 1.172 |
| 2021 | 1.674 | 1.053 | 1.165 | 0.284 | 1.302 |
| 2022 | 2.857 | 1.708 | 1.841 | 0.485 | 2.222 |
| 2023 | 2.796 | 1.581 | 1.730 | 0.440 | 2.175 |
| 2024 | 3.171 | 1.726 | 1.906 | 0.406 | 2.467 |
| 2025 | 4.252 | 2.210 | 2.490 | ⚠️ 0.371 | 3.308 |

### 3.2 Coffee ($/lb) — The Slow Boil

| Year | Nominal $ | RUPI: Wage | RUPI: CPI | RUPI: Gold | RUPI: Min Wage |
|------|----------|-----------|-----------|------------|---------------|
| 2000 | 3.450 | 1.000 | 1.000 | 1.000 | 1.000 |
| 2001 | 3.093 | 0.864 | 0.872 | 0.923 | 0.897 |
| 2002 | 2.924 | 0.797 | 0.811 | 0.763 | 0.848 |
| 2003 | 2.916 | 0.781 | 0.791 | 0.650 | 0.845 |
| 2004 | 2.849 | 0.736 | 0.753 | 0.562 | 0.826 |
| 2005 | 3.262 | 0.836 | 0.834 | 0.593 | 0.946 |
| 2006 | 3.203 | 0.801 | 0.793 | 0.429 | 0.928 |
| 2007 | 3.469 | 0.830 | 0.835 | 0.404 | 1.006 |
| 2008 | ⚠️ ~3.80 | ⚠️ 0.873 | ⚠️ 0.881 | ⚠️ 0.352 | ⚠️ 0.970 |
| 2009 | ⚠️ ~3.67 | ⚠️ 0.826 | ⚠️ 0.854 | ⚠️ 0.305 | ⚠️ 0.836 |
| 2010 | 3.906 | 0.873 | 0.894 | 0.258 | 0.804 |
| 2011 | 5.191 | 1.142 | 1.152 | 0.267 | 1.069 |
| 2012 | 5.676 | 1.219 | 1.233 | 0.275 | 1.168 |
| 2013 | 5.453 | 1.164 | 1.168 | 0.313 | 1.123 |
| 2014 | 4.990 | 1.060 | 1.052 | 0.319 | 1.027 |
| 2015 | 4.720 | 0.974 | 0.994 | 0.329 | 0.972 |
| 2016 | 4.393 | 0.879 | 0.913 | 0.284 | 0.904 |
| 2017 | 4.453 | 0.855 | 0.907 | 0.286 | 0.917 |
| 2018 | 4.302 | 0.810 | 0.855 | 0.274 | 0.886 |
| 2019 | ⚠️ ~4.14 | ⚠️ 0.751 | ⚠️ 0.808 | ⚠️ 0.240 | ⚠️ 0.852 |
| 2020 | 4.433 | 0.729 | 0.855 | 0.203 | 0.913 |
| 2021 | 4.705 | 0.783 | 0.866 | 0.212 | 0.969 |
| 2022 | 5.891 | 0.932 | 1.004 | 0.265 | 1.213 |
| 2023 | 6.156 | 0.921 | 1.008 | 0.257 | 1.267 |
| 2024 | 6.322 | 0.911 | 1.006 | 0.214 | 1.301 |
| 2025 | 8.180 | 1.125 | 1.268 | ⚠️ 0.189 | 1.684 |

### 3.3 Chips ($/16oz) — The Stealth Fighter

| Year | Nominal $ | RUPI: Wage | RUPI: CPI | RUPI: Gold | RUPI: Min Wage |
|------|----------|-----------|-----------|------------|---------------|
| 2000 | 3.360 | 1.000 | 1.000 | 1.000 | 1.000 |
| 2001 | 3.426 | 0.982 | 0.992 | 1.050 | 1.020 |
| 2002 | 3.356 | 0.940 | 0.956 | 0.899 | 0.999 |
| 2003 | 3.499 | 0.962 | 0.975 | 0.800 | 1.041 |
| 2004 | 3.403 | 0.903 | 0.923 | 0.689 | 1.013 |
| 2005 | 3.368 | 0.886 | 0.884 | 0.628 | 1.002 |
| 2006 | 3.466 | 0.890 | 0.881 | 0.476 | 1.032 |
| 2007 | 3.530 | 0.867 | 0.873 | 0.422 | 1.051 |
| 2008 | 4.021 | 0.948 | 0.957 | 0.383 | 1.053 |
| 2009 | 4.569 | 1.056 | 1.091 | 0.390 | 1.069 |
| 2010 | 4.642 | 1.065 | 1.091 | 0.315 | 0.981 |
| 2011 | 4.968 | 1.122 | 1.132 | 0.262 | 1.050 |
| 2012 | 4.986 | 1.099 | 1.112 | 0.248 | 1.054 |
| 2013 | 4.665 | 1.022 | 1.026 | 0.275 | 0.986 |
| 2014 | 4.371 | 0.953 | 0.946 | 0.287 | 0.924 |
| 2015 | 4.408 | 0.934 | 0.953 | 0.316 | 0.932 |
| 2016 | 4.461 | 0.917 | 0.952 | 0.296 | 0.943 |
| 2017 | 4.409 | 0.870 | 0.922 | 0.291 | 0.932 |
| 2018 | 4.446 | 0.859 | 0.908 | 0.291 | 0.940 |
| 2019 | 4.485 | 0.835 | 0.899 | 0.267 | 0.948 |
| 2020 | 4.922 | 0.831 | 0.975 | 0.231 | 1.040 |
| 2021 | 5.076 | 0.868 | 0.960 | 0.234 | 1.073 |
| 2022 | 5.827 | 0.947 | 1.020 | 0.269 | 1.232 |
| 2023 | 6.445 | 0.990 | 1.084 | 0.276 | 1.362 |
| 2024 | 6.455 | 0.955 | 1.054 | 0.225 | 1.364 |
| 2025 | 6.705 | 0.947 | 1.067 | ⚠️ 0.159 | 1.418 |

### 3.4 Milk ($/gal) — Wages Won

| Year | Nominal $ | RUPI: Wage | RUPI: CPI | RUPI: Gold | RUPI: Min Wage |
|------|----------|-----------|-----------|------------|---------------|
| 2000 | 2.781 | 1.000 | 1.000 | 1.000 | 1.000 |
| 2001 | 2.884 | 0.999 | 1.009 | 1.068 | 1.037 |
| 2002 | 2.757 | 0.933 | 0.949 | 0.892 | 0.991 |
| 2003 | 2.761 | 0.918 | 0.930 | 0.763 | 0.993 |
| 2004 | 3.156 | 1.011 | 1.034 | 0.772 | 1.135 |
| 2005 | 3.187 | 1.013 | 1.011 | 0.718 | 1.146 |
| 2006 | 3.081 | 0.956 | 0.946 | 0.512 | 1.108 |
| 2007 | 3.503 | 1.039 | 1.046 | 0.506 | 1.260 |
| 2008 | 3.795 | 1.081 | 1.092 | 0.437 | 1.201 |
| 2009 | 3.109 | 0.868 | 0.897 | 0.321 | 0.879 |
| 2010 | 3.258 | 0.903 | 0.925 | 0.267 | 0.832 |
| 2011 | 3.572 | 0.975 | 0.983 | 0.228 | 0.912 |
| 2012 | 3.493 | 0.930 | 0.942 | 0.210 | 0.892 |
| 2013 | 3.462 | 0.917 | 0.920 | 0.246 | 0.884 |
| 2014 | 3.694 | 0.973 | 0.966 | 0.293 | 0.943 |
| 2015 | 3.419 | 0.876 | 0.893 | 0.296 | 0.873 |
| 2016 | 3.204 | 0.796 | 0.826 | 0.257 | 0.818 |
| 2017 | 3.226 | 0.769 | 0.815 | 0.257 | 0.824 |
| 2018 | 2.896 | 0.676 | 0.714 | 0.229 | 0.740 |
| 2019 | 3.036 | 0.683 | 0.735 | 0.219 | 0.775 |
| 2020 | 3.318 | 0.677 | 0.794 | 0.188 | 0.847 |
| 2021 | 3.544 | 0.732 | 0.810 | 0.198 | 0.905 |
| 2022 | 4.091 | 0.803 | 0.865 | 0.228 | 1.045 |
| 2023 | 4.027 | 0.748 | 0.818 | 0.208 | 1.028 |
| 2024 | 3.984 | 0.712 | 0.786 | 0.168 | 1.017 |
| 2025 | 4.067 | 0.694 | 0.782 | ⚠️ 0.117 | 1.039 |

### 3.5 Peanut Butter ($/lb) — The Steepest Decline

| Year | Nominal $ | RUPI: Wage | RUPI: CPI | RUPI: Gold | RUPI: Min Wage |
|------|----------|-----------|-----------|------------|---------------|
| 2000 | 3.698 | 1.000 | 1.000 | 1.000 | 1.000 |
| 2001 | 3.871 | 1.008 | 1.018 | 1.078 | 1.047 |
| 2002 | 3.881 | 0.987 | 1.004 | 0.945 | 1.049 |
| 2003 | 3.771 | 0.942 | 0.955 | 0.784 | 1.020 |
| 2004 | 3.984 | 0.960 | 0.982 | 0.733 | 1.077 |
| 2005 | 3.881 | 0.928 | 0.925 | 0.658 | 1.049 |
| 2006 | 3.720 | 0.868 | 0.859 | 0.465 | 1.006 |
| 2007 | 3.839 | 0.857 | 0.862 | 0.417 | 1.038 |
| 2008 | 4.042 | 0.866 | 0.874 | 0.350 | 0.962 |
| 2009 | 3.903 | 0.819 | 0.847 | 0.303 | 0.830 |
| 2010 | 3.910 | 0.815 | 0.835 | 0.241 | 0.751 |
| 2011 | 4.066 | 0.834 | 0.842 | 0.195 | 0.781 |
| 2012 | 4.188 | 0.839 | 0.849 | 0.189 | 0.804 |
| 2013 | 4.175 | 0.831 | 0.834 | 0.223 | 0.802 |
| 2014 | 4.494 | 0.890 | 0.884 | 0.268 | 0.863 |
| 2015 | 4.456 | 0.858 | 0.876 | 0.290 | 0.856 |
| 2016 | 4.367 | 0.816 | 0.847 | 0.263 | 0.839 |
| 2017 | 4.248 | 0.761 | 0.807 | 0.255 | 0.816 |
| 2018 | 4.007 | 0.704 | 0.743 | 0.238 | 0.770 |
| 2019 | 3.876 | 0.656 | 0.706 | 0.210 | 0.744 |
| 2020 | 4.104 | 0.630 | 0.738 | 0.175 | 0.788 |
| 2021 | 4.036 | 0.627 | 0.693 | 0.169 | 0.775 |
| 2022 | 4.401 | 0.650 | 0.700 | 0.184 | 0.845 |
| 2023 | 4.756 | 0.664 | 0.727 | 0.185 | 0.913 |
| 2024 | 4.893 | 0.658 | 0.726 | 0.155 | 0.940 |
| 2025 | 4.947 | 0.635 | 0.715 | ⚠️ 0.107 | 0.950 |

### 3.6 Ice Cream ($/½gal) — Size Change Absorbed

| Year | Nominal $ | RUPI: Wage | RUPI: CPI | RUPI: Gold | RUPI: Min Wage |
|------|----------|-----------|-----------|------------|---------------|
| 2000 | 3.830 | 1.000 | 1.000 | 1.000 | 1.000 |
| 2001 | 4.027 | 1.013 | 1.023 | 1.083 | 1.051 |
| 2002 | 4.218 | 1.036 | 1.054 | 0.991 | 1.101 |
| 2003 | 3.948 | 0.953 | 0.965 | 0.792 | 1.031 |
| 2004 | 4.273 | 0.994 | 1.017 | 0.759 | 1.116 |
| 2005 | 4.381 | 1.011 | 1.009 | 0.717 | 1.144 |
| 2006 | 4.255 | 0.959 | 0.949 | 0.513 | 1.111 |
| 2007 | 4.230 | 0.911 | 0.917 | 0.443 | 1.104 |
| 2008 | 4.725 | 0.978 | 0.987 | 0.395 | 1.086 |
| 2009 | 4.669 | 0.946 | 0.978 | 0.350 | 0.958 |
| 2010 | 4.710 | 0.948 | 0.971 | 0.280 | 0.873 |
| 2011 | 5.419 | 1.074 | 1.083 | 0.251 | 1.005 |
| 2012 | 5.625 | 1.088 | 1.101 | 0.246 | 1.043 |
| 2013 | 5.558 | 1.069 | 1.073 | 0.287 | 1.031 |
| 2014 | 5.543 | 1.060 | 1.053 | 0.319 | 1.028 |
| 2015 | 5.379 | 1.000 | 1.021 | 0.338 | 0.997 |
| 2016 | 5.235 | 0.944 | 0.981 | 0.305 | 0.971 |
| 2017 | 4.895 | 0.847 | 0.898 | 0.283 | 0.908 |
| 2018 | 5.135 | 0.871 | 0.920 | 0.295 | 0.952 |
| 2019 | 5.308 | 0.867 | 0.933 | 0.278 | 0.984 |
| 2020 | 5.496 | 0.814 | 0.955 | 0.226 | 1.019 |
| 2021 | 5.440 | 0.816 | 0.902 | 0.220 | 1.009 |
| 2022 | 5.762 | 0.821 | 0.885 | 0.233 | 1.068 |
| 2023 | 5.823 | 0.785 | 0.859 | 0.219 | 1.080 |
| 2024 | 5.664 | 0.735 | 0.812 | 0.173 | 1.050 |
| 2025 | 5.842 | 0.724 | 0.816 | ⚠️ 0.122 | 1.083 |

### 3.7 Spot-Check Calculations — Verifying v3 Error Corrections

The following spot checks demonstrate the computation errors in v3 and confirm the v4 corrected values.

**Spot Check 1: Eggs, 2010 — CPI deflator**
```
v3 value: 1.197 (WRONG)
v4 computation:
  Nominal ratio = 1.660 / 0.913 = 1.818
  CPI index_2010 = 1.266
  RUPI = 1.818 / 1.266 = 1.436 ✅
  Error in v3: -0.239 (v3 was 17% too low)
```

**Spot Check 2: Coffee, 2015 — Min Wage deflator**
```
v3 value: 0.817 (WRONG)
v4 computation:
  Nominal ratio = 4.720 / 3.450 = 1.368
  Min Wage index_2015 = 1.408
  RUPI = 1.368 / 1.408 = 0.972 ✅
  Error in v3: -0.155 (v3 was 16% too low)
```

**Spot Check 3: Chips, 2020 — Gold deflator**
```
v3 value: 0.150 (WRONG)
v4 computation:
  Nominal ratio = 4.922 / 3.360 = 1.465
  Gold index_2020 = 6.344
  RUPI = 1.465 / 6.344 = 0.231 ✅
  Error in v3: -0.081 (v3 was 35% too low)
```

**Spot Check 4: Eggs, 2020 — Min Wage deflator**
```
v3 value: 0.965 (WRONG)
v4 computation:
  Nominal ratio = 1.506 / 0.913 = 1.650
  Min Wage index_2020 = 1.408
  RUPI = 1.650 / 1.408 = 1.172 ✅
  Error in v3: -0.207 (v3 was 18% too low — eggs WERE above 1.0 for min wage workers even in 2020)
```

**Pattern of v3 errors:** The errors are systematically negative (v3 underestimated all non-wage RUPIs) and grew in magnitude over time. The 2000-2004 values were approximately correct; errors became visible ~2005 and significant by 2010+. This is consistent with an accumulation error or incorrect deflator indexing during computation.

### 3.8 Key Change from v3: Min Wage Eggs Were NEVER Below 1.0

A significant finding from the v4 recomputation: under the minimum wage deflator, eggs have been above 1.0 for almost every year since 2001. The v3 data incorrectly showed eggs dipping below 1.0 in 2016-2021 (min wage RUPI range of 0.917-1.085 in v3). The correct values show eggs staying at 1.086-1.310 throughout that period — a minimum-wage worker has NEVER had eggs return to 2000 affordability since 2001.

---

## 4. Analysis — Do the Deflators Agree or Disagree?

### 4.1 The Agreement

All four deflators agree on the **relative ordering** of products:

```
Eggs >> Coffee >> Chips ≈ Ice Cream ≈ Milk > Peanut Butter
(most expensive)                              (least expensive)
```

Eggs are the biggest real-price gainer and peanut butter is the biggest loser under EVERY deflator. This structural story is robust.

### 4.2 The Disagreement — Threshold Effects

The deflators disagree on which products cross the critical RUPI = 1.0 threshold:

| Deflator | Products ABOVE 1.0 (more expensive) | Products BELOW 1.0 (cheaper) |
|----------|-------------------------------------|------------------------------|
| Gold | **0 of 6** | All 6 |
| Median Wage | **2 of 6** (eggs, coffee) | 4 (chips, milk, PB, ice cream) |
| CPI | **3 of 6** (eggs, coffee, chips) | 3 (milk, PB, ice cream) |
| Min Wage | **5 of 6** (eggs, coffee, chips, milk, ice cream) | 1 (peanut butter, barely) |

**This is the video's punchline.** The same data, same products, same years — but the conclusion flips from "most things got cheaper" to "nearly everything got more expensive" depending on whose income you use as the measuring stick.

### 4.3 Why CPI Shows Higher RUPI Than Wages

CPI index (1.870) is LOWER than wage index (2.107). This means:
```
RUPI_CPI = nominal_ratio / 1.870  >  nominal_ratio / 2.107 = RUPI_Wage
```

Because you're dividing by a smaller number, CPI-deflated RUPI is always higher. Economically: **wages grew faster than general inflation** (real wages increased ~12-13% over 25 years for the median worker). This is why the wage-deflated view is more optimistic.

### 4.4 The Minimum Wage Stagnation

The minimum wage deflator tells the most dramatic story:

**2000–2007:** Minimum wage was frozen at $5.15, so min-wage RUPI equals nominal ratio. Products that got more expensive in nominal terms immediately show RUPI > 1.0.

**2007–2009:** Three-step increase to $7.25. Temporary relief — all RUPIs drop as the denominator jumps.

**2009–2025:** 16 years frozen. Every nominal price increase hits unabated. By 2025:
- Eggs: 3.31 (a minimum-wage worker needs 3.3× more work hours to buy eggs than in 2000)
- Coffee: 1.68
- Chips: 1.42
- Even milk (1.04) — previously the "success story" — crosses above 1.0

The 16-year freeze in the federal minimum wage means that every nominal food price increase since 2009 translates directly into reduced purchasing power for workers earning at or near that floor.

### 4.5 Gold: A Different Universe

Gold's 12.5× appreciation dwarfs all food price increases. Even eggs (4.66× nominal) look cheap against gold. This deflator is intellectually interesting but practically irrelevant for the average viewer's experience. However, it makes a powerful philosophical point:

> "If you measured your groceries in gold instead of dollars, everything is on sale. The question is: who measures their life in gold?"

---

## 5. Video Narrative Impact

### 5.1 How This Changes the Story (vs. v2)

The v2 research told a clean, surprising story: "Most things got cheaper relative to wages." The v3 cross-validation doesn't destroy that story — it **contextualizes** it:

1. **The v2 finding was correct BUT conditional.** It's true for the median worker. It's catastrophically wrong for the minimum-wage worker.

2. **The CPI perspective is the "neutral" benchmark.** When we strip out income effects entirely and just ask "did food outpace general inflation?", the answer is mixed: eggs and coffee yes, the rest mostly no. Chips are borderline.

3. **The minimum wage perspective reveals inequality.** Same economy, same products, same 25 years — but the experience depends entirely on where you sit in the income distribution.

### 5.2 The "Deflator Reveal" — Proposed Finale Structure

**Setup (from v2 race chart):** Show the median-wage RUPI race chart. Products race from 2000 to 2025. Most end below 1.0. Eggs soar. Coffee just barely crosses. The line is: *"Huh. Most things actually got cheaper."*

**The Turn:** "But cheaper... for whom?"

**Reveal 1 — CPI:** Same chart, new line. CPI-deflated RUPI is higher across the board. Chips cross above 1.0. Three products now more expensive. *"If we strip out income entirely and just adjust for inflation... the picture gets worse."*

**Reveal 2 — Minimum Wage:** The gut punch. All lines jump UP. Five of six products above 1.0. Eggs at 3.31. *"For the 1.1 million Americans earning federal minimum wage — and the millions more earning near it — almost everything costs more. Not because of shrinkflation. Because their paycheck hasn't moved in sixteen years."*

**Reveal 3 — Gold (optional, philosophical coda):** Everything collapses toward zero. *"And if you'd stored your money in gold instead of a paycheck... groceries are basically free. Same data. Same math. Different ruler."*

**Closing line:** *"Shrinkflation is real. But the biggest shrinkage isn't in your cereal box. It's in the question we forgot to ask: cheaper for whom?"*

---

## 6. Recommendations for Script

### 6.1 Structure the Finale as a "Lens Switch"

The video should NOT present all four deflators chronologically. Instead:
1. Tell the main race chart story with wages (Acts 1–3 from v2)
2. AFTER the race chart resolves, do the "lens switch" as the finale
3. Each new deflator should feel like a revelation, not a repetition

### 6.2 Keep Gold Brief

Gold is visually dramatic (everything crashes to near-zero) but intellectually niche. Spend 15–20 seconds on it max. The real emotional payload is minimum wage.

### 6.3 The Minimum Wage Moment Needs Screen Time

This deserves 30–45 seconds. Show the chart transformation. Let it breathe. Maybe add a visual: "Time since last minimum wage increase: 16 years, 8 months and counting." A counter ticking in the corner.

### 6.4 Don't Lose the Shrinkflation Thread

The deflator analysis could feel disconnected from the shrinkflation core thesis. Bridge it:
- *"Shrinkflation makes every product a little worse. But the frozen minimum wage makes every paycheck a little worse too. One is a corporate decision. The other is a policy choice."*

### 6.5 Data Visualization Recommendations

For the race chart "lens switch" moment:
- **Option A:** Keep the same chart, but animate the RUPI lines morphing as the deflator changes (smooth transition)
- **Option B:** Show 4 small multiples side by side after the main chart resolves
- **Option C:** Show ONLY the 2025 bar chart with all 4 deflators as grouped bars per product

Recommend **Option A** for the main reveal, **Option C** as a summary frame.

### 6.6 Fact-Check Callouts for Script

- ⚠️ Coffee 2008, 2009, 2019 prices are BLS-estimated due to data gaps
- ⚠️ Gold 2025 annual average is estimated (~$3,500) pending year-end data
- All CPI data is BLS-verified
- All minimum wage data is DOL-verified
- 2020 wage anomaly (compositional bias) affects ALL wage-deflated numbers for that year

---

## 7. Sources

1. [BLS CPI-U Data (CUUR0000SA0)](https://www.bls.gov/cpi/) — CPI-U All Items, U.S. City Average, monthly data averaged annually. Retrieved via BLS Public Data API v2.
2. [LBMA London PM Fix / Kitco Historical Gold Prices](https://www.kitco.com) — Annual average gold prices, standard reference for gold price history.
3. [MeasuringWorth Gold Price Dataset](https://www.measuringworth.com/gold/) — Academic gold price reference (Lawrence H. Officer and Samuel H. Williamson).
4. [Wikipedia: Gold as an Investment](https://en.wikipedia.org/wiki/Gold_as_an_investment) — Confirms key anchor points (2000: $273, 2005: $513, 2010: $1,410 year-end; Oct 2025: $4,000+).
5. [WSJ: Gold Prices Top $4,000 for First Time](https://www.wsj.com/finance/commodities-futures/gold-prices-top-4000-for-first-time) — David Uberti, Oct 7, 2025.
6. [U.S. Department of Labor: Minimum Wage History](https://www.dol.gov/agencies/whd/minimum-wage/history) — Federal minimum wage rates since 1938.
7. [BLS Average Price Data](https://www.bls.gov/data/#prices) — All product prices from research-v2 (series APU0000717311, APU0000708111, APU0000718311, APU0000709112, APU0000710211, APU0000710212).
8. [FRED: Median Usual Weekly Earnings (LES1252881500Q)](https://fred.stlouisfed.org/series/LES1252881500Q) — Nominal median earnings from research-v2.
9. [Wikipedia: Big Mac Index](https://en.wikipedia.org/wiki/Big_Mac_Index) — Confirmed insufficient data for longitudinal US price series.

---

## Appendix: Deflator Index Summary Table (Full Series)

| Year | Wage Index | CPI Index | Gold Index | Min Wage Index |
|------|-----------|-----------|------------|---------------|
| 2000 | 1.000 | 1.000 | 1.000 | 1.000 |
| 2001 | 1.038 | 1.028 | 0.971 | 1.000 |
| 2002 | 1.063 | 1.045 | 1.111 | 1.000 |
| 2003 | 1.082 | 1.068 | 1.301 | 1.000 |
| 2004 | 1.122 | 1.097 | 1.470 | 1.000 |
| 2005 | 1.131 | 1.134 | 1.595 | 1.000 |
| 2006 | 1.159 | 1.171 | 2.165 | 1.000 |
| 2007 | 1.212 | 1.204 | 2.491 | 1.000 |
| 2008 | 1.262 | 1.250 | 3.125 | 1.136 |
| 2009 | 1.288 | 1.246 | 3.484 | 1.272 |
| 2010 | 1.297 | 1.266 | 4.391 | 1.408 |
| 2011 | 1.318 | 1.306 | 5.634 | 1.408 |
| 2012 | 1.350 | 1.334 | 5.982 | 1.408 |
| 2013 | 1.358 | 1.353 | 5.057 | 1.408 |
| 2014 | 1.365 | 1.375 | 4.538 | 1.408 |
| 2015 | 1.404 | 1.376 | 4.158 | 1.408 |
| 2016 | 1.448 | 1.394 | 4.484 | 1.408 |
| 2017 | 1.509 | 1.423 | 4.509 | 1.408 |
| 2018 | 1.540 | 1.458 | 4.548 | 1.408 |
| 2019 | 1.598 | 1.485 | 4.993 | 1.408 |
| 2020 | 1.762 | 1.503 | 6.344 | 1.408 |
| 2021 | 1.741 | 1.574 | 6.448 | 1.408 |
| 2022 | 1.832 | 1.700 | 6.452 | 1.408 |
| 2023 | 1.937 | 1.770 | 6.953 | 1.408 |
| 2024 | 2.012 | 1.822 | 8.552 | 1.408 |
| 2025 | 2.107 | 1.870 | ⚠️ ~12.545 | 1.408 |
