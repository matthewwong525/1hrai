# 07 — Analytics

## Goal
Track video performance and feed insights back into the ideation pipeline to continuously improve content.

## Current Status
Documented — metrics framework and feedback loops defined, no automation built yet

## Strategy & Research

### Metrics by Channel Stage

Matt is currently at 0-1K subscribers. The focus metrics change as the channel grows:

| Stage | Focus Metrics |
|-------|---------------|
| **0-1K subs (current)** | Average View Duration, retention curves, CTR (aim for 4-6%) |
| **1K-10K subs** | Subscriber growth rate (target 3-8%/month), watch time, returning viewers |
| **10K+ subs** | RPM, audience demographics/geography, traffic sources, new vs. returning ratio |

**At 0-1K, ignore vanity metrics (total views, subscriber count).** Focus entirely on whether people who click actually watch, and whether the retention graph tells you what's working.

### Key Benchmarks

**CTR by Channel Size:**

| Size | Average CTR |
|------|-------------|
| Under 1K subs | 6-10% |
| 1K-10K subs | 5-8% |
| 10K-100K subs | 4-6% |
| 100K+ subs | 3-5% |

**Audience Retention by Video Length:**

| Length | Healthy Retention |
|--------|-------------------|
| Under 2 min | 50-70% |
| 5-10 min | 50%+ |
| 15-30 min | 30-45% |
| 30+ min | 25-35% |

**Engagement:**
- Like-to-view ratio: 2%+ healthy, 4%+ strong
- Return viewer rate above 10% = sustainable growth
- Improving retention by 10 percentage points correlates with 25% more impressions

### Weekly Analytics Review Habit

Every week, review these three numbers and plan adjustments:

1. **CTR** — Are thumbnails and titles working? If below 4%, the packaging needs work (see `05-thumbnails/`, `06-publishing/`).
2. **Retention at 30 seconds** — Is the hook landing? If below 70%, rework the opening structure (see `02-recording/`).
3. **Returning viewer count** — Are people coming back? This is YouTube's strongest satisfaction signal.

Also review:
- Retention graph drop-off points — identify exactly where viewers leave, then stop doing those things
- Which topics got the best retention — double down on those in `01-ideation/`
- Traffic sources — is growth coming from search (good for early channels) or browse (algorithm is pushing you)?

### The Analytics Feedback Loop

The analytics stage isn't just reporting — it's the engine that improves every other stage:

| Analytics Insight | Feeds Into | Action |
|-------------------|-----------|--------|
| Top-performing topics | `01-ideation/` | Prioritize similar topics, create sequels |
| Retention drop-off points | `02-recording/` | Adjust recording structure, improve hooks |
| Pacing issues (drops during explanation) | `03-editing/` | Add more visual changes, tighten cuts |
| Low completion rate on Shorts | `04-clips/` | Shorter clips, stronger hooks, faster pacing |
| CTR below benchmarks | `05-thumbnails/` | Test new thumbnail styles, A/B test more |
| Low impressions despite good retention | `06-publishing/` | Improve titles, descriptions, SEO |
| Best posting times (actual data) | `06-publishing/` | Adjust upload schedule |
| Subscriber sources | `08-growth/` | Double down on best-performing platforms |

## System Spec
- Pull video performance data from YouTube Analytics API (views, watch time, CTR, retention curves)
- Track metrics over time: which topics perform best, optimal video length, best posting times
- Generate weekly summary reports
- Identify drop-off points in retention curves to improve editing
- Feed top-performing topic categories back into `01-ideation/` for topic scoring

## Tools/APIs Needed
- YouTube Analytics API
- Google OAuth2 (authentication)
- Claude API (insight generation and report writing)
- SQLite or JSON files for historical data storage

## Scripts
_None yet._
