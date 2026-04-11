---
name: headline-thumbnail
description: Generate YouTube video title/headline options and a Nano Banana thumbnail prompt. Use when the user wants to brainstorm titles, create thumbnails, or both. Triggers on phrases like "headline", "thumbnail", "title for my video", "what should I call this video", "YouTube title", or any request about naming/titling/thumbnail for video content.
---

# Headline & Thumbnail Generator

Generate 10-15 YouTube title options and a Nano Banana thumbnail prompt for Matt's latest video.

## Arguments

The user may pass a day number (e.g., `/headline-thumbnail 5` for Day 5). If no number is provided, ask what day this is before generating.

---

# Part A: Headlines

## Title Format

Every title MUST follow this exact structure:

```
Day X, [headline], IN ONE HOUR
```

- Starts with `Day {number},`
- Then the headline (the creative part)
- Ends with `, IN ONE HOUR` (always uppercase, always present)

Examples:
- `Day 5, I Automated My Entire YouTube Pipeline, IN ONE HOUR`
- `Day 3, Building a Thumbnail Generator from Scratch, IN ONE HOUR`
- `Day 7, This AI Edits My Videos Better Than I Do, IN ONE HOUR`

The "Day X" and "IN ONE HOUR" are fixed — all creative energy goes into the middle section.

## Voice & Philosophy

These principles override the style groups below when there's a conflict:

1. **"IN ONE HOUR" carries the hook.** The ending is inherently surprising, so the headline (middle section) doesn't need to be a curiosity gap. It can be clear and specific — the combo still works. Prefer straightforward + surprising ending over vague + vague.
2. **Specific and educational over vague and hype.** Say what the video actually is. "How My AI YouTube Pipeline Works" beats "My 3 Rules Change Everything." Specificity ("AI YouTube Pipeline") always beats vagueness ("everything", "this changes things").
3. **Each title is an episode in a journey.** This is a serial, not a collection of standalones. Each title should feel like the next chapter — building on the last video. "Day X" isn't just a label, it's a narrative device. Viewers should feel like they're following along.
4. **Rough but real.** The tone is someone figuring it out in public, not someone who already has the answers. "Let me show you how this works" beats "I perfected my system." The audience is riding along, not watching a highlight reel.
5. **Sound like Matt, not a copywriter.** Conversational, natural, the kind of thing you'd say to a friend explaining what you built today.

## Step 1: Understand What Was Built

Run these in parallel to figure out what the video is about:

```bash
git log --oneline --all --since="1 week ago"
git log --all --stat --since="1 week ago"
git diff main@{1.week.ago}..main
gh pr list --state all --limit 10
```

Also read CLAUDE.md for project context. If the git history is sparse, expand the timeframe (2 weeks, 1 month) until there's meaningful content.

Skim any key changed files to understand what they actually do — don't just rely on commit messages.

## Step 2: Find the Story

Before writing any titles, answer these four questions (don't output them, just use them to inform your titles):

1. **What's the single most impressive or surprising thing that was built?**
2. **What's the benefit to the viewer?** (what can they learn, copy, or apply?)
3. **Any concrete results, numbers, or milestones?** (e.g., "9 automated pipeline stages", "$0 tools", "1 hour of work")
4. **What's the emotional hook?** (curiosity, aspiration, disbelief, urgency)

## Step 3: Generate Titles

Produce 10-15 titles in these four groups. Every title must follow these rules:

**Hard rules:**
- Follows the format: `Day X, [headline], IN ONE HOUR`
- The full title (including Day X and IN ONE HOUR) should be under 70 characters
- The headline portion (middle section) carries the primary keyword in its first 40 characters
- Accurately reflects what was actually built (YouTube's algorithm penalizes misleading titles via "Quality CTR" — if viewers click and leave, the video gets buried)

**Style guidance:**
- Sound like a real person, not a marketing department
- Be specific over generic — "I Automated My YouTube Thumbnails" beats "I Built an AI System"
- Lean into what makes this genuinely interesting, not what sounds impressive on paper
- Numbers and specifics perform well when they're real ("9 stages", "$0")
- Avoid generic/hype words ("INSANE", "CRAZY", "YOU WON'T BELIEVE") — Matt's brand is authentic

### Group 1: Episode / Journey
The strongest group for this channel. Each title should feel like the next chapter in the series. The viewer should think "oh, I want to see what happens next." Lean into progress, milestones, and the raw process of building.

### Group 2: Educational / Show-How
"Let me show you how this works." Promise the viewer will learn something specific and concrete. This pairs naturally with "IN ONE HOUR" — the ending makes the straightforward headline surprising.

### Group 3: Bold Claim
State something ambitious but true. Lead with the outcome or transformation. Keep it grounded — the claim should be something Matt would actually say out loud.

### Group 4: Curiosity Gap
Use sparingly. Only when there's a genuinely surprising result worth teasing. The headline should still be more specific than vague — let "IN ONE HOUR" do most of the intrigue work.

## Step 4: Pick the Best

Auto-select the single best title. Prioritize titles that: (1) feel like the next episode in an ongoing series, (2) are specific about what was actually built, and (3) sound like something Matt would say. Output the chosen title and a one-line justification.

---

# Part B: Thumbnail

## Step 5: Read Thumbnail Context

Read these in parallel (skip any already read in Step 1):
- Read today's daily file from `daily/YYYY-MM-DD.md` using today's date. If no file exists, check the most recent file in `daily/`.
- Read `05-thumbnails/README.md` for thumbnail research and best practices.
- Read `00-overview/README.md` for brand identity and channel positioning.

## Step 6: Distill the Visual Story

From the context gathered, identify:
- The single most visual or impressive thing being built/shown today
- The viewer benefit ("why should I care?")
- The emotional angle — what's the RAW honest feeling? (excited it worked, stressed about a deadline, surprised by a result, grinding through it)
- The key number or metric that tells the story (subscriber count, hours spent, tools built, money saved)
- What would make someone stop scrolling and click

## Step 7: Generate the Nano Banana Prompt

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

## Step 8: Thumbnail Pairing

For the top 3 headline titles (from Step 4), suggest how the thumbnail text + expression could pair with each. The title and thumbnail should complement each other, never repeat. Together they tell a bigger story than either alone.

## Output Format

---

## Headline
[The chosen title]

**All candidates:**
[Grouped by style, numbered]

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

## Step 9: Refine

Ask which headline style or thumbnail direction resonates. Offer to generate 5 more title variations in that direction, or adjust the thumbnail prompt.
