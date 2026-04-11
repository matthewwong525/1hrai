---
name: changes
description: Analyze repo changes and produce everything needed for the next video - the best headline, a thumbnail prompt, and talking points. The argument is the day number (e.g., `/changes 5`).
---

# Changes

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

4. **Launch Agent 1 (Headline & Thumbnail) and Agent 2 (Talking Points) in parallel:**

   ### Agent 1 — Headline & Thumbnail
   Give this agent the full context from steps 2-3 and the headline-thumbnail skill instructions from `.claude/skills/headline-thumbnail/SKILL.md`. The agent should follow that skill's process to generate and select the best title and create the thumbnail prompt.

   All titles must follow the format: `Day X, [headline], IN ONE HOUR`

   ### Agent 2 — Talking Points
   Give this agent:
   - The full context from steps 2-3
   
   The agent produces 5-10 bullet points Matt can riff on while recording. Format:

   ---

   ### Talking Points: [Based on core story from step 3]

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

5. **Once both agents complete**, update talking points: take the chosen headline from Agent 1 and use it to refine the talking points header and ensure the first bullet hooks into the actual title.

6. **Output everything together** in this format:

   ---

   ## Headline
   [The chosen title]

   ## Thumbnail
   **Prompt for nanobanana:**
   [The full image generation prompt]

   **Text overlay:** [The 1-3 words to place on the thumbnail]

   **Framework:** [Which thumbnail framework was used]

   ## Talking Points
   [The bullet points]

   ---
