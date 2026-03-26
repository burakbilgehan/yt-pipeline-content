# Pre-Research: Time vs Earnings — Feasibility Study

> Version: pre-research-v1
> Date: 2026-03-21
> Status: Preliminary — exploring data availability and video angles
> Agent: collector (web data) + director (synthesis)

---

## 1. Data Sources Found

### Primary Sources (High Reliability)

| Source | What It Has | Granularity | Coverage | URL |
|--------|------------|-------------|----------|-----|
| **ILO ILOSTAT** | Mean weekly hours by occupation (ISCO-08 level 2) | Country × Profession | ~100 countries, modelled estimates for 180+ | https://ilostat.ilo.org/topics/working-time/ |
| **OECD Average Wages** | Annual wages, PPP-adjusted | Country only | 38 OECD members | https://data.oecd.org/earnwage/average-wages.htm |
| **OECD Hours Worked** | Annual hours per worker (1950–2022) | Country only | 38 OECD members | https://data.oecd.org/emp/hours-worked.htm |
| **BLS OEWS** | Median/mean hourly wage, 800+ occupations | Profession × State × Metro | US only | https://www.bls.gov/oes/current/oes_nat.htm |
| **Eurostat SES** | Structure of Earnings Survey | Profession × Country | EU-27 | https://ec.europa.eu/eurostat |
| **Our World in Data** | Annual hours compiled from ILO/OECD | Country only | ~90 countries | via Wikipedia compilation |
| **UNECE** | Gross monthly wages (nominal USD) | Country only | ~50 countries incl. Central Asia | via Wikipedia compilation |

### Secondary / Computed
- **Penn World Table** — GDP per hour worked (productivity by country)
- **ILO COND database** — Wages by ISCO occupation for ~60 countries (partial, needs cleaning)
- **National equivalents of BLS** — UK (ONS ASHE), Germany (Destatis), Japan (MHLW), Australia (ABS)

---

## 2. Key Findings & Outliers

### 2a. Computed Hourly Earnings by Country (OECD wages ÷ OECD hours)

| Country | Annual Wage (PPP) | Annual Hours | **$/hour** |
|---------|------------------|-------------|-----------|
| Luxembourg | $94,447 | 1,473 | **$64.12** |
| Switzerland | $87,468 | 1,528 | **$57.24** |
| Denmark | $74,022 | 1,371 | **$53.99** |
| Norway | $74,864 | 1,424 | **$52.57** |
| Germany | $69,433 | 1,340 | **$51.81** |
| USA | $82,933 | 1,810 | **$45.82** |
| Australia | $70,763 | 1,707 | **$41.45** |
| UK | $63,691 | 1,531 | **$41.60** |
| Japan | $49,446 | 1,607 | **$30.77** |
| South Korea | $50,947 | 1,901 | **$26.80** |
| Greece | $32,257 | 1,886 | **$17.11** |
| Mexico | $20,433 | 2,226 | **$9.18** |

**Killer stat:** A German worker earns **5.6× more per hour** than a Mexican worker while working **40% fewer hours**.

**Greece paradox:** Works the most hours in the EU (1,886/yr) but earns the least ($17.11/hr).

### 2b. Country-Level Working Hours Extremes

**Most hours/year (2023, Our World in Data):**
| Country | Hours/year |
|---------|-----------|
| Sudan | 2,658 |
| UAE | 2,514 |
| Jordan | 2,483 |
| Pakistan | 2,471 |
| Colombia | 2,471 |
| Cambodia | 2,389 |
| India | 2,383 |
| China | 2,328 |

**Fewest hours/year:**
| Country | Hours/year |
|---------|-----------|
| Denmark | 1,381 |
| Norway | 1,384 |
| Germany | 1,386 |
| Netherlands | 1,440 |
| Iceland | 1,454 |
| France | 1,505 |

Germany (1,386) vs Cambodia (2,389) = **72% more hours** in Cambodia.

### 2c. Gender Gap in Working Hours

| Country | Men (h/week) | Women (h/week) | Gap |
|---------|-------------|----------------|-----|
| Pakistan | 51.28 | 35.05 | **16.2h** |
| Turkey | 44.40 | 39.55 | 4.9h |
| USA | 38.21 | 33.95 | 4.3h |
| Germany | 33.03 | 25.81 | 7.2h |
| São Tomé | 47.89 | **50.12** | **Women work MORE** |
| UAE | 48.24 | **48.42** | Women work more |

### 2d. Historical Trends (OECD, 1950–2022)

| Country | 1950 | 2022 | Change |
|---------|------|------|--------|
| France | 2,351 | 1,511 | **−36%** |
| Japan | 2,243 (1970) | 1,607 | −28% |
| Sweden | 1,824 | 1,440 | −21% |
| **USA** | **1,968** | **1,810** | **−8%** (remarkably flat!) |

The US barely reduced working hours in 72 years while Europe slashed theirs by 20-36%.

### 2e. Wage Stagnation Outliers

- **Italy:** Wages DECREASED in real terms — $52,237 (2000) → $51,019 (2024). Unique in OECD.
- **Japan:** Flat for 25 years — $50,109 (2000) → $49,446 (2024).
- **Greece:** Crashed and never recovered — $40,933 (2010) → $32,257 (2024).
- **Lithuania:** Tripled — $19,105 (2000) → $52,898 (2024).

### 2f. US Profession-Level Data (BLS, May 2023)

| Occupation | Employment | Median $/hr | Annual Mean |
|-----------|-----------|-------------|-------------|
| Chief Executives | 211K | $99.37 | $258,900 |
| Computer/Info Systems Mgrs | 593K | $81.50 | $180,720 |
| Software Developers | ~1.8M | ~$61 | ~$127K |
| Financial Managers | 787K | $75.05 | $174,820 |
| Management Analysts | 838K | $47.80 | $115,530 |
| Food Service Managers | 246K | $30.32 | $69,580 |
| Preschool/Daycare Admin | 64K | $26.10 | $61,320 |
| **All Occupations** | **151.9M** | **$23.11** | **$65,470** |

Note: US average wage ($63,932) vs median ($43,222) gap reveals significant inequality.

---

## 3. Data Availability Assessment

| What We Need | Source | Status | Notes |
|-------------|--------|--------|-------|
| Hours by country | OECD/ILO/Wikipedia | ✅ Excellent | Rich, multi-decade data |
| Wages by country (PPP) | OECD/UNECE | ✅ Excellent | PPP available for OECD members |
| Hours by profession (single country) | BLS (US) | ✅ Excellent | 800+ occupations, US only |
| Wages by profession (single country) | BLS (US) | ✅ Excellent | US only |
| Hours by profession × country | ILO ISCO | ✅ Good | ~100 countries, ISCO level 2 (9 broad groups) |
| Wages by profession × country | ILO COND / Eurostat | ⚠️ Partial | ~60 countries, needs cleaning |
| **Hourly earnings by profession × country** | **Must compute** | ⚠️ Derived | No direct source — combine hours + wages |
| Historical trends (hours) | OECD | ✅ Good | 1950–2022, OECD members only |
| Life satisfaction / happiness | OECD Better Life Index, Gallup | ⚠️ Subjective | Hard to measure, user skeptical — skip unless compelling |

**Bottom line:** Country-level data is rock solid. Profession-level data exists but cross-country profession comparison requires combining multiple sources and is only clean for OECD/EU countries.

---

## 4. Suggested Video Angles (Ranked)

### Angle 1: "The Hourly Wage Map" — Who Really Earns More?
**Concept:** Convert all country wages to $/hour. Reveal that countries working the most earn the least per hour. The "work more = earn more" myth demolished by data.
- **Data richness:** ⭐⭐⭐⭐⭐ (OECD data is clean and complete)
- **Surprise factor:** ⭐⭐⭐⭐ (Greece/Mexico paradox is strong)
- **Visual potential:** ⭐⭐⭐⭐⭐ (scatter plot: hours on X, $/hr on Y — beautiful inverse correlation)
- **Channel fit:** ⭐⭐⭐⭐⭐ (pure data, no opinion needed)

### Angle 2: "Same Job, Different World" — Cross-Country Profession Comparison
**Concept:** Pick 5-6 professions, show how the same job pays wildly differently across countries — not just in dollars but in hours required.
- **Data richness:** ⭐⭐⭐ (ILO ISCO + Eurostat — needs cleaning, limited to ~60 countries)
- **Surprise factor:** ⭐⭐⭐⭐⭐ (a teacher in Luxembourg vs. a teacher in India)
- **Visual potential:** ⭐⭐⭐⭐ (bar chart races, side-by-side comparisons)
- **Channel fit:** ⭐⭐⭐⭐⭐

### Angle 3: "The Countries That Stopped Working Less" — Historical Divergence
**Concept:** Since 1950, Europe cut working hours by 30%+. The US barely moved (−8%). Why? What happened?
- **Data richness:** ⭐⭐⭐⭐⭐ (OECD historical data is clean)
- **Surprise factor:** ⭐⭐⭐⭐ (US stagnation is genuinely surprising)
- **Visual potential:** ⭐⭐⭐⭐⭐ (animated line chart divergence over 70 years)
- **Channel fit:** ⭐⭐⭐⭐ (Trends Over Time pillar)

### Angle 4: "Golden Jobs & Trap Jobs" — The Time-Money Matrix
**Concept:** Plot professions on a 2×2 matrix: hours vs. pay. Identify "golden" jobs (low hours, high pay) and "trap" jobs (high hours, low pay). Where do different countries cluster?
- **Data richness:** ⭐⭐⭐ (US data is rich; international needs assembly)
- **Surprise factor:** ⭐⭐⭐⭐⭐ (people love knowing which jobs are "traps")
- **Visual potential:** ⭐⭐⭐⭐⭐ (2×2 quadrant chart — instantly readable)
- **Channel fit:** ⭐⭐⭐⭐

### Angle 5: Hybrid — Combine Angle 1 + 2
**Concept:** Start macro (country-level hourly wage map), then zoom into profession-level for 3-4 countries. Best of both worlds.
- **Data richness:** ⭐⭐⭐⭐
- **Surprise factor:** ⭐⭐⭐⭐⭐
- **Visual potential:** ⭐⭐⭐⭐⭐
- **Channel fit:** ⭐⭐⭐⭐⭐

---

## 5. Raw Data Notes

All data points above are from:
- OECD (2024 wages, 2022 hours) — PPP-adjusted USD
- ILO (2023 modelled estimates via Our World in Data)
- BLS (May 2023 OEWS survey, 1.1M establishments)
- UNECE (2024 nominal monthly wages)
- Wikipedia compilations sourcing the above

**Caveat:** Part-time work inclusion varies by country and significantly affects "average hours" figures. Germany's low hours (1,340) partly reflects high part-time employment rates, not just shorter full-time hours. When comparing, acknowledge this.

**Missing:** Sub-Saharan Africa, most of South Asia, and Central Asia have limited wage-by-profession data. ILO modelled estimates exist for hours but wage data is sparse outside OECD/EU.
