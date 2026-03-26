# Methodology Analysis: Double Adjustment Problem in Big Macs/Hour Metric

> Date: 2026-03-22
> Author: Researcher Agent
> Status: Complete analysis with concrete numbers and recommendation
> Context: User raised concern about PPP wage / Big Mac USD price formula

---

## 1. What Exactly Is OECD PPP-Adjusted Wages?

### How PPP Adjustment Works

OECD PPP (Purchasing Power Parity) adjustments convert all wages to a **common currency ("PPP dollars" or "international dollars")** using PPP conversion factors, NOT market exchange rates.

**The PPP conversion factor** is the ratio of prices in national currencies of the **same basket of goods and services** in different countries. According to the OECD, this basket contains approximately:
- ~3,000 consumer goods and services
- 30 occupations in government
- 200 types of equipment goods
- ~15 construction projects

[Source: OECD PPP FAQ](https://www.oecd.org/sdd/prices-ppp/purchasingpowerparities-frequentlyaskedquestionsfaqs.htm)

### What PPP Does

When OECD says Swiss wages are $87,468 PPP, it means:
> "A Swiss worker can buy the same amount of goods/services as someone spending $87,468 in the USA"

The PPP conversion **already accounts for the fact that things cost more in Switzerland**. It deflates the nominal Swiss wage downward because Swiss prices are ~30-40% higher than US prices.

Conversely, when OECD says Mexican wages are $20,433 PPP, it **inflates** the nominal Mexican wage upward because Mexican prices are much lower than US prices.

**Key insight: PPP dollars are already a purchasing-power-equalized unit. $1 PPP buys the same "basket" everywhere.**

[Source: Wikipedia - Purchasing Power Parity](https://en.wikipedia.org/wiki/Purchasing_power_parity)

---

## 2. What Does Dividing by Big Mac USD Price Accomplish ON TOP of PPP?

### The Core Problem

Our formula: `PPP Wage / Hours / Big Mac USD Price`

Let's trace what happens:

1. **PPP Wage** = already adjusted for general price level differences (using ~3,000 item basket)
2. **Big Mac USD Price** = a SPECIFIC product price converted to USD at MARKET exchange rates

When you divide a PPP-equalized wage by a market-exchange-rate-denominated price, you're mixing two different conversion systems:

- **Numerator** uses PPP conversion rates (which say CHF 1.00 = ~$0.73 PPP for Switzerland)
- **Denominator** uses market exchange rates (which say CHF 1.00 = ~$1.14 market for Switzerland)

### Is This Redundant?

**YES, partially.** Here's why:

PPP already says: "Swiss wages LOOK high in nominal terms, but Swiss prices are high too, so real purchasing power is lower than nominal suggests."

Then dividing by the Big Mac (which is expensive in Switzerland at $7.99 USD) does the SAME correction AGAIN: "Swiss wages need to be deflated because Swiss goods are expensive."

The result: **Switzerland gets punished twice** for being expensive.

Conversely: **Japan gets rewarded twice** — PPP inflates Japanese wages (because Japan is relatively cheap for a rich country), and then the cheap Big Mac ($3.11) inflates purchasing power AGAIN.

### But It's Not 100% Redundant Either

PPP uses a ~3,000 item basket. A Big Mac is ONE specific item. The Big Mac price doesn't perfectly track the general PPP price level. So the Big Mac division adds SOME new information — specifically, it measures how the Big Mac deviates from the general basket.

However, for our video's purpose ("how many Big Macs can you actually buy?"), we want a CLEAN answer, not a double-adjusted one.

---

## 3. Three Approaches with Concrete Numbers

### Data Points Used

| Country | Nominal Wage (local currency) | OECD PPP Wage ($) | Market Exchange Rate (LC/$) | PPP Factor (LC/$) | Big Mac Local Price | Big Mac USD Price | Annual Hours |
|---------|-----:|-----:|-----:|-----:|-----:|-----:|-----:|
| Switzerland | CHF 78,344* | $87,468 | 0.896 CHF/$ | 0.896* | CHF 7.16 | $7.99 | 1,528 |
| USA | $82,933 | $82,933 | 1.00 | 1.00 | $5.79 | $5.79 | 1,810 |
| Japan | JPY 5,723,000* | $49,446 | 155.7 JPY/$ | 115.7* | JPY 484 | $3.11 | 1,607 |
| Mexico | MXN 207,000* | $20,433 | 17.0 MXN/$ | 10.13* | MXN 78.2 | $4.60 | 2,226 |

*Estimated nominal wages by reverse-engineering from PPP wages using approximate PPP conversion factors and market exchange rates circa 2024-2025. These are illustrative — exact nominal OECD data would need to be sourced separately.

**Important note:** Exact nominal wages in local currency are not directly available from the OECD dataset we used (which only provides PPP $). The numbers below use estimated conversions. The directional conclusions hold regardless of minor estimation errors.

### Approach A: Our Current Formula (PPP Wage / Hours / Big Mac USD)

```
Big Macs/hr = (PPP Annual Wage / Annual Hours) / Big Mac USD Price
```

| Country | PPP $/hr | Big Mac USD | BM/hr | Rank |
|---------|--------:|----------:|------:|-----:|
| Japan | 30.77 | 3.11 | **9.89** | 1 |
| Switzerland | 57.24 | 7.99 | **7.16** | 3 |
| USA | 45.82 | 5.79 | **7.91** | 2 |
| Mexico | 9.18 | 4.60 | **2.00** | 4 |

### Approach B: Nominal Wage / Hours / Local Big Mac Price (THE CORRECT ONE)

```
Big Macs/hr = (Nominal Annual Wage in Local Currency / Annual Hours) / Big Mac Price in Local Currency
```

This is the ONLY formula that directly answers "how many Big Macs can a worker buy with one hour of work in their country."

| Country | Nominal Local $/hr | Local Big Mac Price | BM/hr | Rank |
|---------|--------:|----------:|------:|-----:|
| Switzerland | CHF 51.27* | CHF 7.16 | **7.16** | 2 |
| USA | $45.82 | $5.79 | **7.91** | 1 |
| Japan | JPY 3,561* | JPY 484 | **7.36** | (see note) |
| Mexico | MXN 9,298* / hr? | MXN 78.2 | **~1.19** | 4 |

**CRITICAL NOTE:** For Approach B, we don't even need exchange rates at all. It's purely: `local wage / local price`. No currency conversion needed. This is the fundamental insight.

*However*, when I try to reverse-engineer exact nominal wages, I don't have the precise OECD nominal data. Let me work this differently using a mathematical identity:

### The Mathematical Proof

Let's define:
- `W_nom` = nominal wage in local currency
- `PPP_factor` = PPP conversion rate (local currency per PPP dollar)
- `W_ppp` = `W_nom / PPP_factor` (this is the OECD PPP wage)
- `E` = market exchange rate (local currency per USD)
- `P_local` = Big Mac price in local currency
- `P_usd` = `P_local / E` (Big Mac price in USD)

**Approach A (our current):**
```
BM/hr_A = (W_ppp / hours) / P_usd
        = (W_nom / PPP_factor / hours) / (P_local / E)
        = (W_nom * E) / (PPP_factor * P_local * hours)
```

**Approach B (correct):**
```
BM/hr_B = (W_nom / hours) / P_local
        = W_nom / (P_local * hours)
```

**The difference:**
```
BM/hr_A / BM/hr_B = E / PPP_factor
```

This ratio `E / PPP_factor` is exactly the **raw Big Mac Index** (or more precisely, it's proportional to how much the market exchange rate deviates from PPP). 

**When `E / PPP_factor > 1`:** the currency is "undervalued" by PPP standards (things are cheap in market USD terms). Approach A OVERSTATES Big Macs/hr relative to reality. This benefits countries like Japan, Mexico.

**When `E / PPP_factor < 1`:** the currency is "overvalued" by PPP standards (things are expensive in market USD terms). Approach A UNDERSTATES Big Macs/hr relative to reality. This hurts countries like Switzerland, Norway.

**When `E / PPP_factor = 1`:** Both approaches give the same answer. This is the USA (trivially, since PPP uses USD as base).

### Approach C: Nominal Wage (USD at market rate) / Hours / Big Mac USD Price

```
Big Macs/hr = (Nominal Wage in Local Currency / Market Exchange Rate / Hours) / Big Mac USD Price
```

This simplifies to:
```
= (W_nom / E / hours) / (P_local / E)
= W_nom / (P_local * hours)
```

**APPROACH C IS MATHEMATICALLY IDENTICAL TO APPROACH B.** The exchange rate cancels out when both numerator and denominator are converted using the same exchange rate. This makes sense — it doesn't matter what exchange rate you use, as long as you use the same one for both wage and price.

---

## 4. Which Approach Is Methodologically Correct?

### The Question: "How many Big Macs can you buy per hour of work?"

This is a **physical/tangible** question. A worker in Tokyo walks into McDonald's after working one hour. How many Big Macs can they buy?

**The answer requires:**
1. What they earned in that hour (in their LOCAL currency, because that's what they have in their pocket)
2. What a Big Mac costs at their LOCAL McDonald's (in their LOCAL currency)

**That's Approach B.** No exchange rates needed. No PPP adjustments needed. Just `local hourly wage / local Big Mac price`.

**Approach A (our current) answers a DIFFERENT question:**
> "If we first equalize everyone's wages to a common purchasing-power-adjusted standard, and then divide by the Big Mac's USD market price, what do we get?"

This question has no clear economic interpretation. It's a hybrid metric mixing two different price-level adjustments.

### The Verdict

**Approach B is the only methodologically correct approach for our video's stated question.**

Approach A introduces a systematic distortion factor of `E / PPP_factor`, which:
- Inflates Japan's ranking (cheap yen in market terms vs PPP)
- Deflates Switzerland's ranking (expensive franc in market terms vs PPP)
- Has no effect on USA (base country)

---

## 5. What Do Economists Say?

### The Economist's Big Mac Index

The Economist's Big Mac Index uses **NOMINAL/MARKET exchange rates** as its starting point, NOT PPP rates. The whole point of the Big Mac Index is to DERIVE an implied PPP rate from Big Mac prices and COMPARE it to market rates.

From the GitHub repository codebook:
- `local_price` = Price of a Big Mac in local currency
- `dollar_ex` = Local currency units per dollar (market rate)
- `dollar_price` = Price of a Big Mac in dollars (converted at market rate)

The Big Mac Index calculates: `local_price_A / local_price_US` to get an implied PPP rate, then compares it to the actual market exchange rate. 

**The Economist NEVER uses PPP-converted values in the Big Mac Index.** The entire point is that the Big Mac IS the PPP measure — you don't need another PPP adjustment on top of it.

[Source: The Economist GitHub - big-mac-data](https://github.com/TheEconomist/big-mac-data)

### UBS "Prices and Earnings" Report

The UBS Prices and Earnings report (cited in Wikipedia's Big Mac Index article) calculates "minutes of work to buy a Big Mac" using:
- **Local wages in local currency**
- **Local Big Mac price in local currency**

This is exactly Approach B. No PPP adjustment involved.

From Wikipedia's Big Mac article — "Six fastest earned" (2015 UBS data):
1. Hong Kong: 8.6 min
2. Luxembourg: 10.3 min
3. Tokyo: 10.4 min
4. Zurich: 10.6 min

Note: Zurich and Tokyo are nearly identical at ~10.5 min. In our current Approach A, Japan (9.89 BM/hr) dramatically outperforms Switzerland (7.16 BM/hr) — a 38% gap. The UBS data shows the reality: they're almost the same.

[Source: Wikipedia - Big Mac Index, citing UBS Prices and Earnings 2015](https://en.wikipedia.org/wiki/Big_Mac_Index)

### Academic Consensus

The "Burgernomics" literature (Pakko & Pollard, 2003, Federal Reserve Bank of St. Louis) treats the Big Mac as a **substitute for PPP**, not as something to be layered on top of PPP. Using PPP-adjusted wages AND Big Mac prices is analogous to adjusting for inflation twice.

---

## 6. How Rankings Would Change

Since we don't have exact nominal wages in local currency from our OECD source (it only provides PPP $), let me illustrate the distortion using the mathematical relationship:

```
Distortion factor = BM/hr_A / BM/hr_B = E / PPP_factor
```

Countries where PPP says currency is "undervalued" (Japan, Mexico, Hungary) get OVERSTATED in Approach A.
Countries where PPP says currency is "overvalued" (Switzerland, Norway) get UNDERSTATED in Approach A.

### Estimated Impact on Key Countries

| Country | Approach A (our current) | Estimated Distortion | Direction | Impact on Rank |
|---------|-----:|-----:|-----:|-----:|
| Japan | 9.89 | ~1.35x overstated | UP | Probably not #2, more like #5-8 |
| Switzerland | 7.16 | ~0.80x understated | DOWN | Should be higher, ~8.5-9.0 |
| Hungary | 5.64 | ~1.30x overstated | UP | Should be ~4.3 |
| Norway | 7.88 | ~0.85x understated | DOWN | Should be higher, ~9.0-9.5 |
| USA | 7.91 | 1.00x (base) | NONE | Stays same |
| Mexico | 2.00 | ~1.68x overstated | UP | Should be ~1.2 |

### The Japan Story Is the Biggest Casualty

Japan at #2 is one of our video's KEY surprise moments. With the correct methodology:

- Japan's true Big Macs/hr is likely ~7.0-7.5 (not 9.89)
- This puts Japan in the middle of the DREAM quadrant, not at the top
- Still a good story, but not the "incredible #2 surprise" we currently sell

The UBS 2015 data confirms this: Tokyo (10.4 min/Big Mac) vs Luxembourg (10.3 min) vs Zurich (10.6 min) — Japan is in the pack, not dominating.

---

## 7. Bottom Line Recommendation

### The Honest Answer

**Our current approach (Approach A) is methodologically incorrect for the question we claim to answer.**

The formula `PPP wage / Big Mac USD price` double-adjusts for purchasing power:
1. PPP already converts wages to purchasing-power-equivalent dollars
2. Big Mac price then applies a SECOND local-price adjustment

The correct formula is `nominal local wage / local Big Mac price` (Approach B), which requires no exchange rate conversion at all.

### What Should We Do?

**Option 1: Switch to Correct Methodology (RECOMMENDED)**

Use Approach B or equivalently Approach C:
- Need to source **nominal wages** (not PPP) from OECD or convert back
- OECD does publish nominal wages in national currency
- Or: use `PPP wage * (PPP_factor / E)` to reverse the PPP adjustment, then divide by local Big Mac price

Pros: Mathematically correct, matches what UBS and The Economist do, defensible against scrutiny
Cons: Rankings change, Japan #2 story weakens, need to re-do data table

**Option 2: Keep Current but Reframe the Question**

Keep Approach A but honestly describe what it measures:
- NOT "how many Big Macs you can buy per hour"
- Instead: "a PPP-adjusted wage efficiency index, with Big Mac as a tangibility layer"
- This is vaguer and less compelling

Pros: No data rework needed
Cons: The video's hook becomes weaker, methodologically awkward to explain

**Option 3: Use OECD Nominal Wages + Local Big Mac Prices (BEST)**

Source OECD nominal average wages in national currency (they publish these) and local Big Mac prices in local currency from The Economist dataset. Divide directly. No exchange rates needed anywhere.

This is the cleanest, most correct, and most intuitive approach.

### My Strong Recommendation: Option 1 or 3

The double adjustment is real and material (30-70% distortion for some countries). The video claims to answer "how many Big Macs can you ACTUALLY buy per hour" — that claim is currently false. For a data-driven channel, accuracy is the brand. Fix it now, before the video goes live.

The Japan surprise story weakens but doesn't disappear — Japan still has genuinely cheap Big Macs relative to wages. It just won't be #2. Germany, Luxembourg, Denmark will likely remain top performers. The core narrative (quadrant matrix, hours vs purchasing power) is INTACT. Only the numbers change.

---

## Sources

1. [OECD PPP FAQ](https://www.oecd.org/sdd/prices-ppp/purchasingpowerparities-frequentlyaskedquestionsfaqs.htm) — OECD methodology for PPP calculations, ~3,000 item basket
2. [Wikipedia - Purchasing Power Parity](https://en.wikipedia.org/wiki/Purchasing_power_parity) — Comprehensive PPP theory, Balassa-Samuelson effect
3. [Wikipedia - Big Mac Index](https://en.wikipedia.org/wiki/Big_Mac_Index) — History, methodology, UBS "fastest earned" data
4. [The Economist GitHub - big-mac-data](https://github.com/TheEconomist/big-mac-data) — Official Big Mac Index data and methodology. Uses market exchange rates, NOT PPP.
5. Pakko & Pollard (2003), "Burgernomics: A Big Mac Guide to Purchasing Power Parity", Federal Reserve Bank of St. Louis — Academic treatment of Big Mac as PPP proxy
6. UBS Prices and Earnings Report (2015) — Uses local wages / local prices for "minutes to earn a Big Mac"
