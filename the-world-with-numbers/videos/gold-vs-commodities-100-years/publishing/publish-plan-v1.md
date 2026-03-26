# Publishing Plan: What If You Priced Everything in Gold? (100 Years of Data)
> version: 1
> based_on: production-v1
> date: 2026-03-17

## Schedule
- **Upload date:** 2026-03-18 (Tuesday)
- **Upload time:** 15:00 UTC (11:00 AM EST / 8:00 AM PST)
- **Rationale:** First video on channel — no historical data to optimize against. Tuesday mid-morning US time is a safe general-purpose slot. Finance/investing content performs well on weekday mornings when audiences are in "learning mode." Avoid weekend drops where finance content underperforms.

## YouTube Metadata

### Title Options (A/B testing recommended)
- **Primary:** What If You Priced Everything in Gold? (100 Years of Data) *(58 chars)*
- **A/B test:** The Dow Gained 26,000% — But Only 132% Priced in Gold *(55 chars)*
- **Backup:** Gold vs Stocks vs Commodities: 100 Years of Real Returns *(56 chars)*

### Description
```
What happens when you price the Dow, S&P 500, Nikkei, silver, oil, and other major assets in gold over 100 years? The results will change how you think about money.

The Dow Jones gained 26,000% since 1925. Impressive, right? But when you measure it in gold instead of dollars, that gain shrinks to just 132% — less than 1% per year. This video uses 175,000+ daily data points to price 9 major assets in gold terms from 1925 to 2025 through an animated horse race chart.

🏆 The 100-Year Scoreboard (Gold-Priced Returns):
• Nikkei 225: +942%
• S&P 500: +237%
• DAX: +224%
• Dow Jones: +132%
• FTSE 100: +41%
• Silver: −66%
• Copper: −67%
• Oil: −74%
• Platinum: −95%

Every single commodity lost value against gold. Every stock index survived — but barely.

⏱️ Timestamps:
0:00 — The Dow's Illusion
0:17 — How to Price Assets in Gold
1:01 — Boom, Bust & Revaluation (1925–1944)
2:31 — Post-War Boom (1944–1971)
3:35 — Nixon Shock & the End of Bretton Woods (1971–1980)
4:41 — The Great Reversal (1980–2000)
5:58 — Gold's Revenge (2000–2025)
7:28 — The 100-Year Scoreboard
8:25 — Final Thoughts

📊 Data source: Stooq.com (175,000+ daily data points, 1925–2025)
🎵 Music: "Taste" by TrackTribe (YouTube Audio Library)

If you think about investing, inflation, or what "real value" even means — this video is for you. Gold doesn't lie.

👉 Subscribe to The World With Numbers for more data-driven stories that challenge how you see the world.

#GoldVsStocks #PricedInGold #Investing
```

### Tags (28 tags, 499 chars — under 500 limit)
priced in gold, gold vs stocks, gold vs stocks 100 years, dow jones priced in gold, gold vs dollar, gold vs s&p 500, gold vs commodities, real returns investing, gold standard, nixon shock 1971, bretton woods, gold price history, 100 years of stock market, dow jones 100 years, gold as money, gold investing, stock market vs gold, silver vs gold, oil priced in gold, nikkei 225 history, inflation adjusted returns, real value of money, gold vs inflation, long term investing, asset comparison, economics explained, facts, data

### Other Settings
- **Category:** Education (ID: 27)
- **Language:** English (en)
- **Visibility:** Public (first video — no reason to hide it)
- **Made for kids:** No
- **Comments:** Enabled
- **Embedding:** Enabled

## Engagement

### End Screen (last 20 seconds: 8:16–8:36)
- Subscribe button (centered)
- NO "next video" card (no other videos on channel yet)
- Update end screen once second video is published

### Cards
- None for first video (no other content to link to)

### Pinned Comment
```
📊 Full scoreboard in gold terms (1925–2025):
🥇 Nikkei 225: +942%
🥈 S&P 500: +237%
🥉 DAX: +224%
4. Dow Jones: +132%
5. FTSE 100: +41%
6. Silver: −66%
7. Copper: −67%
8. Oil: −74%
9. Platinum: −95%

What surprised you the most? Drop it below 👇

Data: 175,000+ daily data points from Stooq.com
```

### Community Post (publish after upload)
```
Our first video is live! 🎬

What if you priced every major asset — stocks, oil, silver, platinum — in gold instead of dollars?

We crunched 175,000+ data points across 100 years and the results are... humbling.

The Dow gained 26,000% in dollars.
In gold? Just 132%.

Watch the full breakdown → [link]

#PricedInGold #DataDriven
```

---

## Pre-Publish Checklist

### ✅ Ready
- [x] Video file rendered (250.3 MB, 8:36, 1080p 30fps)
- [x] Title finalized (58 chars, under 100 limit)
- [x] Description complete with timestamps, hashtags, CTA
- [x] Tags optimized (499/500 chars)
- [x] Category set (Education)
- [x] Pinned comment drafted
- [x] Community post drafted
- [x] Music attribution included in description
- [x] Data source credited
- [x] Timestamps verified against video-config.json scenes
- [x] No copyright-claimed content (YouTube Audio Library music)

### ⚠️ Issues to Resolve

#### 🔴 CRITICAL: Video filename mismatch
Upload script expects: `production/output/final.mp4`
Actual file: `production/output/gold-vs-commodities-100-years.mp4`
**Action needed:** Rename or copy the file to `final.mp4` before upload.

#### 🔴 CRITICAL: No thumbnail
No thumbnail file found in the project directory.
YouTube will auto-generate one, but custom thumbnails get 2-3x higher CTR.
**Action needed:** Create a thumbnail (1280x720, <2MB) before publishing.
**Suggested concept:** Gold bar on one side, crashing stock chart on other. Big text: "100 YEARS" and "PRICED IN GOLD". Use gold (#C8A94E) and dark background.

#### 🟡 WARNING: Channel handle discrepancy
- `channel-config.json` says: `@theworldwithnumbers`
- User provided: `@sickmananalytics`
**Action needed:** Confirm which YouTube channel this uploads to. Update channel-config.json if needed.

#### 🟡 WARNING: YouTube API credentials
Upload requires `YOUTUBE_CLIENT_ID`, `YOUTUBE_CLIENT_SECRET`, `YOUTUBE_REFRESH_TOKEN` in `.env`
**Action needed:** Verify these are set up for the correct channel.

#### 🟡 INFO: Tags trimmed
Original tags (36 items, 611 chars) exceeded 500 char limit.
Dropped 8 lower-priority tags: financial history, data visualization, investing data, the world with numbers, ranking, education, numbers, comparison.
The channel name "the world with numbers" was dropped from tags but appears in description.

#### 🟡 INFO: Description special characters
Description uses `−` (minus sign, U+2212) for negative returns and `–` (en dash, U+2013) for ranges.
YouTube renders these correctly — no issue, but flagging for awareness.
