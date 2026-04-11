# 03 — Editing

## Goal
Automatically transform raw 1-hour recordings into polished, upload-ready YouTube videos with no manual editing required.

## Current Status
Documented — pipeline spec defined, no automation built yet

## Strategy & Research

### Editing Philosophy

- "Editing is not the hero — your story is. The purpose of editing is to support your message, not distract from it." — Film Booth
- For tutorials: focus on pacing, not flashiness. The goal is clarity and momentum.
- Every edit should either remove friction (dead air, mistakes) or add engagement (visual variety, emphasis).
- **Edit for narrative arc, not just clarity.** The finished video should feel like an episode with tension → struggle → resolution. Structure: cold open with the most dramatic moment (the breakthrough or the failure), then flashback to the start, build through the messy middle, and land on the resolution.
- **Preserve authentic moments** — don't cut frustration, surprise, or genuine reactions. These are the emotional beats that make viewers feel something. Only cut dead air and true tangents.

### Retention-Optimized Editing Checklist

These techniques directly impact the algorithm's key metric — Average View Duration:

- **Jump cuts:** Remove all pauses between sentences to tighten pacing. This is the single highest-impact edit for tutorial content.
- **B-roll breaths:** Insert 3-5 second visual breaks every 60-90 seconds during explanation-heavy sections. For screen recording: switch to webcam, show a diagram, or display a key stat.
- **Speed ramping:** Accelerate mundane footage 2-4x (installing packages, waiting for loads), return to normal for key moments.
- **Visual change every 15-25 seconds:** Angle, zoom, cutaway, text overlay. Videos maintaining 50%+ average view duration are 3x more likely to receive recommendations.
- **Sound design:** Subtle SFX on transitions, ambient layers, dynamic music enhance flow and reduce fatigue. Whoosh sounds on cuts, pop sounds on text reveals.
- **The Ken Burns Zoom:** Slow 10-15% scale increase over 8-10 seconds keeps static shots feeling dynamic.
- **The Text Punch:** 2-4 bold words synced with key stats or takeaways.

### CTA Placement Rules

| Timing | CTA Type | Example |
|--------|----------|---------|
| **0-60 sec** | Light/preview | "Stay until the end for X" |
| **30-70% mark** | Contextual (after delivering value) | "If that tip was helpful, hit like" |
| **Last 15-20 sec** | Strong primary | "Click the link," "Watch next video" |

Mid-roll CTAs get more clicks than end-roll since not everyone finishes. Place CTAs right after solving a pain point — viewers are most receptive when they just got value.

### Running Threads & Episode Continuity

The edit should reinforce that each video is part of a larger story:

- **Cold open hook** — Pull the most dramatic moment forward (the "oh no" or "yes!!" moment) before rewinding to the start
- **"Previously on..." recap** — Brief text overlay or voiceover referencing the last episode (5-10 seconds max)
- **Callbacks** — When something connects to a past episode, add a brief text overlay or picture-in-picture referencing it (e.g., "Day 5: this same thing broke")
- **Next episode tease** — Before the end screen, drop a hint about what's coming: "Next time, I'm tackling [X]..." This creates an open loop.
- **Progress indicators** — Occasional text overlays showing pipeline progress ("Editing: automated. Thumbnails: still manual.") to remind viewers of the larger journey

### End Screen & Playlist Strategy

- Start end screen sequence **20-30 seconds** before video ends
- Link to relevant next video, subscribe button, and/or playlist
- Optimized end screens increase channel watch time by up to 34%
- Average session time rises from 9:12 to 14:05 with optimized end screens
- Use **Series Playlists** for "Day X" videos — tells the algorithm they should be watched in order
- Strategic playlists extend session watch time, which is one of the top algorithm signals

## System Spec

### Pipeline Overview
Raw MP4 from `02-recording/` goes through these stages in order:

```
raw MP4 → silence removal → chapter detection → caption generation → intro/outro injection → final export
```

### Stage 1: Silence & Dead Air Removal
- Use FFmpeg's `silencedetect` filter to find segments with audio below a threshold
- Remove silences longer than 2 seconds, keeping 0.5s of padding on each side
- Configurable thresholds: silence dB level (-30dB default), minimum silence duration
- Output: trimmed MP4 with a cut list (timestamps of what was removed)

### Stage 2: Chapter Detection
- Run Whisper transcription on the trimmed video
- Use Claude to analyze the transcript and identify logical chapter boundaries
- Generate YouTube-compatible chapter timestamps (must start at 0:00)
- Output: chapter list as JSON and YouTube description format

### Stage 3: Caption Generation
- Use OpenAI Whisper (or whisper.cpp for speed) to generate word-level timestamps
- Output SRT and VTT subtitle files
- Optionally burn captions into video (configurable — YouTube has its own caption support)

### Stage 4: Intro/Outro Injection
- Prepend a branded intro clip (5-10 seconds)
- Append an outro with subscribe CTA and end screen placeholder (15-20 seconds)
- Use FFmpeg concat demuxer for lossless joining
- Intro/outro templates stored in `03-editing/assets/`

### Stage 5: Final Export
- Re-encode to YouTube-optimal settings:
  - Codec: H.264 (libx264), High profile
  - Audio: AAC 320kbps
  - Resolution: 1920x1080
  - Bitrate: 8-12 Mbps VBR
  - Container: MP4 with faststart
- Output: final MP4 + SRT + chapters JSON, ready for `06-publishing/`

### Configuration
All thresholds and settings will be configurable via a `config.yaml` in this folder:
```yaml
silence:
  threshold_db: -30
  min_duration_s: 2.0
  padding_s: 0.5

export:
  resolution: "1920x1080"
  video_bitrate: "8M"
  audio_bitrate: "320k"
  codec: "libx264"
  preset: "slow"

captions:
  model: "large-v2"
  language: "en"
  burn_in: false

intro_clip: "assets/intro.mp4"
outro_clip: "assets/outro.mp4"
```

## Tools/APIs Needed
- **FFmpeg**: silence detection, trimming, concat, final encoding
- **Whisper** (openai-whisper or whisper.cpp): transcription and captions
- **Claude API**: chapter boundary detection from transcript
- **Python**: orchestration script tying the pipeline together
- **PyYAML**: config file parsing

## Scripts
_None yet. Planned:_
- `edit.py` — main orchestration script
- `silence.py` — silence detection and removal
- `chapters.py` — transcript-based chapter generation
- `captions.py` — subtitle generation
- `export.py` — final encoding and packaging
