# 05 — Thumbnail Generation

## Goal
Automatically generate click-worthy YouTube thumbnails for each video using AI image generation and templating.

## Current Status
Not started

## System Spec
- Extract a representative frame from the video (high-energy moment, clear face)
- Use a template system: background frame + bold text overlay + branding elements
- Generate title text options optimized for thumbnail readability (short, punchy, large font)
- Produce 2-3 thumbnail variants for A/B testing
- Output at YouTube's recommended 1280x720 resolution

## Tools/APIs Needed
- FFmpeg (frame extraction)
- Pillow or ImageMagick (text overlay, compositing)
- Optionally: AI image generation for background enhancement
- Claude API (title text generation)

## Scripts
_None yet._
