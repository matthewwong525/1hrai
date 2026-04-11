Generate a Nano Banana prompt for today's YouTube thumbnail. The argument is the day number (e.g., `/thumbnail 5`).

## Steps

1. **Extract the day number** from `$ARGUMENTS`. If missing, ask for it before proceeding.

2. **Read today's context** — run these in parallel:
   - Read today's daily file from the `daily/` folder (try `daily/YYYY-MM-DD.md` using today's date — check both current year and prior year in case of naming convention). If no file exists for today, check the most recent file in `daily/`.
   - Read `05-thumbnails/README.md` for thumbnail research and best practices.
   - Read `00-overview/README.md` for brand identity and channel positioning.
   - `git log --oneline --all --since="3 days ago"` for very recent commits to supplement the daily file.

3. **Distill the visual story** — from the daily file and git context, identify:
   - The single most visual or impressive thing being built/shown today
   - The viewer benefit ("why should I care?")
   - The emotional angle — what's the RAW honest feeling? (excited it worked, stressed about a deadline, surprised by a result, grinding through it)
   - The key number or metric that tells the story (subscriber count, hours spent, tools built, money saved)
   - What would make someone stop scrolling and click

4. **Generate the Nano Banana prompt** using these rules:

   ### Style: Raw & Authentic (inspired by lockedinpoker)
   The thumbnail should look like a real moment from Matt's life, NOT a polished graphic design piece. Think raw vlog screenshot with bold text slapped on top. The vibe is "building in public" — real screens, real reactions, real numbers. This is a journey series where each day is a chapter, building toward the goal of 1,000 subscribers.

   Key style principles:
   - **Real setting, not a studio** — Matt at his desk, laptop open, real room with natural mess and personality. NOT a clean gradient background or glowing sci-fi scene.
   - **Selfie/vlog camera quality** — slightly wide angle, casual framing, like a photo someone actually took with their phone. NOT a professional portrait with 85mm bokeh.
   - **Big, bold, slightly imperfect text** — chunky text that looks hand-placed, not perfectly centered or aligned. Slightly tilted or overlapping the subject is fine. The text should feel urgent and raw, not designed.
   - **One clear emotion** — each thumbnail captures ONE honest feeling. Not a generic "excited face" but a specific reaction: staring at subscriber count, laughing at something that broke, focused while coding.
   - **Show real screens when relevant** — actual laptop/monitor showing Claude Code, YouTube Studio analytics, subscriber counts, the pipeline running. Real artifacts > abstract illustrations.
   - **Minimal composition** — just Matt + big text + maybe one real prop or screen. Two elements max. No flowcharts, no icons, no decorative elements.

   ### Nano Banana Prompting Rules
   - Write in **natural language paragraphs**, NOT keyword tag soup — Nano Banana is Gemini-powered and understands full sentences
   - Structure: **Subject + Action + Scene** (who/what, what they're doing, where/how it looks)
   - Put any text you want rendered in the image inside `"quotes"`
   - Describe real, tangible settings — "at a desk with a laptop," "in a bedroom with LED lights," "looking at a phone screen"
   - Use casual photography terms: "phone camera selfie angle," "slightly overexposed indoor lighting," "wide angle close-up"
   - Include negative constraints at the end: "No watermark, no extra people, no deformed hands, no overly polished or studio look, no AI-generated glow effects"
   - The prompt should be detailed enough to work in one shot, but designed for iterative refinement

   ### Thumbnail Composition Rules
   - The prompt MUST start with: **"I'm attaching a picture of my face to use in this thumbnail."**
   - Matt's face with a **genuine, raw expression** — the real emotion of the moment, not a YouTube performance face
   - **Simple layout**: Matt on one side (left or center), big text on the other side or overlapping
   - **Text style**: chunky bold sans-serif, white or bright colored with a thick black or dark outline/shadow. Slightly tilted or imperfect placement adds to the raw feel. Can overlap the subject slightly.
   - **1-3 words MAX** of thumbnail text — a number, a reaction word, or a short phrase that hooks. Examples: "1,000 SUBS?!", "IT WORKS", "DAY 5", "$0", "I QUIT?", "WTF"
   - **Green for growth/money/subscriber milestones**, white or yellow for emphasis, red for urgency or setbacks — pick ONE accent color per thumbnail
   - Include **"Day {number}"** either as the main text or as a small label (like an episode tag in the corner)
   - The text should create a curiosity gap with the title — complement, never repeat
   - Keep bottom-right clear (YouTube overlays video duration there)
   - Output resolution: 1280x720, 16:9 landscape
   - Must be readable at 168x94px (mobile preview size)

   ### Expression Guidelines
   - Match the expression to what ACTUALLY happened that day — what's the honest reaction?
   - Good expressions for this style: staring at a screen in disbelief, laughing, frustrated focus, quiet determination, genuine surprise at a result
   - Avoid: posed/polished expressions, exaggerated YouTube shock face, generic smiling
   - The expression should make someone think "what happened to this guy?" and click to find out

   ### The 1,000 Subscriber Journey
   Every thumbnail is a chapter in the story of Matt building toward 1,000 subscribers using AI. The thumbnails should evolve over time:
   - Early days (1-10): excitement, uncertainty, building the foundation, "can this actually work?"
   - Mid journey (10-30): grinding, real results starting to show, setbacks, breakthroughs
   - Late journey (30+): momentum, real numbers, getting close, the final push

5. **Output in this format:**

   ---

   ## Thumbnail for Day {number}

   **Today's topic:** [One-line summary of what the video covers]

   **The moment:** [What's the raw, honest visual moment from today's session?]

   **Framework:** [Which approach and why — keep it simple]

   **Nano Banana prompt:**

   [The full prompt — ready to paste into Nano Banana]

   **Text overlay:** [The 1-3 words to place on the thumbnail]

   **Expression:** [The specific genuine expression and why]

   ### Refinement prompts
   After the first generation, paste these one at a time to improve it:
   1. [Make it feel more raw/authentic — less AI, more real]
   2. [Fix the text — bigger, bolder, more impactful]
   3. [Adjust the expression or framing]

   ### A/B test idea
   [One alternative text or composition to test]

   ---
