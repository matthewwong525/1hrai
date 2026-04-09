# 06 — Publishing

## Goal
Automatically upload finished videos to YouTube with optimized metadata (title, description, tags, chapters, thumbnail, scheduling).

## Current Status
Documented — SEO and publishing strategy defined, no automation built yet

## Strategy & Research

### Title Best Practices for AI Education

- **Length:** Under 60-70 characters to avoid truncation
- **Keywords:** Front-load the primary keyword in the first 40 characters
- **"Day X" placement:** Include near the end so the keyword leads: "Automate Your Emails with Claude — Day 12" not "Day 12: Automate Your Emails with Claude"
- **Style:** Natural, compelling, clear value proposition. Avoid generic/hype headlines.
- **Avoid:** Misleading clickbait — the algorithm now penalizes high CTR + low retention ("Quality CTR")
- **Generate 30-50 title options** per video (Paddy Galloway's advice) — use Claude to brainstorm, then pick the best

**Title formulas that work for AI tutorials:**
- "How I [Result] Using [AI Tool]" — proof-based
- "[AI Tool] Can Do [Surprising Thing] — Here's How" — curiosity
- "Stop [Manual Process] — Use [AI Tool] Instead" — problem/solution
- "[Number] [AI Tool] Tricks That Save [Time/Money]" — listicle

### Description Optimization

- **First 125-157 characters are critical** — visible before "Show more" on desktop/mobile. Make them count.
- Include primary keyword in first 25 words
- **Optimal length:** 200-500 words
- Add timestamps/chapters with keyword-rich labels (appear as Google search snippets)
- Place 3-5 hashtags in description (max 15; exceeding causes YouTube to ignore all)
- Include links: related videos, playlists, affiliate links (with disclosure), social media
- **Template structure:**
  1. Compelling summary (125 chars)
  2. What you'll learn (bullet points)
  3. Chapters/timestamps
  4. Links and resources mentioned
  5. Affiliate disclosure
  6. Social links

### Tags Strategy

- Use 10-15 relevant tags (YouTube doesn't reward excess)
- Place most important keyword first
- Tags are secondary to titles/descriptions but reinforce topic context
- Include common misspellings and variations (e.g., "ChatGPT" and "Chat GPT")
- Mix broad ("AI tools") and specific ("Claude for email marketing")

### Captions as SEO

- YouTube **indexes caption text** for search ranking — this is a hidden goldmine
- A 10-minute video contains 1,300-1,500 searchable words
- Upload custom SRT files (from `03-editing/`) rather than relying on auto-generated — better accuracy, better SEO
- Multi-language captions expand reach to new audiences
- **Pro tip:** Rename video files with the primary keyword before uploading (e.g., "ai-email-marketing-tutorial-2026.mp4" not "video_final_v3.mp4")

### What YouTube Scans Beyond Metadata

YouTube's algorithm analyzes far more than title/description/tags:
- **Spoken words** (audio transcription) — say your keywords naturally in the video
- **Visual elements and text overlays** (computer vision) — on-screen text reinforces topic signals
- **Channel context and content consistency** — staying in the AI niche strengthens all videos
- **Viewer behavior patterns** — what viewers watch before and after your video

### Upload & Scheduling

- **Best posting time:** Tuesday-Thursday, 2:00-4:00 PM EST (captures North American afternoon + European evening)
- **Consistency matters more than optimal time** — pick a day and stick to it
- Channels with regular schedules see 67% faster subscriber growth
- Schedule uploads to go live at the same time each week so subscribers know when to expect new content

## System Spec
- Upload final MP4 from `03-editing/` via YouTube Data API
- Generate SEO-optimized title and description using Claude (based on transcript and topic)
- Auto-populate chapters in description from `03-editing/` chapter data
- Set tags based on topic, content pillars, and trending keywords
- Attach thumbnail from `05-thumbnails/`
- Upload captions (SRT) as closed captions
- Schedule publish time based on audience analytics (optimal posting windows)
- Set end screen and cards if API supports it

## Tools/APIs Needed
- YouTube Data API v3 (upload, metadata, captions, thumbnails)
- Google OAuth2 (authentication)
- Claude API (title/description generation)

## Scripts
_None yet._
