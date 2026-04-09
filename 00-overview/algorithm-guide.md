# How YouTube's Algorithm Works (2025-2026)

YouTube's algorithm is a personalized recommendation engine answering one question: **"Will this specific viewer enjoy this specific video right now?"** It drives 70% of all platform watch time through recommendations.

## Five Separate Recommendation Systems

| System | How It Works | Average CTR |
|--------|-------------|-------------|
| **Home Feed** | Personalized by watch history clustering + video performance | 3.5-4.5% |
| **Suggested Videos** | Based on current video topic + viewer history | ~9.5% |
| **YouTube Search** | Relevance + engagement + individual signals | ~12.5% |
| **Subscriptions** | Mostly chronological with some ranking | Varies |
| **Shorts Feed** | Completely separate system (Explore & Exploit model) | N/A (autoplay) |

## The 4-Layer Impression Distribution System

When you upload, YouTube tests through concentric audience circles:

1. **Core Audience:** Subscribers and regular viewers (first test)
2. **Recent Viewers:** People who watched your content recently
3. **Topic Matches:** Related-content viewers who don't know your channel
4. **Adjacent Audiences:** Viewers of related (but not identical) topics — this is where viral potential lives

**Critical window:** The first 24-48 hours are decisive. Videos achieving above-average CTR and retention in their first ~1,000 impressions receive 5-10x more distribution.

## What the Algorithm Measures (2025 Weighting)

| Signal | Weight | Change from 2023 |
|--------|--------|-------------------|
| **Viewer Satisfaction** | **35%** | Up from 15% |
| **Average View Duration** | 25% | Down from 35% |
| **Click-Through Rate** | 20% | Down from 35% |
| **Return Sessions** | 15% | Up from 10% |

**Satisfaction is now king.** YouTube measures it through:
- Post-view surveys ("Did you enjoy this video?")
- Sentiment modeling from comments
- Whether viewers continue watching after your video
- "Not Interested" and "Don't Recommend" signals
- Return viewers within 7-30 days

## The "Quality CTR" Concept

YouTube evaluates what happens in the 30 seconds after a click:
- A 10% CTR with 80% of viewers leaving in 30 seconds is **worse** than a 5% CTR where viewers watch 60% of the video
- When retention drops below 40%, YouTube deprioritizes the video regardless of CTR
- **Bottom line:** CTR gets your foot in the door; retention keeps you in the room; satisfaction keeps you coming back

## What This Means for 1HR AI

- The automated editing pipeline (`03-editing/`) directly impacts retention — tight cuts and silence removal matter
- Thumbnails and titles (`05-thumbnails/`, `06-publishing/`) drive CTR, but misleading packaging gets penalized
- Analytics feedback (`07-analytics/`) should track satisfaction signals (return viewers, comment sentiment), not just views
- The "Day X" series format encourages return sessions — one of the rising algorithm signals
