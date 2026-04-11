Analyze repo changes and produce everything needed for the next video: the best headline, a thumbnail prompt, and a video script. The argument is the day number (e.g., `/changes 5`).

## Steps

1. **Extract the day number** from `$ARGUMENTS`. If missing, ask for it before proceeding.

2. **Gather context** — run these in parallel to build a full picture:
   - `git log --oneline --all --since="1 week ago"` for recent commits (expand timeframe if sparse — 2 weeks, 1 month — until you have meaningful content)
   - `git log --all --stat` for a fuller view of what files changed
   - `git diff main@{1.week.ago}..main` (or appropriate range) for actual code changes
   - Read CLAUDE.md and key files to understand project structure
   - Check for open PRs with `gh pr list`

3. **Distill the core story** — before launching agents, identify:
   - The single most impressive or visual thing built
   - The viewer benefit ("why should I care?")
   - The emotional hook (curiosity, surprise, achievement)
   - What would look good on screen (demos, before/after, UI changes)

4. **Launch Agent 1 (Headline) and Agent 2 (Thumbnail) in parallel:**

   ### Agent 1 — Headline
   Give this agent the full context from steps 2-3 and the headline skill instructions from `.claude/skills/headline/SKILL.md`. The agent should follow that skill's process (Steps 2-4) to generate and select the best title.

   All titles must follow the format: `Day X, [headline], IN ONE HOUR`

   ### Agent 2 — Thumbnail Prompt
   Give this agent the full context from steps 2-3, the thumbnail research from `05-thumbnails/README.md`, and these instructions:
   - Generate a detailed image generation prompt for nanobanana
   - The prompt MUST start with: "I'm attaching a picture of my face to use in this thumbnail."
   - **Style: Raw & authentic** (inspired by lockedinpoker) — the thumbnail should look like a real moment from Matt's life, NOT a polished graphic. Think raw vlog screenshot with bold text slapped on top. Real setting (desk, laptop, room), selfie/phone camera quality, casual framing.
   - Matt's face with a **genuine, raw expression** matching the honest emotion of the day — NOT a YouTube performance face. Think: staring at a screen in disbelief, laughing, frustrated focus, genuine surprise at a result.
   - **Simple layout**: Matt on one side, big bold text on the other or overlapping. Two elements max. No flowcharts, no icons, no decorative elements.
   - **1-3 words MAX** of bold thumbnail text — chunky sans-serif, white or bright with thick dark outline, slightly imperfect/tilted placement. A number, reaction word, or short hook (e.g., "1,000 SUBS?!", "IT WORKS", "$0", "WTF").
   - **Green** for growth/subscriber milestones, **white/yellow** for emphasis, **red** for urgency/setbacks — ONE accent color per thumbnail
   - Include "Day {number}" as main text or small episode label
   - Text creates a curiosity gap with the title (complements, never repeats)
   - Show real screens when relevant (laptop showing Claude Code, YouTube analytics, subscriber counts)
   - Keep bottom-right clear (YouTube duration overlay). 1280x720, readable at 168x94px mobile size.
   - This is chapter {day number} in the journey to 1,000 subscribers using AI.
   - Also output the thumbnail text overlay separately

5. **Launch Agent 3 (Talking Points)** — after Agents 1 and 2 are done, give this agent:
   - The chosen headline from Agent 1
   - The thumbnail concept from Agent 2
   - The full context from steps 2-3
   
   The agent produces 5-10 bullet points Matt can riff on while recording. Format:

   ---

   ### Talking Points: [Chosen Headline]

   - **[Bullet 1]** — one sentence on what to say + what to show on screen
   - **[Bullet 2]** — ...
   - ...5-10 bullets total

   ---

   **Talking points rules:**
   - 5-10 bullets, no more — Matt riffs naturally on camera, he just needs the beats
   - Each bullet is ONE key thing to mention, not a paragraph
   - Group by themes, not commits
   - Plain English, conversational — what Matt would actually say
   - Include a brief screen cue in each bullet (what to show)
   - First bullet should hook the viewer (connect to title/thumbnail promise)
   - Last bullet should be the "what's next" + CTA
   - Deliver on the promise made by the title + thumbnail

6. **Output everything together** in this format:

   ---

   ## Headline
   [The chosen title]

   ## Thumbnail
   **Prompt for nanobanana:**
   [The full image generation prompt]

   **Text overlay:** [The 3-5 words to place on the thumbnail]

   **Framework:** [Which thumbnail framework was used]

   ## Talking Points
   [The bullet points from Agent 3]

   ---
