# 04 — Clip Extraction

## Goal
Automatically extract short-form clips (60-90 seconds) from the full video for use as YouTube Shorts, social media teasers, or a summary reel.

## Current Status
Not started

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
