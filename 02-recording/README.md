# 02 — Recording

## Goal
This is the one manual step. Matthew records ~1 hour of content per session. This stage documents everything needed to make that hour as productive as possible and ensure the raw output feeds cleanly into the automated pipeline.

## Current Status
Documented — checklist and conventions defined, no automation yet

## Strategy & Research

### Equipment Priorities for Screen-Recording-Heavy Format

**Audio > Lighting > Camera** — viewers tolerate bad video but abandon bad audio. 69% of focus group viewers said audio quality was "extremely important" for trustworthiness.

Since 1HR AI is primarily screen recording with webcam overlay:
- **Audio is #1 priority.** A USB mic (Shure MV7+ ~$249 or Blue Yeti ~$100) on the desk is ideal for stationary recording. DJI Mic 3 (~$200) with 32-bit float recording is impossible to clip.
- **Camera is secondary.** Webcam or phone in a mount works fine — the screen share is the star. If upgrading: Sony ZV-E10 II is the top dedicated pick.
- **Lighting matters for webcam.** Face a window for free, or use a single LED key light at 45 degrees (Elgato Key Light Air ~$130).

### Recording Technique for Retention

The raw recording directly determines the edited video's retention. Structure sessions for engagement:

**The 30-Second Blueprint (Hook):**

| Timeframe | Purpose | What To Do |
|-----------|---------|------------|
| 0:00-0:05 | Attention grab | Show the end result, bold claim, or surprising stat |
| 0:05-0:15 | Clarify the promise | What viewers will learn/gain from this session |
| 0:15-0:30 | Establish stakes | Why this matters for their business |

**Retention benchmarks:** Above 70% at 30 seconds = solid. Below 50% at 15 seconds = hook is failing.

**MrBeast's Structure Adapted for Tutorials:**
- **Minutes 0-1:** Front-load the result or key insight. Show what they'll be able to do.
- **Minutes 1-3:** Quick progression through setup/context. Don't dwell.
- **3-Minute Mark:** Re-engagement — show something unexpected or impressive.
- **Throughout:** Change what's on screen every 15-25 seconds (switch apps, zoom in, show output). Monotonous screen recordings kill retention.
- **Ending:** Stop while energy is high. Never say "well, that's about it" — retention craters when you signal the end.

**Pattern Interrupts During Recording:**
- Switch between screen share and webcam-only moments
- Zoom into specific UI elements when explaining details
- Use multiple browser tabs/apps to create visual variety
- Verbally tease upcoming sections: "Coming up, I'll show you the trick that saves 3 hours..."

**Story Structure for Tool Tutorials (Dan Harmon Circle):**
1. You: Introduce the viewer's current situation (manual process, wasted time)
2. Need: The problem pushing them to try something new
3. Go: Open the AI tool, start the demo
4. Search: Work through challenges, show real troubleshooting
5. Find: The breakthrough moment — it works
6. Take: Acknowledge the learning curve or cost
7. Return: Show the streamlined final workflow
8. Change: The payoff — before vs. after comparison

### Music & Sound Effects

| Source | Price | Notes |
|--------|-------|-------|
| YouTube Audio Library | Free | Start here. Pre-cleared for monetization. |
| Epidemic Sound | $10/month | 55K+ tracks. Most popular among established YouTubers. |
| Artlist | $10/month | Lifetime rights on downloads even after cancellation. |

Background music during tutorials should be subtle — lower volume, ambient/lo-fi. It fills silence without competing with explanation.

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
