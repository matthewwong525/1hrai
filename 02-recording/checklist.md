# Recording Checklist & Conventions

## Pre-Recording Checklist

1. **Topic ready**: Session plan reviewed — topic, talking points, demo outline
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
4. **Notes visible**: Keep talking points on a second monitor or printed out
5. **Water + timer**: Stay hydrated, keep a clock visible

## Recording Principles

- **Don't cut when things break** — errors and confusion are the content
- **Narrate your thinking** — "I'm trying X because Y..." pulls viewers into the process
- **Reference the journey** — briefly mention last session and what's at stake today
- **Hook in first 30 seconds** — show the result, bold claim, or stakes up front
- **Stop while energy is high** — never signal the video is ending

## File Conventions

- **Naming**: `YYYY-MM-DD_topic-slug.mkv` (e.g., `2026-04-08_ai-email-marketing.mkv`)
- **Location**: Raw files go to a local `raw/` directory (not in repo)
- **Post-record**: Remux MKV to MP4 via `ffmpeg -i input.mkv -c copy output.mp4`
- **Metadata sidecar**: `.json` file with same name:
  ```json
  {
    "date": "2026-04-08",
    "topic": "AI Email Marketing",
    "slug": "ai-email-marketing",
    "duration_minutes": 58,
    "notes": "Covered Mailchimp AI features and Claude for copywriting"
  }
  ```

## How Recording Feeds Into Next Stages

- `03-editing/` picks up the MP4 + metadata JSON from `raw/`
- `04-clips/` uses the same source to extract short-form clips
- `05-thumbnails/` uses the topic and a representative frame for thumbnail generation
