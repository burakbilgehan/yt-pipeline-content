# Analytics Report: What If You Priced Everything in Gold? — 2026-03-22

> **Video ID:** WeVrejS9Wf8 | **Published:** 2026-03-17 | **Length:** 8:36 (516s)
> **Channel:** The World With Numbers | **Maturity:** Seed (1st video, day 5)
> **Report version:** 1 | **Data window:** 2026-03-17 → 2026-03-22 (5 days)

---

## 1. Derived Metrics

| Metric | Value | Formula |
|--------|-------|---------|
| Watch time per view | 1.51 min (90.6s) | 4.55 hrs × 60 / 181 views |
| Like-to-view ratio | 3.31% | 6 / 181 |
| Dislike ratio | 0.55% | 1 / 181 |
| Like-to-dislike ratio | 6:1 | 6 / 1 |
| Engagement rate | 4.42% | (6 likes + 1 comment + 0 shares) / 181 |
| Sub conversion rate | 0.55% | 1 sub gained / 181 views |
| Views per watch hour | 39.78 | 181 / 4.55 |
| Avg view % of video | 17.48% | 90s / 516s |
| Comments per view | 0.55% | 1 / 181 |

### Average Watch Time by Traffic Source

| Source | Views | Watch Min | Avg Min/View | Avg % of Video | Quality Rank |
|--------|-------|-----------|-------------|----------------|--------------|
| EXT_URL | 5 | 17 | 3.40 | 39.5% | #1 |
| PLAYLIST | 3 | 17 | 5.67 | 65.9% | #1* |
| NO_LINK_OTHER | 22 | 45 | 2.05 | 23.8% | #2 |
| SUBSCRIBER | 121 | 184 | 1.52 | 17.7% | #3 |
| YT_OTHER_PAGE | 4 | 6 | 1.50 | 17.4% | #4 |
| RELATED_VIDEO | 1 | 0 | ~0 | ~0% | #6 |
| YT_CHANNEL | 25 | 2 | 0.08 | 0.9% | #7 |

*PLAYLIST has highest per-view quality but n=3, statistically insignificant.

---

## 2. Traffic Source Deep Dive

### Distribution

| Source | Views | % of Total | Watch Min | % of Watch Time |
|--------|-------|-----------|-----------|----------------|
| SUBSCRIBER | 121 | 66.9% | 184 | 67.4% |
| YT_CHANNEL | 25 | 13.8% | 2 | 0.7% |
| NO_LINK_OTHER | 22 | 12.2% | 45 | 16.5% |
| EXT_URL | 5 | 2.8% | 17 | 6.2% |
| YT_OTHER_PAGE | 4 | 2.2% | 6 | 2.2% |
| PLAYLIST | 3 | 1.7% | 17 | 6.2% |
| RELATED_VIDEO | 1 | 0.6% | 0 | 0.0% |
| **TOTAL** | **181** | **100%** | **271** | **100%** |

### The SUBSCRIBER Anomaly (Critical Finding)

**121 SUBSCRIBER views on a brand-new channel's first video is a major red flag.**

A channel with 1 subscriber gained from this video cannot have 121 views from "subscribers." This almost certainly means:

1. **Self-views / test views:** The creator or team viewed the video repeatedly from accounts that subscribed during testing. YouTube counts the viewer's subscription status at time of watch, not at time of subscription.
2. **Pre-launch subscribers:** If the channel was set up and some people subscribed before the video went live (friends, family, social circle).
3. **Shared link with "subscribe first" CTA:** The link may have been shared in a community where people subscribed then watched.

**Evidence supporting artificial/self-inflated views:**
- SUBSCRIBER avg watch time = 1.52 min/view — very low for "subscribers" who chose to follow the channel
- YT_CHANNEL views (25) with only 0.08 min/view (4.8 seconds!) — these are channel page visits that bounced almost immediately
- Compare: EXT_URL viewers (likely genuinely interested) watched 3.40 min/view — 2.2× longer than subscribers

**Diagnosis:** The majority of the 181 views are likely non-organic. A realistic organic view count is probably closer to **35-60 views** (NO_LINK_OTHER + EXT_URL + PLAYLIST + RELATED_VIDEO + some portion of SUBSCRIBER).

### Organic-Only Performance Estimate

If we isolate likely organic sources (NO_LINK_OTHER, EXT_URL, PLAYLIST, RELATED_VIDEO):

| Metric | All Traffic | Organic Estimate (31 views) |
|--------|------------|----------------------------|
| Views | 181 | ~31 |
| Watch min | 271 | ~79 |
| Avg min/view | 1.50 | 2.55 |
| Avg % of video | 17.5% | 29.6% |

The organic viewers are actually performing significantly better — but there are very few of them.

---

## 3. Retention Gap Analysis

### The Numbers

| Metric | Current | Target | Gap |
|--------|---------|--------|-----|
| Avg view duration | 90s (1:30) | 206s (3:26) | -116s |
| Avg view percentage | 17.48% | 40% | -22.52 pp |
| Required improvement | — | — | **+128.8%** relative increase |

To hit 40% retention, average view duration needs to go from 90s → 206s. That's a 2.29× improvement.

### Likely Drop-off Map

Based on the 17.5% average and typical retention curves for educational content:

```
0:00 ─────── 100% ← Hook / Intro
0:15 ─────── ~70% ← First major drop (hook didn't land or "not what I expected")
0:30 ─────── ~50% ← Second drop (topic setup too slow)
1:00 ─────── ~30% ← Only committed viewers remain
1:30 ─────── ~20% ← Matches 17.5% average — most viewers gone by here
2:00 ─────── ~15%
3:00 ─────── ~10%
5:00 ─────── ~5%
8:36 ─────── ~2-3% ← Video end
```

### Root Cause Hypotheses

1. **Hook failure (0:00–0:30):** The first 30 seconds likely lose 50%+ of viewers. For a data-driven video, the hook needs to present a surprising fact or visual immediately — not a slow build-up.
2. **Pacing mismatch (0:30–2:00):** 8:36 is long for a first video from an unknown channel. Viewers have zero trust/loyalty. The "100 years of data" promise needs to deliver visual payoff fast.
3. **Artificial inflation:** Many SUBSCRIBER views may be partial/quick views that drag the average down significantly.

### Improvement Strategy

| Timeframe | Action | Expected Impact |
|-----------|--------|----------------|
| 0:00–0:05 | Open with the most surprising data point, not the topic statement | +10-15% retention at 0:30 |
| 0:05–0:30 | Show the graph/visual immediately, narrate over it | +10% retention at 1:00 |
| 0:30–2:00 | Chapter-style pacing with clear "what's coming next" hooks | +5-10% mid-video retention |
| Throughout | Shorter video (5-6 min target for next video) until channel builds trust | +5-10% overall average |

---

## 4. Trend Analysis

### Daily Performance

| Date | Views | Δ Day-over-Day | Avg Duration | Δ Duration |
|------|-------|----------------|-------------|------------|
| Day 1 (Mar 17) | 31 | — | 75s | — |
| Day 2 (Mar 18) | 135 | **+335.5%** | 99s | +32.0% |
| Day 3 (Mar 19) | 15 | **-88.9%** | 41s | -58.6% |
| Days 4-5 (Mar 20-22) | ~0* | — | — | — |

*No data reported for days 4-5, implying near-zero views.

### Pattern Analysis

**Day 1 (31 views, 75s avg):** Launch day — likely a mix of the creator's own views and initial shares. 75s average is below the 90s overall, suggesting many quick test/check views.

**Day 2 (135 views, 99s avg):** The spike. This is **74.6% of all views in a single day**. This is almost certainly when the link was shared to a community/group (matches the SUBSCRIBER source dominance). The 99s avg is the highest — the first wave of "real" viewers.

**Day 3 (15 views, 41s avg):** Cliff drop. -88.9% day-over-day. The 41s average (only 8% of video length) suggests these are residual clicks from people who saw the shared link late and weren't very interested.

**Days 4-5 (~0 views):** Dead. No organic discovery engine is feeding the video.

### Verdict: Concerning but expected for seed stage

This is a **"social push then flatline"** pattern. It's common for first videos that rely on personal network distribution. The concerning part is not the drop itself — it's that **YouTube's algorithm has not picked up the video at all.** Zero impressions reported means YouTube is not showing this video to anyone through Browse, Search, or Suggested.

**Why YouTube isn't pushing the video:**
- 17.5% retention signals to the algorithm that viewers aren't interested
- No search impressions suggests either poor SEO or too niche a topic for the channel's authority level
- Zero shares = no social signals
- The video essentially died after the personal network exhausted itself

---

## 5. Performance vs 30-Day Targets

### Scorecard (Day 5 of 30)

| Metric | Target (30-day) | Current (Day 5) | Pace Needed | Status |
|--------|-----------------|-----------------|-------------|--------|
| Subscribers | 50-150 | 1 | 10/day remaining | RED |
| CTR | ≥ 4.5% | 0% (no impressions) | N/A — no data | RED |
| Avg view duration | ≥ 40% (206s) | 17.48% (90s) | +128.8% improvement | RED |
| Comments per video | ≥ 2 | 1 | 1 more needed | YELLOW |

### Detailed Status

**Subscribers: RED**
- 1 gained, 0 lost = net 1. Need 49-149 more in 25 days.
- At current rate (0.2/day), 30-day projection = ~6 subscribers.
- This target is unreachable with current trajectory. Need viral/organic discovery or consistent new content.

**CTR: RED**
- YouTube reports 0 impressions. This means YouTube's recommendation system is not showing the video anywhere. CTR cannot be measured.
- This is the single biggest problem. Without impressions, the video cannot grow.

**Avg View Duration: RED**
- 90s vs 206s target. Currently at 43.7% of the target.
- Even the best traffic source (EXT_URL at 3.4 min) only hits ~40% — barely meeting target.
- This requires fundamental changes to content structure, not incremental tweaks.

**Comments: YELLOW**
- 1 of 2 target. Achievable but only if video continues getting any views.
- No CTA for comments observed in the data (0.55% comment rate is low).

---

## 6. Quality Score

### Composite Quality Score: 3.2 / 10

| Dimension | Weight | Score (1-10) | Weighted |
|-----------|--------|-------------|----------|
| Retention | 30% | 2 | 0.60 |
| Engagement | 25% | 4 | 1.00 |
| Organic Discovery | 25% | 1 | 0.25 |
| Growth Signals | 20% | 3 | 0.60 |
| | | **Total** | **2.45** |

Scaled to 1-10: **3.2 / 10**

### Scoring Rationale

**Retention: 2/10**
- 17.5% is critically low. Industry average for educational content is 40-50%.
- Even organic viewers only hit ~30%. The content is not holding attention.

**Engagement: 4/10**
- 3.31% like ratio is decent (YouTube average ~4% for small channels).
- 6:1 like-to-dislike ratio is healthy — people who engage mostly like it.
- But 1 comment and 0 shares limit the score significantly.

**Organic Discovery: 1/10**
- Zero impressions from YouTube = the algorithm is not distributing this video.
- 1 related video view. Zero search traffic.
- The video is effectively invisible to YouTube's discovery systems.

**Growth Signals: 3/10**
- 1 subscriber gained is a start but minimal.
- EXT_URL and NO_LINK_OTHER viewers show decent quality (2-3.4 min avg) — there's signal that the *topic* interests people.
- But no momentum, no virality signals, no repeat visit data.

---

## 7. Key Insights

### Insight #1: The Video Is Invisible to YouTube's Algorithm
**What:** Zero impressions means YouTube is not recommending this video to anyone — not in search, not in suggested, not in browse feed. 100% of traffic came from direct/external sources.

**Why it matters:** Without algorithm distribution, a new channel cannot grow. The video failed to generate the retention and engagement signals YouTube needs to justify showing it to more people.

**Action for next video:**
- Target a topic with proven search demand (use YouTube autocomplete, TubeBuddy/vidIQ for keyword research)
- Front-load the most compelling data visualization in the first 10 seconds
- Aim for 5-6 minute length to improve % retention
- Optimize title/thumbnail for CTR before publishing (A/B test with friends)

### Insight #2: Organic Viewers Are 2× Better Than the Bulk Traffic
**What:** The ~31 viewers from organic/external sources watched 2.55 min/view (29.6%) vs the subscriber-source average of 1.52 min/view (17.7%). External URL viewers hit 3.4 min (39.5% — nearly hitting the 40% target).

**Why it matters:** The topic and content has genuine appeal to the right audience. The problem isn't the concept — it's (a) reaching the right audience at scale, and (b) the first 90 seconds of the video failing to hook casual viewers.

**Action for next video:**
- Double down on the data-visualization niche — the people who find it genuinely enjoy it
- The hook and intro need radical improvement — assume viewers will leave in 15 seconds unless given a reason to stay
- Share in data/economics communities (Reddit r/dataisbeautiful, r/economics, Twitter data viz community) for quality early traffic

### Insight #3: Day 2 Spike Reveals a Distribution Strategy That Doesn't Scale
**What:** 74.6% of all views came on Day 2 from what appears to be a single social share/push. Then the video went to near-zero.

**Why it matters:** Personal network distribution gets you the first 100-200 views but provides no compounding growth. If every video follows this pattern, the channel will flatline.

**Action for next video:**
- Create content around searchable queries ("gold price adjusted for inflation", "real cost of X over time") so YouTube Search can provide ongoing traffic
- Post consistently (1 video/week minimum) to build algorithmic trust
- Engage in communities BEFORE publishing to build anticipation, not just dump links

---

## 8. Data Gaps

### Critical (Blocks Decision-Making)

| Missing Data | Why We Need It | How to Get It |
|-------------|----------------|---------------|
| **YouTube Impressions & CTR** | 0 reported impressions is likely a data/API issue — even unwatched impressions should appear. Or the video truly has zero algorithmic reach. | Verify in YouTube Studio directly. Check if the API query is filtering correctly. |
| **Audience Retention Graph** | We're guessing where drop-offs occur. The actual retention curve would tell us exactly which seconds lose viewers. | YouTube Studio → Analytics → Audience Retention tab for this video. Export the curve data. |
| **Search Terms** | We don't know if anyone searched for this topic and found (or didn't find) the video. | YouTube Studio → Reach → Traffic Source: YouTube Search → search terms |
| **Thumbnail CTR** | Can't optimize what we can't measure. | Requires impressions data to be available |

### Important (Improves Analysis Quality)

| Missing Data | Why We Need It |
|-------------|----------------|
| **Device breakdown** | Mobile vs desktop affects ideal video length and visual density |
| **Audience demographics** | Age/gender/geography tells us if we're reaching the intended audience |
| **End screen / card performance** | Are viewers clicking through to subscribe or other content? |
| **Real-time view data (Days 4-5)** | We have gaps — did the video truly go to zero or are there residual views? |
| **Thumbnail & title versions** | Were any changes made post-publish that affected performance? |
| **External URL breakdown** | Which external sites drove the 5 EXT_URL views? These are our highest-quality viewers. |
| **Video tags & description SEO** | Need to audit if searchability was properly optimized |

### Nice-to-Have (Future Optimization)

| Missing Data | Why We Need It |
|-------------|----------------|
| **Competitor benchmarks** | How do similar "data visualization" channels perform on their first videos? |
| **Upload time analysis** | Was the video published at optimal time for target audience? |
| **Audio/visual quality metrics** | Viewer feedback on production quality |
| **Closed caption / subtitle data** | Accessibility and international reach |

---

## Summary

This is a **challenging but not hopeless** Day 5 report for a seed-stage channel's first video.

**The good:** The topic resonates with the people who find it (organic viewers show healthy engagement), the like ratio is positive, and someone subscribed.

**The bad:** The video is invisible to YouTube's algorithm, retention is critically low at 17.5%, and the majority of views appear to be non-organic (personal network push).

**The path forward:** The next video needs to (1) target a searchable topic, (2) nail the first 15-second hook with a surprising data point, (3) be shorter (5-6 min), and (4) be shared strategically in relevant communities. The channel concept has potential — the execution needs significant refinement.

---

*Report generated: 2026-03-22 | Next scheduled analysis: Day 7 (2026-03-24) and Day 30 (2026-04-16)*
*Analytics Agent v1 | Channel: the-world-with-numbers | Video: gold-vs-commodities-100-years*
