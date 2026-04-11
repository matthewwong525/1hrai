# YouTube OS — 1HR AI

Matt records 1 hour teaching people how to use AI to grow their business. Everything else is automated. Building in public — each video covers the pipeline itself.

## Daily Context

Before starting any work, read today's daily file from the **main branch** (not the worktree):

```
/Users/matthewwong/Documents/1hrai/daily/<YYYY-MM-DD>.md
```

Use today's date to construct the path. This file contains Matt's goals and notes for the session. If no file exists, proceed without it.

## The Process

Each session follows this order:

1. **Headline + Thumbnail** — Run `/changes {day}` to generate both in parallel. The title and thumbnail complement each other (never repeat). Start here because if you can't make a clickable title and thumbnail, the idea isn't viable.
2. **Talking Points** — `/changes` generates 5-10 bullet points Matt can riff on. These are beats, not a script.
3. **Record + Build** — Matt goes through the talking points on camera (~1 hour). At the same time, he improves the repo and pipeline, creating material for the next video.

## Creative Direction

Every video is an **episode in an ongoing journey**, not a standalone tutorial. Inspired by LockedInPoker's bankroll challenge — viewers come back to see what happens next.

1. **Journey arc** — each video is a chapter. "Day X" is episode progression.
2. **Real stakes** — show failures, setbacks, the messy middle. When something breaks, that's the content.
3. **Tension/resolution** — every piece of content has a problem, a struggle, a payoff.
4. **Think out loud** — show the decision process, not the polished result.
5. **Raw over polished** — rough but real beats polished and fake.

When generating titles, thumbnails, hooks, or any viewer-facing content, filter through these principles. The question isn't "is this educational?" — it's "does this feel like the next episode?"

## Repository Map

| Folder | What's Inside |
|--------|--------------|
| `00-overview/` | Channel strategy reference files — philosophy, algorithm, monetization, first 90 days, legal |
| `01-ideation/` | Video topic backlog and session plans _(future automation)_ |
| `02-recording/` | Pre-recording checklist, file naming conventions, Matt's headshot |
| `03-editing/` | Editing pipeline technical spec — silence removal, chapters, captions, export |
| `04-clips/` | Shorts and clip extraction _(future automation)_ |
| `05-thumbnails/` | Detailed thumbnail research — psychology, composition, color theory, A/B testing (used by `/thumbnail` and `/changes`) |
| `06-publishing/` | YouTube upload, SEO, metadata _(future automation)_ |
| `07-analytics/` | Performance tracking and feedback loop _(future automation)_ |
| `08-growth/` | Cross-platform distribution _(future automation)_ |
| `youtube-channel-guide.md` | Comprehensive reference — algorithm, strategy, scripting, thumbnails, SEO, monetization, analytics, growth. Read for deep context on any topic. |

## How to Answer Questions

1. Check the repository map to find the relevant folder
2. Read the files inside that folder before answering
3. For deep research or cross-cutting questions, read `youtube-channel-guide.md`
4. Never answer from memory alone when project-specific context exists in a file

## Conventions

- Each pipeline stage has its own numbered folder
- Scripts and automation code go inside the relevant stage folder
- Raw media files are NOT stored in this repo
- When learning something new from Matt, update the relevant file (not CLAUDE.md)
