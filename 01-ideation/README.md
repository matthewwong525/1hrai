# 01 — Ideation & Session Planning

## Goal
Automatically generate and prioritize video topics, maintain a content calendar, and produce a session plan for each recording.

## Current Status
Documented — strategy and research complete, no automation built yet

## Strategy & Research

### Hero-Hub-Help Framework for 1HR AI

| Type | Purpose | Frequency | 1HR AI Examples |
|------|---------|-----------|-----------------|
| **Help** | Answer questions, solve problems | Weekly (highest volume) | "How to use Claude for email marketing," "ChatGPT vs Claude for small business" |
| **Hub** | Build deeper engagement | Monthly | Full workflow builds, "Day X" deep dives, step-by-step automation guides |
| **Hero** | Go viral, reach new audiences | Quarterly | "I automated my entire YouTube channel with AI," ultimate guides, collabs |

**Recommended ratio:** 1 Hero : 3 Hub : 12+ Help pieces

### Evergreen vs. Trending Balance

**Target: 70-80% evergreen / 20-30% trending**

- Evergreen builds a stable foundation of compounding search traffic (e.g., "How to use AI for small business marketing")
- Trending provides bursts of rapid growth (e.g., "New Claude feature just dropped — here's what it means for your business")
- For AI niche: lean closer to 70/30 since AI tools change fast — more trending content stays relevant
- Monitor AI tool launches (OpenAI, Anthropic, Google) for reactive content opportunities

### Video Length Strategy

Matt records 1 hour raw. The editing pipeline should target these outputs:

| Output | Length | Purpose |
|--------|--------|---------|
| Hub video (main) | 15-30 min | In-depth tutorial, highest monetization (mid-roll ads at 8+ min) |
| Help video (focused) | 7-10 min | Single topic, search-optimized |
| YouTube Shorts | 15-60 sec | Hooks and highlights, growth funnel |

**Cardinal rule:** Never pad a video to hit a time target. Make it exactly as long as it needs to be.

### Ideation Process for AI Education

1. **Mine comments** — What do viewers keep asking? What confused them?
2. **Monitor AI launches** — New features from OpenAI, Anthropic, Google, Midjourney = instant content opportunities
3. **Study outlier videos** — Search AI tutorial topics, filter by "Last Month," find small channels with outsized views
4. **Keyword gap analysis** — Use vidIQ/TubeBuddy to find topics with search demand (1K-100K/month) but weak existing content
5. **Cross-platform mining** — Reddit (r/artificial, r/smallbusiness), Twitter/X, LinkedIn for unanswered questions
6. **Revisit best performers** — Can you update, expand, or sequel your top videos?
7. **Pipeline meta-content** — Building the YouTube OS itself is content: "How I automated my editing with AI"

### Session Planning: Hooks + Structure

**Plan the hook before recording.** 10 proven hook types for AI tutorials:

1. **Big Reveal** — Show the AI output/result first, then explain how
2. **Problem Statement** — "Most small businesses waste 10 hours/week on X. Here's how AI fixes that."
3. **Curiosity Question** — "Can Claude actually replace a $5K marketing agency?"
4. **Shocking Stat** — "This AI tool saved me 40 hours last month"
5. **Before/After** — Show the manual process, then the automated version
6. **Pattern Interrupt** — 3-5 rapid cuts in first 12 seconds showing different outputs

**Story structure for tool tutorials:** Use the Dan Harmon circle (see `02-recording/README.md`). Present the problem, demo the solution, show the transformation.

### Content Calendar

- **Target cadence:** 1 long-form/week + 3-5 Shorts/week
- **Build a 2-4 video buffer** to prevent burnout and missed uploads
- **Leave 1-2 flex slots per month** for trending/reactive content (AI tool launches)
- **Batch film** when possible — record 2-3 sessions back-to-back with different topics
- **Pipeline:** Idea -> Session Plan -> Record -> Edit -> Thumbnail -> Publish -> Analyze -> feed back to Idea

## System Spec
- Pull trending AI topics from news, Twitter/X, Reddit, and YouTube search trends
- Cross-reference with channel analytics (what's performing well)
- Maintain a ranked backlog of video ideas with estimated audience interest
- Before each session, generate a session plan: topic, key talking points, demo outline, and screen share prep
- Feed analytics data back into topic scoring

## Tools/APIs Needed
- YouTube Data API (trending, search suggest)
- Twitter/X API or scraper for AI topic trends
- Reddit API (r/artificial, r/smallbusiness, etc.)
- LLM (Claude) for topic synthesis and session plan generation

## Scripts
_None yet._
