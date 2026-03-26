# Video Critique — Gold vs Commodities: 100 Years of Prices in Gold Terms
**Date:** 2026-03-17
**Reviewed:** Test frames (faz2/faz3 era), video-config.json, script-v2.md, audio file list, render output (faz4 — 213.7MB)
**Overall Grade:** B+

## Executive Summary
This is a solid first video with a genuinely interesting concept and clean data visualization. The chart is the star — readable, well-synced to voiceover, and the 100-year horse race format works beautifully. However, the non-chart scenes (hook, CTA) feel underdeveloped compared to the chart quality, and some polish items hold it back from an A. Would I watch the whole thing? Yes. Would I subscribe? Not yet — needs one more pass.

## Strengths
1. **Chart quality is excellent** — Log scale, floating labels, color differentiation, year watermark. This is genuinely better than most YouTube data visualization charts. The 1971→1980 crash visual is dramatic and compelling.
2. **Voiceover-to-chart sync** — The SceneYearRange system works. When the narrator says "1971", the chart is at 1971. This is a non-trivial achievement.
3. **Scoreboard design** — Clean, ranked, color-coded. The animated bars with green/red distinction communicate instantly. Professional look.
4. **Data integrity** — 175K data points, verified Nikkei calculation, all ratios checked. The content is trustworthy.
5. **Asset Parade scene** — Formula breakdown with real examples ($42,800 ÷ Gold $2,990 = 14.31 oz) is pedagogically excellent.

## Issues Found

### 🔴 Critical (must fix before publish)

1. **Background music — untested in final render**
   - The bg music was just added in Faz 4. Volume is set to 0.12 (12%). Nobody has listened to how it actually sounds in the final video. Is the loop seamless? Does the music style match the content tone? Does the volume balance with the Australian baritone voiceover?
   - **Fix:** Watch the full 6:16 video with audio. Verify loop transition point (~3-4 min mark) isn't jarring. Adjust volume if needed.

2. **Music copyright status unknown**
   - File is `moodmode-no-copyright-music-201745.mp3`. The name suggests "no copyright" but the actual license terms haven't been verified. If this gets a Content ID match, the channel gets a strike on its very first video.
   - **Fix:** Verify the exact license. Check if attribution is required. Test with YouTube's copyright check tool before publishing.

### 🟡 Important (strongly recommended)

3. **Hook scene is too minimal**
   - Just "26,000%" in green on cream background for 5 seconds. No motion, no context, no visual hook. First impression for YouTube viewers is a static number on a blank screen. YouTube retention data shows the first 3 seconds are make-or-break.
   - **Fix:** Add subtle animation — scale pulse, particle effect, or at minimum a supporting subtitle visible from frame 1 (e.g., "The Dow Jones since 1925"). The viewer needs context immediately.

4. **CTA scene feels bare**
   - "Nominal returns are an illusion." + channel name + tiny subscribe button. 10 seconds of near-blank screen. This is wasted screen time at the most important moment (end screen overlay zone).
   - **Fix:** Add end screen elements area (subscribe + next video placeholder). Consider showing a teaser for the next video or a key stat recap.

5. **No thumbnail strategy**
   - No thumbnail has been designed. The video's click-through rate is 80% determined by the thumbnail. This should not be an afterthought.
   - **Fix:** Design a thumbnail before publishing. Suggestion: Split screen — "26,000%" crossed out on one side, "132%" in gold on the other, with "PRICED IN GOLD" text.

6. **Scoreboard doesn't use series-specific colors**
   - The scoreboard uses generic green/red for positive/negative. But each asset has a carefully chosen color in the chart (e.g., Nikkei = `#DC2626`, S&P = `#D63384`). The scoreboard should use these colors for brand consistency — viewers just spent 5 minutes learning to associate colors with assets.
   - **Fix:** Update scoreboard items to use each asset's chart color for the bar fill, not generic green/red.

7. **DAX bar shows as negative (red) but the bar extends right**
   - In the scoreboard, DAX at -29.0% has a small red bar extending to the right. Negative values should extend left from the zero line, or the bar should be absent. Current visual is misleading.
   - **Fix:** Implement proper negative bar rendering (bars going left) or use a different visual for losers (e.g., no bar, just the percentage).

### 🟢 Nice to Have (polish items)

8. **Year watermark could be larger or more prominent during key moments**
   - The big year watermark (e.g., "1989") in the chart background is nice but subtle. During peak drama moments (1980 crash, 1989 Nikkei peak), it could briefly pulse or change opacity to draw attention.
   - **Fix:** Add a subtle scale animation on the year text at scene transition points.

9. **No channel branding in chart scenes**
   - During the 4+ minutes of horse-race chart, there's no channel name or watermark visible. If someone screenshots or shares a frame, there's no attribution.
   - **Fix:** Add a small, semi-transparent "The World With Numbers" watermark in the bottom-right corner during chart scenes.

10. **FDR annotation badge style**
    - The "FDR: GOLD $20.67 → $35" annotation is a solid purple rectangle that feels stylistically disconnected from the cream/editorial theme. It looks like a debugging label.
    - **Fix:** Restyle annotations to match the editorial theme — cream background with gold border, or a more subtle banner style.

11. **Test frames are from mixed Faz versions**
    - The test-renders directory has 64 frames from faz1, faz2, faz2b, faz2c, faz2d, faz3, and bgm-test. This is confusing. No dedicated Faz 4 test frames exist.
    - **Fix:** Generate a clean set of Faz 4 test frames at key moments. Consider cleaning up old test frames.

12. **Video file size is large (213.7 MB for 6:16)**
    - That's ~568 kbps, which is reasonable for 1080p30 but worth checking if YouTube re-encodes well. Consider if a 2-pass encode would reduce size without quality loss.
    - **Fix:** Low priority — YouTube handles re-encoding. But worth noting for future videos.

## Scene-by-Scene Notes
| Scene | Verdict | Notes |
|-------|---------|-------|
| hook | ⚠️ | Too minimal. Static green number on blank screen. Needs animation or context text from frame 1. |
| setup (parade) | ✅ | Formula + asset-by-asset breakdown works well. Good pacing for 44s. Dot indicators are nice. |
| goldStdEra | ✅ | Chart reads well. FDR annotation present. Only 4 series visible (Dow, Nikkei, S&P, Silver) — clean. |
| nixonShock | ✅ | The dramatic crash is visually compelling. All 9 lines visible. Good density. |
| greatRev | ✅ | Nikkei peak at 73.95 visible. Good label placement. No overlap issues. |
| goldsRev | ✅ | Modern era reads clearly. Dow/Nikkei/FTSE clustering at top is distinguishable. |
| scoreboard | ⚠️ | Clean layout but uses generic green/red instead of asset-specific colors. Negative bar direction incorrect. |
| cta | ⚠️ | Too bare. Wasted end-screen real estate. Subscribe button is too small/subtle. |

## Final Verdict
**Not ready to publish as-is.** Minimum to ship:
1. ✅ Verify background music sounds good in actual playback (listen to full video)
2. ✅ Confirm music copyright/license
3. ⚠️ Consider hook improvement (even a small animation helps)
4. 📋 Design a thumbnail

The chart — which is 70% of the video — is genuinely good. The issues are in the bookend scenes and pre-publish checklist items. One more focused session could get this to publish-ready.
