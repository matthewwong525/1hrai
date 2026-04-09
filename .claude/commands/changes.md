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
   Give this agent the full context from steps 2-3 and these instructions:
   - Generate 10-15 title candidates
   - Every title MUST include "Day {number}" (e.g., "Day 5")
   - All titles under 60 characters
   - Group candidates by style: Curiosity Gap, Bold Claim, Educational/How-To, Build-in-Public
   - Auto-select the single best title — the one with the strongest curiosity gap that accurately represents what was built
   - Output the chosen title and a one-line justification

   **Title rules:**
   - Under 60 characters (never truncated on any device)
   - Front-load the primary keyword in the first 40 characters
   - Natural language, compelling, clear value proposition
   - Never misleading — YouTube penalizes high CTR + low retention
   - The title should COMPLEMENT the thumbnail, never repeat it
   - Avoid generic/hype words ("INSANE", "CRAZY", "YOU WON'T BELIEVE")
   - Keep it real — Matt's brand is authentic building-in-public

   ### Agent 2 — Thumbnail Prompt
   Give this agent the full context from steps 2-3, the thumbnail research from `05-thumbnails/README.md`, and these instructions:
   - Generate a detailed image generation prompt for nanobanana
   - The prompt MUST start with: "I'm attaching a picture of my face to use in this thumbnail."
   - The thumbnail MUST feature Matt's face (from the attached photo) with a genuine expression (curiosity, excitement, or "aha" moment — NOT exaggerated YouTube shock face)
   - Choose one of these proven frameworks: Face + Bold Text, Reaction, Before/After, Stats + React, or Cut-Out Graphics
   - Follow the 60-30-10 color rule: blue primary (trust/tech), yellow or orange accent, white for contrast
   - The composition should follow Z-pattern: face/subject upper-left, context upper-right, text area lower-left, bottom-right empty
   - Include 3-5 words of bold thumbnail text that creates a curiosity gap with the title (complements, never repeats)
   - The prompt should describe: scene/background, Matt's expression and pose, lighting, color palette, mood, composition, and any props or screen elements
   - Also output the thumbnail text overlay separately (the 3-5 words to be placed on the image)
   - Specify that the image should be 1280x720, high contrast, readable at mobile size (168x94px)

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
