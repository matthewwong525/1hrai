# 04 — Clip Extraction

## Goal
Automatically extract short-form clips (60-90 seconds) from the full video for use as YouTube Shorts, social media teasers, or a summary reel.

## Current Status
Documented — Shorts strategy defined, no automation built yet

## Strategy & Research

### How the Shorts Algorithm Works

The Shorts algorithm is **completely separate** from long-form (decoupled since late 2025). It operates on an "Explore & Exploit" model:

- **Explore Phase:** Every Short is tested against a small seed audience
- **Exploit Phase:** If the seed responds well, pushed to progressively larger audiences
- **No CTR tracking** — autoplay is default; swipe-through rate replaces CTR

### Shorts Ranking Signals (by importance)

1. **Completion Rate** — Below 50% = struggle; 70% = competitive baseline; 80%+ = significant boost
2. **Viewed vs. Swiped Ratio** — Target 75%+; below 50% = weak hook
3. **Loop/Replay Rate** — Each loop counts as a separate view (since March 2025)
4. **Engagement** — Shares carry particularly strong weight for viral potential
5. **Niche Alignment** — Clear AI/business niche improves recommendation matching

### Shorts Best Practices for AI Education

- **Optimal length:** 15-60 seconds (despite the 3-minute allowance). Shorter = higher completion rate.
- **Hook in first 1-3 seconds** or viewers swipe. Open with the result, a bold claim, or a visual transformation.
- **Pattern interrupts every 2-3 seconds** — zooms, cuts, text overlays. Shorts attention spans are brutal.
- **Never repost with TikTok/Instagram watermarks** — immediately downranked by YouTube.
- **Burned-in captions are mandatory** — short-form viewers expect them and many watch without sound.
- **Post 3-7 Shorts per week** for best algorithmic performance.

**Content types that work for AI education Shorts:**
- "Did you know [AI tool] can do this?" — 15-second reveal
- Before/after transformations (manual vs. AI-assisted)
- "One tip that saves 3 hours" — focused single-insight clips
- Quick tool walkthroughs at 2x speed with captions
- Controversial takes or surprising AI outputs

### Jenny Hoyos's Shorts Formula Applied to AI Clips

- Write the hook and closing line first, then fill in the middle
- Target 90%+ retention on every Short
- Use "But/Then" storytelling: "I asked Claude to write my emails... but then it did something unexpected"
- Close on maximum emotion — viewers judge based on how they feel at the end
- Power words for hooks: "free," "secret," "banned," "one prompt," "replaced"

### Shorts as Growth Funnel

- Creators posting both Shorts and long-form grow subscribers **3x faster**
- Total watch time increases 2.5x in the first year for dual-format creators
- Shorts RPM is lower (45% creator share vs. 55% for long-form) — use Shorts for exposure, long-form for depth and revenue
- End each Short with context that drives to the full video: "Full tutorial on my channel" or pin a comment linking to the long-form version
- Use Shorts to tease upcoming long-form content: "Tomorrow I'm showing the full automation — subscribe so you don't miss it"

## System Spec
- Analyze the transcript (from `03-editing/`) to find the most engaging or insightful segments
- Use Claude to score segments by "shareability" — clear insight, self-contained point, high energy
- Extract top 3-5 clips per video
- Re-frame to 9:16 vertical for Shorts (crop or zoom on speaker)
- Add captions burned in (short-form viewers expect them)

## Tools/APIs Needed
- FFmpeg (clip extraction, re-framing, caption burn-in)
- Whisper transcript (from `03-editing/`)
- Claude API (segment scoring and selection)

## Scripts
_None yet._
