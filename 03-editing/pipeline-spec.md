# Editing Pipeline Spec

Automatically transform raw 1-hour recordings into polished, upload-ready YouTube videos.

## Pipeline

```
raw MP4 → silence removal → chapter detection → caption generation → intro/outro → final export
```

### Stage 1: Silence & Dead Air Removal
- FFmpeg `silencedetect` filter to find segments below threshold
- Remove silences longer than 2 seconds, keeping 0.5s padding on each side
- Output: trimmed MP4 + cut list (timestamps of what was removed)

### Stage 2: Chapter Detection
- Whisper transcription on trimmed video
- Claude analyzes transcript for logical chapter boundaries
- Generate YouTube-compatible timestamps (must start at 0:00)
- Output: chapter list as JSON + YouTube description format

### Stage 3: Caption Generation
- OpenAI Whisper (or whisper.cpp) for word-level timestamps
- Output: SRT and VTT subtitle files
- Optional: burn captions into video

### Stage 4: Intro/Outro Injection
- Prepend branded intro (5-10 seconds)
- Append outro with subscribe CTA + end screen placeholder (15-20 seconds)
- FFmpeg concat demuxer for lossless joining
- Templates stored in `03-editing/assets/`

### Stage 5: Final Export
- Codec: H.264 (libx264), High profile
- Audio: AAC 320kbps
- Resolution: 1920x1080
- Bitrate: 8-12 Mbps VBR
- Container: MP4 with faststart
- Output: final MP4 + SRT + chapters JSON, ready for publishing

## Configuration

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

## Tools

- **FFmpeg**: silence detection, trimming, concat, encoding
- **Whisper**: transcription and captions
- **Claude API**: chapter boundary detection
- **Python**: orchestration
