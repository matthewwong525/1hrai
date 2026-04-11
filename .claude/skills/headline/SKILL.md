---
name: headline
description: Generate YouTube video title/headline options. Use this skill whenever the user wants to brainstorm, create, or refine video titles, headlines, or naming for YouTube videos. Triggers on phrases like "headline", "title for my video", "what should I call this video", "video name", "YouTube title", or any request about naming/titling video content.
---

# Headline Generator

Generate 10-15 YouTube title options for Matt's latest video, grouped by style.

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

## Arguments

The user may pass a day number (e.g., `/headline 1` for Day 1). If no number is provided, ask what day this is before generating titles.

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

## Step 5: Thumbnail Pairing

For the top 3 titles, suggest what the thumbnail should show. The title and thumbnail should complement each other, never repeat. Together they tell a bigger story than either alone.

Examples of good pairing:
- Title: "Day 5, I Automated 90% of YouTube, IN ONE HOUR" → Thumbnail: pipeline diagram with 9 green checkmarks
- Title: "Day 3, the Upload Broke Everything, IN ONE HOUR" → Thumbnail: Matt's face looking at an error screen

Keep thumbnail suggestions to one line each.

## Step 6: Refine

Ask which style or specific title resonates. Offer to generate 5 more variations in that direction, or to combine elements from different titles.
