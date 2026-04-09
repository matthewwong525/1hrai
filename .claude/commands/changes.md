Analyze the entire repo and git history to create YouTube-ready talking points for Matt to record a summary video.

## Steps

1. **Gather context**: Run these in parallel to build a full picture:
   - `git log --oneline --all --since="1 week ago"` for recent commits (adjust timeframe if sparse — expand to 2 weeks, 1 month, etc. until you have meaningful content)
   - `git log --all --stat` for a fuller view of what files changed and how much
   - `git diff main@{1.week.ago}..main` (or appropriate range) to see actual code changes
   - Read key files in the repo to understand the project structure and what it does
   - Check for any open PRs with `gh pr list`

2. **Identify themes**: Group the changes into logical themes/features rather than listing commit-by-commit. Think about what an audience would care about — not "updated line 42 of utils.js" but "added real-time notifications so users get instant feedback."

3. **Write the talking points script** in this format:

---

### 🎬 Video Script: [Project Name] Update

**Intro** (10-15 seconds)
- A casual, natural opening line for Matt. Example: "Hey everyone, quick update on what I've been building this week..."

**Section 1: [Theme/Feature Name]** (30-60 seconds)
- What changed and why it matters (plain English, no jargon unless the audience is technical)
- What to show on screen (specific file, page, or demo action)
- A one-liner transition to the next section

**Section 2: [Theme/Feature Name]** (30-60 seconds)
- Same structure

*...repeat for each theme...*

**Wrap-up** (10-15 seconds)
- What's coming next / what Matt is working on next
- Call to action (subscribe, comment, etc.)

---

4. **Tailor the tone**: Keep it conversational — this is Matt talking to camera, not a changelog. Use "I" and "we", short sentences, and enthusiasm where appropriate. Avoid reading out code — instead describe what the code *does* and *why*.

5. **Include screen recording cues**: For each section, note what Matt should have on screen (specific page of the app, terminal, VS Code with a file open, etc.) so he can plan his screen recording.

6. **Estimate timing**: Add rough time estimates per section so Matt knows if the video will be 2 minutes or 10 minutes, and can adjust.
