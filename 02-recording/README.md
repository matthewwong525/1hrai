# 02 — Recording

## Goal
This is the one manual step. Matthew records ~1 hour of content per session. This stage documents everything needed to make that hour as productive as possible and ensure the raw output feeds cleanly into the automated pipeline.

## Current Status
Documented — checklist and conventions defined, no automation yet

## System Spec

### Pre-Recording Checklist
1. **Topic ready**: Session plan pulled from `01-ideation/` — topic, talking points, demo outline reviewed
2. **Environment**:
   - Close unnecessary apps, silence notifications
   - Open demo tabs/apps needed for screen share
   - Check audio levels (mic gain, no background noise)
   - Check webcam framing and lighting
3. **OBS configured**:
   - Scene: webcam + screen capture layout
   - Recording format: MKV (remux to MP4 after)
   - Audio: separate tracks for mic and desktop audio
   - Resolution: 1920x1080, 30fps minimum
4. **Notes visible**: Keep session plan on a second monitor or printed out
5. **Water + timer**: Stay hydrated, keep a clock visible to pace the session

### File Output Conventions
- **Naming**: `YYYY-MM-DD_topic-slug.mkv` (e.g., `2026-04-08_ai-email-marketing.mkv`)
- **Location**: Raw files go to a local `raw/` directory (not in this repo, too large)
- **Post-record**: Remux MKV to MP4 via `ffmpeg -i input.mkv -c copy output.mp4`
- **Metadata sidecar**: A `.json` file with the same name containing:
  ```json
  {
    "date": "2026-04-08",
    "topic": "AI Email Marketing",
    "slug": "ai-email-marketing",
    "duration_minutes": 58,
    "session_plan": "01-ideation/plans/2026-04-08.md",
    "notes": "Covered Mailchimp AI features and Claude for copywriting"
  }
  ```

### How Recording Feeds into Next Stages
- `03-editing/` picks up the MP4 + metadata JSON from `raw/`
- `04-clips/` uses the same source to extract short-form clips
- `05-thumbnails/` uses the topic and a representative frame for thumbnail generation

### Future Automation Ideas
- Auto-start/stop recording via hotkey script
- Real-time audio level monitoring with alerts
- Auto-generate metadata JSON from session plan

## Tools/APIs Needed
- OBS Studio (recording)
- FFmpeg (remux MKV to MP4)

## Scripts
_None yet._
