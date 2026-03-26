# TTS Provider Comparison: ElevenLabs vs Gemini TTS vs Google Cloud TTS

> date: 2026-03-21
> purpose: Pipeline infrastructure decision — choose optimal TTS provider
> context: YouTube channel "The World With Numbers", ~10 min English narration videos, ~9,000 chars/video

---

## 1. Executive Summary & Recommendation

**For our use case (YouTube narration, 4 videos/month, ~36,000 chars/month):**

| Criterion | Winner |
|-----------|--------|
| Audio Quality (narration) | **Gemini 2.5 Pro TTS** / **ElevenLabs** (close) |
| Cost Efficiency | **Google Cloud TTS (Chirp 3: HD)** — effectively free |
| Control & Flexibility | **Gemini TTS** (natural language prompts for style) |
| Ease of Integration | **ElevenLabs** (simplest API, already integrated) |
| Voice Cloning | **ElevenLabs** (only provider with this feature) |
| Best Value Overall | **Gemini 2.5 Flash TTS** or **Chirp 3: HD** |

**Bottom line:** At our volume (36K chars/month), **Google Cloud Chirp 3: HD voices are completely free** (1M free chars/month). Gemini 2.5 Flash TTS is also extremely cheap (~$0.15/video). ElevenLabs costs $5-22/month for this usage. Quality-wise, Gemini TTS and ElevenLabs are now comparable — Gemini TTS has the unique advantage of natural-language style prompting ("say this in a curious, authoritative way").

**Recommendation:** Test Gemini 2.5 Flash TTS and Chirp 3: HD with our actual scripts. If quality matches ElevenLabs, switch — the cost savings are significant and the style control via prompts is a powerful feature for narration.

---

## 2. Pricing Comparison

### 2.1 ElevenLabs

[Source: elevenlabs.io/pricing](https://elevenlabs.io/pricing)

ElevenLabs uses a **credit-based system**. For Multilingual v2 (our current model): 1 character = 1 credit.

| Plan | Price/mo | Credits | ~Minutes (Multilingual v2) | Extra Minute Cost |
|------|----------|---------|----------------------------|-------------------|
| Free | $0 | 10,000 | ~10 min | N/A |
| Starter | $5 | 30,000 | ~30 min | N/A |
| Creator | $22 | 100,000 | ~100 min | ~$0.30/min |
| Pro | $99 | 500,000 | ~500 min | ~$0.24/min |
| Scale | $330 | 2,000,000 | ~2,000 min | ~$0.18/min |

**Flash model** (lower quality, faster): costs ~0.5 credits/char, so roughly 2x the minutes for the same credits.

**Our usage calculation (Multilingual v2):**
- 1 video: ~9,000 characters = 9,000 credits ≈ 10 min audio
- 4 videos/month: ~36,000 characters = 36,000 credits
- **Free tier**: 10,000 credits → covers ~1.1 videos ❌
- **Starter ($5/mo)**: 30,000 credits → covers ~3.3 videos ❌ (barely short)
- **Creator ($22/mo)**: 100,000 credits → covers ~11 videos ✅
- **Effective cost per video on Starter**: ~$1.50/video (if within quota)
- **Effective cost per video on Creator**: ~$2.00/video

**Hidden costs:** None beyond subscription. Commercial license included in Starter+.

### 2.2 Google Cloud TTS (Chirp 3: HD, WaveNet, Neural2, Studio)

[Source: cloud.google.com/text-to-speech/pricing](https://cloud.google.com/text-to-speech/pricing)

| Voice Type | Free Tier | Price per 1M chars | Price per char |
|------------|-----------|---------------------|----------------|
| **Chirp 3: HD** | 1,000,000 chars/mo | $30 | $0.00003 |
| Instant Custom Voice | None | $60 | $0.00006 |
| WaveNet | 4,000,000 chars/mo | $4 | $0.000004 |
| Neural2 | 1,000,000 chars/mo | $16 | $0.000016 |
| Studio | 1,000,000 chars/mo | $160 | $0.00016 |
| Standard | 4,000,000 chars/mo | $4 | $0.000004 |

**Our usage calculation (Chirp 3: HD — recommended):**
- 1 video: 9,000 chars × $0.00003 = **$0.27** (but free tier covers it)
- 4 videos/month: 36,000 chars → **$0.00** (well within 1M free chars)
- 12 videos/month (3/week target): 108,000 chars → **$0.00** (still free)
- Breakeven to paid: ~111 videos/month before exceeding free tier

**Hidden costs:**
- Requires a GCP project with billing enabled (no charge unless free tier exceeded)
- No minimum commitment
- SSML tags count as characters (except `<mark>`)

### 2.3 Gemini TTS (via Cloud TTS API or Vertex AI)

[Source: cloud.google.com/text-to-speech/pricing](https://cloud.google.com/text-to-speech/pricing)

Gemini TTS is priced differently — by **tokens**, not characters.

| Model | Input Price (per 1M text tokens) | Output Price (per 1M audio tokens*) | Free Tier |
|-------|----------------------------------|--------------------------------------|-----------|
| **Gemini 2.5 Flash TTS** | $0.50 | $10.00 | Not listed |
| Gemini 2.5 Flash Lite TTS (Preview) | $0.50 | $10.00 | Not listed |
| **Gemini 2.5 Pro TTS** | $1.00 | $20.00 | Not listed |

*Audio tokens: 25 tokens per second of audio

**Our usage calculation (Gemini 2.5 Flash TTS):**
- 1 video: ~9,000 chars ≈ ~2,250 text tokens (rough: 4 chars/token)
  - Input cost: 2,250 / 1,000,000 × $0.50 = **$0.001**
  - Output: ~600 seconds × 25 tokens/sec = 15,000 audio tokens
  - Output cost: 15,000 / 1,000,000 × $10.00 = **$0.15**
  - **Total per video: ~$0.15**
- 4 videos/month: **~$0.60**
- 12 videos/month: **~$1.80**

**For Gemini 2.5 Pro TTS:**
- Per video: ~$0.30 (2× Flash)
- 4 videos/month: **~$1.20**
- 12 videos/month: **~$3.60**

**Hidden costs:** Requires GCP project with billing. No explicit free tier listed for Gemini TTS models.

### 2.4 Pricing Summary Table

| | ElevenLabs (Starter) | ElevenLabs (Creator) | Chirp 3: HD | Gemini 2.5 Flash TTS | Gemini 2.5 Pro TTS |
|---|---|---|---|---|---|
| **Monthly fixed cost** | $5 | $22 | $0 | $0 | $0 |
| **Cost per video (9K chars)** | ~$1.50* | ~$2.00* | **$0 (free tier)** | ~$0.15 | ~$0.30 |
| **4 videos/month** | **$5** | **$22** | **$0** | **$0.60** | **$1.20** |
| **12 videos/month** | ❌ Exceeds Starter | **$22** | **$0** | **$1.80** | **$3.60** |
| **Annual cost (12 vid/mo)** | N/A | **$264** | **$0** | **$21.60** | **$43.20** |

*ElevenLabs: subscription cost amortized across videos, not per-character overage

---

## 3. Gemini API TTS — Voice Catalog & Capabilities

[Source: cloud.google.com/text-to-speech/docs/gemini-tts](https://cloud.google.com/text-to-speech/docs/gemini-tts)

### 3.1 Available Models

| Model | ID | Best For | Multi-Speaker |
|-------|-----|----------|---------------|
| Flash TTS | `gemini-2.5-flash-tts` | Low-latency, cost-efficient | Yes |
| Flash Lite TTS | `gemini-2.5-flash-lite-preview-tts` | Ultra-cheap, single speaker | No (single only) |
| Pro TTS | `gemini-2.5-pro-tts` | Highest quality, structured workflows | Yes |

### 3.2 Voice Catalog — 30 Voices

Gemini TTS offers **30 distinct voices** (same voice names as Chirp 3: HD):

#### Female Voices (14)
| Name | Character |
|------|-----------|
| Achernar | — |
| Aoede | — |
| Autonoe | — |
| Callirrhoe | — |
| Despina | — |
| Erinome | — |
| Gacrux | — |
| Kore | — |
| Laomedeia | — |
| Leda | — |
| Pulcherrima | — |
| Sulafat | — |
| Vindemiatrix | — |
| Zephyr | — |

#### Male Voices (16)
| Name | Character |
|------|-----------|
| Achird | — |
| Algenib | — |
| Algieba | — |
| Alnilam | — |
| Charon | — |
| Enceladus | — |
| Fenrir | — |
| Iapetus | — |
| Orus | — |
| Puck | — |
| Rasalgethi | — |
| Sadachbia | — |
| Sadaltager | — |
| Schedar | — |
| Umbriel | — |
| Zubenelgenubi | — |

> **Note:** Google does not publish detailed voice characteristic descriptions (warm, authoritative, etc.). You need to listen to demos at the [Vertex AI Studio](https://console.cloud.google.com/vertex-ai/studio/media/generate;tab=audio) or [Colab notebook](https://colab.research.google.com/github/GoogleCloudPlatform/generative-ai/blob/main/audio/speech/getting-started/get_started_with_gemini_tts_voices.ipynb).

### 3.3 Voice Selection

- Voice is selected by **name** (e.g., `"Kore"`, `"Charon"`)
- For Chirp 3: HD, full format is needed: `"en-US-Chirp3-HD-Kore"`
- For Gemini TTS, just the short name: `"Kore"`
- Language specified separately via `language_code`

### 3.4 Style Control — The Killer Feature

**Gemini TTS uses natural-language prompts** to control style. This is fundamentally different from ElevenLabs' stability/similarity sliders.

```
prompt: "Say the following in a calm, authoritative documentary narrator voice"
text: "In 2024, the global population reached 8.1 billion..."
speaker: "Charon"
```

You can control:
- Tone (curious, authoritative, solemn, excited)
- Pace (extremely fast, slowly)
- Accent
- Emotional expression
- Whisper, emphasis
- Speaking style (news anchor, storytelling, casual)

**This is very relevant for our channel** — we could prompt "neutral, data-focused documentary narrator" and get consistent output.

### 3.5 SSML Support

- **Gemini TTS**: Does NOT support SSML. Uses natural-language prompts instead.
- **Chirp 3: HD**: Supports SSML in **Preview** (batch/synchronous only, not streaming). Supported tags: `<speak>`, `<say-as>`, `<p>`, `<s>`, `<phoneme>`, `<sub>`, `<break>`, `<audio>`, `<prosody>`, `<voice>`.
- **WaveNet/Neural2/Studio**: Full SSML support (GA).

### 3.6 Speed/Pitch Control

- **Gemini TTS**: Via natural-language prompt (e.g., `"[extremely fast]"` or `"say slowly"`)
- **Chirp 3: HD**: `speaking_rate` parameter: 0.25x to 2.0x
- No pitch parameter for Chirp 3: HD
- WaveNet/Neural2: Full `<prosody>` SSML control (rate, pitch, volume)

### 3.7 Break/Pause Control

- **Gemini TTS**: Use punctuation (ellipses, hyphens) or disfluencies in the text. No `<break>` tag.
- **Chirp 3: HD**: `[pause short]`, `[pause long]`, `[pause]` tags in the `markup` input field. Also SSML `<break>` in preview.
- **WaveNet/Neural2/Studio**: Full `<break time="0.5s" />` support.

### 3.8 API Endpoint & Key Parameters

**Cloud TTS API (recommended for our use case):**
```
POST https://texttospeech.googleapis.com/v1/text:synthesize

{
  "input": {
    "prompt": "Say the following in a neutral, authoritative narrator voice",
    "text": "The global population reached 8.1 billion in 2024..."
  },
  "voice": {
    "languageCode": "en-us",
    "name": "Charon",
    "model_name": "gemini-2.5-flash-tts"
  },
  "audioConfig": {
    "audioEncoding": "MP3"
  }
}
```

**Vertex AI API:**
```
POST https://aiplatform.googleapis.com/v1beta1/projects/{PROJECT}/locations/{REGION}/publishers/google/models/gemini-2.5-flash-tts:generateContent

{
  "contents": {
    "role": "user",
    "parts": { "text": "Say the following in a neutral narrator voice: ..." }
  },
  "generation_config": {
    "speech_config": {
      "language_code": "en-us",
      "voice_config": {
        "prebuilt_voice_config": { "voice_name": "Charon" }
      }
    }
  }
}
```

### 3.9 Input Limits

| | Gemini TTS | Chirp 3: HD | ElevenLabs |
|---|---|---|---|
| **Max input per request** | 8,000 bytes (text + prompt) | No explicit limit listed (uses standard TTS limits) | ~5,000 chars (varies by plan) |
| **Max output audio** | ~655 seconds (~11 min) | N/A | No hard limit (via long-form) |
| **Text field max** | 4,000 bytes | — | — |
| **Prompt field max** | 4,000 bytes | — | — |

⚠️ **IMPORTANT**: 655 seconds ≈ 11 minutes is tight for our 10-min videos. We may need to split longer scripts into two requests.

---

## 4. Feature Comparison Table

| Feature | ElevenLabs (v2) | Gemini TTS (Flash/Pro) | Google Cloud TTS (Chirp 3: HD) |
|---------|-----------------|------------------------|-------------------------------|
| **Audio Quality** | Excellent — industry leader | Excellent — comparable to ElevenLabs | Very Good — step below Gemini TTS |
| **Output Formats** | MP3, WAV, PCM, OGG Opus, μ-law, A-law (27 format options) | LINEAR16, ALAW, MULAW, MP3, OGG_OPUS, PCM | LINEAR16, ALAW, MULAW, MP3, OGG_OPUS, PCM |
| **Max Sample Rate** | 48kHz (PCM), 44.1kHz (MP3/WAV) | 24kHz default | 24kHz |
| **Bit Rate Options** | 32/64/96/128/192 kbps MP3 | N/A (codec-dependent) | N/A |
| **SSML Support** | None (uses voice settings) | None (uses NL prompts) | Preview (batch only) |
| **Speed Control** | 0.25x-4.0x (via `speed` param) | Via NL prompt + `[extremely fast]` tags | 0.25x-2.0x (`speaking_rate`) |
| **Pitch Control** | No | No | No (Chirp 3). Yes (WaveNet/Neural2 via SSML) |
| **Pause/Break Control** | Via `<break>` in text (limited) | Via NL, punctuation, disfluencies | `[pause short/long]` in markup field |
| **Style Control** | Stability, Similarity, Style sliders (0-1) | **Natural language prompts** (unique!) | None |
| **Voice Cloning** | Yes (Instant + Professional) | No | Instant Custom Voice ($60/1M chars) |
| **Streaming** | Yes | Yes (bidirectional) | Yes (bidirectional) |
| **Multi-Speaker** | No (one voice per request) | Yes (Flash & Pro) | Yes (Studio multispeaker) |
| **Latency (500 chars)** | ~1-3 seconds | ~2-5 seconds ⚠️ UNVERIFIED | ~1-3 seconds |
| **Rate Limits** | Plan-dependent | GCP quota-based | GCP quota-based |
| **Max Text/Request** | ~5,000 chars | 4,000 bytes text + 4,000 bytes prompt | Long Audio Synthesis available |
| **Language Support** | 32 languages | 24 GA + 50+ Preview | 40+ languages, 220+ voices |
| **Emotion/Prosody** | Via Stability/Style sliders | Via NL prompts (very flexible) | Limited |
| **Request Stitching** | Yes (`previous_request_ids`) | Not documented | Not documented |
| **Pronunciation Dict** | Yes | Custom pronunciations (IPA/X-SAMPA) | Custom pronunciations (IPA/X-SAMPA) |
| **Seed for Reproducibility** | Yes (`seed` param) | Via `temperature` param (Vertex AI) | No |
| **Commercial License** | Starter+ plans | Yes (GCP ToS) | Yes (GCP ToS) |

---

## 5. Quality Notes & Community Sentiment

### 5.1 ElevenLabs
- **Reputation:** Industry gold standard for AI TTS. Consistently ranked #1 in blind listening tests.
- **Strengths:** Most natural prosody, excellent emotional range, great for narration.
- **Weaknesses:** Occasional "glitches" (artifacts, mispronunciations). Stability slider can cause inconsistency between generations. No SSML — you're somewhat at the mercy of the AI's interpretation.
- **Our experience:** Using Maisie voice with Multilingual v2. WPM measured at 151. Had to switch from Daniel due to monotone issues. Style=0.20, Stability=0.35 for expressiveness.
- **For YouTube narration:** Excellent. Used by many YouTubers.

### 5.2 Gemini TTS
- **Reputation:** New entrant (2025-2026), rapidly improving. Google's latest generative TTS.
- **Strengths:** Natural-language style prompting is a game-changer. Multi-speaker support. Good for long-form content. Temperature control for variety.
- **Weaknesses:** Relatively new — less community battle-testing. 655-second output limit could be an issue. No SSML support. Pricing is token-based (less predictable for exact budgeting).
- **For YouTube narration:** Very promising. The prompt-based style control ("calm, documentary narrator") is ideal for consistent channel voice.
- **Key differentiator:** You can literally describe the speaking style you want in English. This is more intuitive than ElevenLabs' numeric sliders.

### 5.3 Google Cloud TTS (Chirp 3: HD)
- **Reputation:** Solid, reliable, widely used in production. Chirp 3: HD is a major upgrade from WaveNet.
- **Strengths:** Generous free tier (1M chars/month). 30 voices across many languages. SSML support (preview). Pace and pause control. Well-documented API. Very stable.
- **Weaknesses:** Less "natural" than ElevenLabs or Gemini TTS. More robotic feel in some voices. No NL prompt control.
- **For YouTube narration:** Good enough for many channels. May lack the warmth and dynamism of ElevenLabs for documentary-style content.

### 5.4 Known Gotchas

| Provider | Gotcha |
|----------|--------|
| ElevenLabs | Regenerating same text can produce different results (non-deterministic). Use `seed` param to mitigate. |
| ElevenLabs | Credit counting includes spaces and punctuation. A 9,000-char script uses exactly 9,000 credits. |
| Gemini TTS | Output capped at ~655 seconds. Must split scripts >11 min. |
| Gemini TTS | `aiplatform.endpoints.predict` permission required — not just standard TTS permissions. |
| Gemini TTS | Vertex AI output is raw PCM 16-bit 24kHz without WAV headers — you need to handle conversion. Cloud TTS API supports MP3 directly. |
| Chirp 3: HD | Does NOT support SSML input by default. SSML is in Preview for batch only. |
| Chirp 3: HD | No `<prosody pitch>` — can't adjust pitch. |
| Google Cloud | Must enable billing on GCP project even for free tier. |
| All Google | SSML tags (except `<mark>`) count toward character billing. |

---

## 6. Integration Considerations for yt-pipeline

### Current Setup
- Provider: ElevenLabs
- Voice: Maisie (`QtY3JBOUKEB5xzrRfOKc`)
- Model: `eleven_multilingual_v2`
- Script: `src/scripts/tts-generate.ts`
- Config: `channels/the-world-with-numbers/channel-config.json` → `tts` section

### Migration Path to Gemini TTS
1. **Add `@google-cloud/text-to-speech` package** (or use REST API directly)
2. **Update `tts` config** to support multiple providers
3. **Handle the 655-second limit** — split long scripts at paragraph boundaries
4. **Style prompt** — add a `tts.stylePrompt` field to channel config, e.g., `"Neutral, calm, authoritative documentary narrator. Clear diction, measured pace."`
5. **Audio conversion** — if using Vertex AI API, convert raw PCM to WAV/MP3
6. **Recalibrate WPM** — Gemini TTS may have different speaking speed than ElevenLabs

### Recommended Config Addition
```json
{
  "tts": {
    "provider": "google-gemini-tts",
    "model": "gemini-2.5-flash-tts",
    "voiceName": "Charon",
    "languageCode": "en-US",
    "stylePrompt": "Neutral, calm, authoritative documentary narrator. Clear enunciation, measured pace, no excitement, let the data speak.",
    "outputFormat": "MP3",
    "fallbackProvider": "elevenlabs"
  }
}
```

---

## 7. Action Items

1. **[ ] A/B Test** — Generate the same 60-second script segment with ElevenLabs (Maisie) and Gemini TTS (Charon + narration prompt). Blind-test the results.
2. **[ ] Test Multiple Gemini Voices** — Try Charon, Enceladus, Fenrir, Orus for documentary narration style.
3. **[ ] Test Chirp 3: HD** — As a free fallback, test if quality is sufficient.
4. **[ ] Measure Latency** — Time API response for 9,000-char input on each provider.
5. **[ ] Test 655-sec Limit** — Confirm whether our typical scripts exceed this limit.
6. **[ ] Prototype Integration** — Write a minimal `tts-generate-google.ts` script.

---

## Sources

1. [ElevenLabs Pricing](https://elevenlabs.io/pricing) — Accessed 2026-03-21
2. [Google Cloud TTS Pricing](https://cloud.google.com/text-to-speech/pricing) — Accessed 2026-03-21
3. [Gemini-TTS Documentation](https://cloud.google.com/text-to-speech/docs/gemini-tts) — Accessed 2026-03-21
4. [Chirp 3: HD Documentation](https://cloud.google.com/text-to-speech/docs/chirp3-hd) — Accessed 2026-03-21
5. [Google Cloud TTS Supported Voices](https://cloud.google.com/text-to-speech/docs/voices) — Accessed 2026-03-21
6. [ElevenLabs API Reference](https://elevenlabs.io/docs/api-reference/text-to-speech/convert) — Accessed 2026-03-21
7. [ElevenLabs FAQ: Credits & Characters](https://elevenlabs.io/pricing#faqs) — Accessed 2026-03-21
