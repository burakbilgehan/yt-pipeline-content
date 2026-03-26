# FTE Hours Research — Full-Time Equivalent Working Hours

**Date:** 2026-03-22  
**Status:** RESOLVED — Keeping OECD ANHRS (all workers) with in-video explanation  

## Research Question

Can we find "full-time workers only" annual hours data for all 34 OECD countries to replace the OECD ANHRS metric (which includes part-time workers)?

## Findings

### OECD (Primary Source)
- OECD publishes **"Average annual hours actually worked per worker"** (ANHRS) — this includes ALL workers (full-time + part-time)
- OECD does **NOT** publish a separate "full-time only" annual hours dataset
- The OECD `AV_AN_WAGE` methodology internally uses "usual weekly hours per full-time employee" for FTE conversion in salary calculations, but this intermediate variable is not published as a standalone dataset

### Eurostat (European Only)
- Eurostat publishes **"Average number of usual weekly hours of work in main job"** for full-time employees
- Coverage: EU/EEA countries only — **missing JPN, USA, KOR, AUS, CAN, NZL, ISR, MEX**
- Cannot be used for a 34-country comparison

### ILO (Partial)
- ILO ILOSTAT has hours data but coverage is inconsistent across all 34 countries
- Different methodologies by country make direct comparison unreliable

## The Japan Anomaly

Japan 2022 OECD hours: **1,607** — lower than USA (1,810) and OECD avg (1,751)

### Historical Trend
| Year | Hours | Change |
|------|-------|--------|
| 1990 | 2,031 | — |
| 2000 | 1,821 | -10.3% |
| 2010 | 1,733 | -4.8% |
| 2022 | 1,607 | -7.3% |

**Total decline: -21% in 32 years**

### Why the Number Is Correct (for what it measures)
The low number reflects Japan's **high part-time employment rate**, driven by:

1. **"Freeter" culture** — Young people choosing part-time/irregular employment
2. **Women entering workforce** predominantly as part-time (パート, "paato") workers
3. **Aging population** working part-time post-retirement (re-employment system)
4. **Government labor reforms:**
   - "Premium Friday" campaign (leave at 3pm on last Friday)
   - Overtime limit regulations (2019 Work Style Reform)
   - Karoshi prevention measures

**Full-time Japanese workers still work extreme hours** — karoshi (death from overwork) cases continue to be documented. But the OECD average gets pulled down by the large part-time workforce.

### Same Effect in Netherlands
Netherlands 2022: **1,427 hours** (lowest in dataset). The EU's highest part-time employment rate (~50% of workforce) creates the same averaging effect.

## Decision

**Keep OECD ANHRS as-is.** Rationale:

1. **Source consistency** — Same methodology for all 34 countries
2. **No viable alternative** — No single dataset covers all 34 countries with FTE-only hours
3. **Storytelling value** — The Japan anomaly becomes a narrative feature:
   - "We know this surprises you. Here's why the number is actually correct..."
   - Teaches viewers about statistical literacy (average vs. median, sample composition)
4. **Methodological honesty** — Better to use the official stat and explain caveats than to mix-and-match sources

## Video Approach

In the video, when Japan appears in the low-hours quadrant:
- Acknowledge the surprise explicitly
- Brief explanation of part-time worker inclusion
- Frame as "this is what the data says — and here's why it's not wrong"
- Consistent with channel identity: "no opinions, numbers speak for themselves"
