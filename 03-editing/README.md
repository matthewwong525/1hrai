# 03 — Editing

## Goal
Automatically transform raw 1-hour recordings into polished, upload-ready YouTube videos with no manual editing required.

## Current Status
Documented — pipeline spec defined, no automation built yet

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
