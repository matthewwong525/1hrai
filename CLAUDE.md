# YouTube OS — 1HR AI

Matt spends 1 hour recording himself teaching people how to use AI to grow their business. Everything else is automated. Building in public — each video covers the pipeline itself.

## Daily Context

Before starting any work, read today's daily file from the **main branch** (not the worktree):

```
/Users/matthewwong/Documents/1hrai/daily/<YYYY-MM-DD>.md
```

Use today's date to construct the path (e.g. `2025-04-11.md`). This file contains Matt's goals, priorities, and notes for the session. If the file doesn't exist yet, proceed without it.

## How to Answer Questions

1. Identify which pipeline stage(s) the question relates to using the routing table below
2. Read the relevant README(s) before answering — they contain strategy research, system specs, and project decisions
3. For cross-cutting questions (algorithm, monetization, storytelling), check `youtube-channel-guide.md`
4. Never answer from memory alone when stage-specific context exists in a README

## Routing Table

| Topic | Read first |
|-------|-----------|
| Channel strategy, audience, positioning, branding | `00-overview/README.md` + reference files in `00-overview/` |
| Video topics, session planning, content calendar | `01-ideation/README.md` |
| Recording setup, OBS, checklist | `02-recording/README.md` |
| Editing pipeline, silence removal, chapters, captions | `03-editing/README.md` |
| Shorts, clips, vertical video | `04-clips/README.md` |
| Thumbnails, CTR, design | `05-thumbnails/README.md` |
| Publishing, titles, SEO, descriptions, tags | `06-publishing/README.md` |
| Analytics, metrics, retention, reporting | `07-analytics/README.md` |
| Growth, cross-posting, distribution, community | `08-growth/README.md` |
| YouTube algorithm, monetization, scripting, storytelling | `youtube-channel-guide.md` |
| End-to-end workflow | All stage READMEs |

## Pipeline Stages

| Stage | Folder | Status |
|-------|--------|--------|
| Channel Strategy | [00-overview/](00-overview/README.md) | Documented |
| Ideation | [01-ideation/](01-ideation/README.md) | Documented |
| Recording | [02-recording/](02-recording/README.md) | Documented |
| Editing | [03-editing/](03-editing/README.md) | Documented |
| Clips | [04-clips/](04-clips/README.md) | Documented |
| Thumbnails | [05-thumbnails/](05-thumbnails/README.md) | Prompt Generator Built |
| Publishing | [06-publishing/](06-publishing/README.md) | Documented |
| Analytics | [07-analytics/](07-analytics/README.md) | Documented |
| Growth | [08-growth/](08-growth/README.md) | Documented |

## Project Conventions

- Each pipeline stage lives in its own numbered folder
- Each folder has a `README.md` with: Goal, Current Status, Strategy & Research, System Spec, Tools/APIs, Scripts
- Scripts and automation code go inside the relevant stage folder
- Raw media files are NOT stored in this repo

## Keeping Knowledge Current

- When you learn something new from Matt, update the relevant stage README (not this file)
- Keep stage statuses in the table above in sync with actual project state
- Strategy & Research sections in READMEs are the source of truth for each stage's context
