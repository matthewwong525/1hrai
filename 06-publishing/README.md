# 06 — Publishing

## Goal
Automatically upload finished videos to YouTube with optimized metadata (title, description, tags, chapters, thumbnail, scheduling).

## Current Status
Not started

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
