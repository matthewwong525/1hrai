# 05 — Thumbnail Generation

## Goal
Automatically generate click-worthy YouTube thumbnails for each video using AI image generation and templating.

## Current Status
Research complete. Implementation not started.

## Research: What Makes A-Tier YouTube Thumbnails

### 1. Technical Specifications

| Spec | Recommended | Notes |
|------|-------------|-------|
| Dimensions | 1280 x 720 px | 16:9 aspect ratio required |
| Max resolution | 3840 x 2160 px | YouTube raised limit to 4K in early 2026 |
| Minimum width | 640 px | Will appear blurry on HD screens |
| File size | Under 2 MB | Maintains ~99% sharpness in PNG/JPG |
| New file size limit | Up to 50 MB | Rolled out early 2026 for 4K thumbnails |
| Formats | JPG, PNG, GIF, WebP, BMP | JPG and PNG most reliable |
| Color profile | sRGB | Required for accurate color rendering |
| Mobile display size | ~168 x 94 px | What viewers actually see on phones |
| Text safe zone | Central 1146 x 423 px | Keep critical elements here |
| Bottom-right | AVOID | YouTube overlays video duration here |

### 2. Psychology of Click-Worthy Thumbnails

**The Curiosity Gap:**
- When a thumbnail poses a visual question and the title provides a logical answer, this combination appears in 78% of high-CTR videos
- The brain processes visual thumbnails 60,000x faster than text
- 96% of browse sessions: image serves as primary hook over title
- Viewers make click decisions in ~0.3 seconds

**Eye Contact and Visual Processing:**
- 65% of YouTube users aged 18-34 focus on thumbnails with direct eye contact before reading the title
- 40% of thumbnail clicks come from the top-left "emotion zone"
- Z-pattern layout: emotional subject top-left, context top-right, visual hook bottom-left

**Authenticity Shift (2025-2026):**
- 73% of viewers prefer "relatable" expressions over exaggerated "YouTube face"
- Real human skin texture achieves 22% higher satisfaction than fully AI-generated faces
- "Proof of Human" is the dominant 2026 trend — thumbnails showing genuine micro-expressions outperform AI-generated ones
- Misleading thumbnails get penalized by YouTube's algorithm (high clicks + low engagement = reduced reach)

### 3. Face and Emotion Data

**Impact on CTR:**
- Faces with strong emotion: +20-30% CTR (VidIQ data)
- Emotional faces: +42.3% clicks (TubeBuddy study, Nov 2025, 1.2M videos)
- Expressive genuine faces: +25-50% CTR due to immediate trust

**Nuanced Findings (Search Engine Journal, 300K+ viral videos, 2025):**
- Overall, thumbnails with faces and without faces perform similarly at scale
- Faces help more for larger channels than smaller channels
- Results vary by niche: faces help in finance, hurt in business content
- Multiple faces outperform single faces
- Impact depends on niche, format, and audience familiarity

**Expression Rankings:**
- "Surprised" appears in 26.95% of top-performing thumbnails
- Best performers: surprise, shock, excitement, curiosity
- Worst performer: neutral/blank expressions

**Expression Performance Data:**

| Expression | % of Top Thumbnails | Notes |
|------------|--------------------:|-------|
| Surprised | 27% | High avg views, most common in top performers |
| Happy | 27% | High avg views, tied with surprised |
| Sad (underexploited) | 1.8% | **2.3M avg views** — highest of any expression |
| Fearful | 18% | Used heavily by MrBeast |

**2024-2025 shift:** "Closed mouth" determined expressions are outperforming the traditional shocked/open-mouth face. The trend is moving toward intensity and authenticity over exaggerated mugging.

**For Matt's tech/AI education niche:** Use genuine expressions (curiosity, excitement about a result, "aha" moments) rather than exaggerated shock faces. Position face in upper-left third. Since this is educational/business content, test both with-face and without-face variants. Consider "sad" expressions for problem-focused videos (underexploited = opportunity).

### 3b. Thumbnail-Title Relationship: "1 + 1 = 3"

The thumbnail and title should **complement, never repeat.** Together they create a more compelling narrative than either alone:
- Thumbnail: shocked face looking at something off-screen. Title: "I can't believe they actually did this"
- Thumbnail: before/after split. Title: "72 hours changed everything"
- Thumbnail: huge number "$50,000,000." Title: "I gave it all away"

**For Matt's "Day X" series:** The thumbnail shows the visual result or a reaction; the title provides the "what" and day number. Never put the full title text on the thumbnail.

### 3c. 7 Thumbnail Frameworks

1. **Before/After** — 35% higher CTR than showing only the finished result
2. **Reaction** — Close-up face reacting to something off-screen
3. **Mystery** — Blurred/hidden elements, arrows pointing at obscured items
4. **Comparison** — Two items side by side with "VS"
5. **Face + Bold Text** — Most universally applicable
6. **Stats + React** — Big number next to emotional face
7. **Cut-Out Graphics** — Subject on clean/contrasting background (trending in 2025)

**For AI education:** Before/After (showing a tool's output), Face + Bold Text, and Stats + React work best. Mystery thumbnails work for "I found a tool that..." style videos.

### 3d. MrBeast's Thumbnail Process

- Spends up to $10,000 per thumbnail
- Creates 50+ variations per video
- A/B tests 3+ versions simultaneously
- Measures "Watch Time Share" not just CTR — clickbait that causes drop-off loses
- If a video underperforms in the first hours, thumbnails are swapped immediately
- Current formula: 1-2 words maximum, extreme expressions, dramatic color contrast

**Takeaway for 1HR AI:** You don't need 50 variations, but always generate 2-3 variants for A/B testing. Swap the thumbnail if CTR is below target after 48 hours.

### 4. Text on Thumbnails

**Word Count:**
- 3-5 words maximum (strict)
- 1-2 impactful words is often even better
- 20 characters or fewer
- 6+ words drops CTR to 4.3% — too long to scan, too short for a story
- 73% of creators make the mistake of repeating the video title verbatim

**Font Specifications:**
- Font size: 150-200px for primary headlines, 80-120px for secondary (at 1280x720)
- Font weight: 700 or heavier (bold/extra bold)
- Style: Bold sans-serif only (Impact, Bebas Neue, Montserrat Extra Bold)
- Outline: 4-8px contrasting outline for readability on any background
- Text should cover 20-30% of the thumbnail area

**Placement:**
- Use rule of thirds grid
- Top or bottom third works best
- NEVER bottom-right (video duration overlay)
- Top-left text placement used in 87% of 2025's top thumbnails

**CTR Impact:**
- Text overlays increase CTR by 30-40% when used correctly

### 5. Color Theory

**The 60-30-10 Rule:**
- 60% dominant color (background)
- 30% secondary color (subject/overlay)
- 10% accent color (text/highlight)

**Best Performing Colors:**
| Color | Use Case | Why |
|-------|----------|-----|
| Red | Urgency, excitement | Most powerful for thumbnails; used by MrBeast, PewDiePie |
| Yellow | Attention, visibility | Most visible color in spectrum; yellow+black = maximum readability |
| Blue | Trust, expertise | Best for educational/tech/business content |
| Green | Growth, money | Pairs well with red (complementary) |
| Orange | Energy, warmth | High CTR when combined with dark backgrounds |
| White | Clean, contrast | Essential for text outlines and clean designs |

**Key Principles:**
- Use 2-3 colors maximum per thumbnail
- High-contrast combinations (complementary colors): red/green, yellow/purple, blue/orange
- High-contrast thumbnails with bold colors increase CTR by 20-30%
- Dark backgrounds make bright subjects pop
- Avoid pastels and muted colors — they disappear in the feed
- 2-3x higher scroll-stop rates for high-contrast thumbnails on mobile

**For Matt's niche:** Blue as primary (trust/tech), with yellow or orange accents for text. This signals expertise while maintaining scroll-stopping contrast.

### 6. Composition and Layout

**Rule of Thirds:**
- Divide frame into 9 equal sections
- Place main subject at intersection points
- Off-center placement feels more dynamic than centered

**Visual Hierarchy (what viewers see in order):**
1. Size — larger elements dominate
2. Saturation — bright colors pull focus
3. Position — rule-of-thirds intersections draw attention

**Z-Pattern Layout (highest performing):**
- Top-left: emotional face / main subject
- Top-right: context / secondary element
- Bottom-left: visual hook / text
- Bottom-right: leave empty (video duration overlay)

**Depth and Layering:**
- Background layer (furthest back)
- Subject in middle ground
- Text on top
- 3D depth replacing flat design in 2026

**Key Rules:**
- Fill most of the frame with the subject
- One dominant element + one supporting element (max before clutter)
- One directional element per thumbnail (arrow, circle, or highlight box)
- Cluttered thumbnails with too many elements lower CTR by 23%

### 7. Common Mistakes That Kill CTR

| Mistake | Impact |
|---------|--------|
| Auto-generated thumbnails (no custom design) | Custom designs boost CTR by 60-70% |
| 6+ words of text | CTR drops to 4.3% |
| Repeating video title on thumbnail | 73% of creators make this mistake; kills curiosity |
| Low contrast / muted colors | Lost in the feed; blue/beige worst offenders |
| Visual clutter (many elements, fonts, faces) | -23% CTR |
| Illegible text on mobile | 70%+ of YouTube viewing is mobile |
| Misleading thumbnails | Algorithm penalty for low retention |
| Inconsistent branding | Algorithm treats channel as 50 micro-channels |
| Mismatched face emotion vs. topic | Confuses viewers |
| "AI slop" (obvious AI-generated thumbnails) | -30% CTR reduction |
| Flat/minimalist design | -35% algorithm penalty |
| Wrong resolution | 40% blur increase on large screens |

### 8. Branding and Consistency

- Most successful channels have thumbnails identifiable without reading the title
- Consistent branding yields 1.8x subscriber growth rate vs. weekly changes
- Use a recognizable template: same font, color palette, and layout
- For Matt's channel: establish a "Day X" series look — consistent template with the day number as a prominent element

### 9. A/B Testing

**YouTube Native (Test & Compare):**
- Upload up to 3 thumbnails per video
- YouTube shows them to different viewer groups
- Reports which gets the most watch time (not just CTR)
- Free for all creators

**TubeBuddy:**
- Full A/B testing with 95% statistical significance threshold
- Minimum 500 impressions per variant before declaring winner
- Reports CTR, subscribers gained, watch time, engagement
- Legend plan ($49/mo) for thumbnail testing
- Can upload up to 20 variants per video

**Strategy:**
- Track CTR after 48 hours
- Change one element at a time to isolate results
- Always test: with face vs. without, different text, different colors

### 10. Tools and Workflow

**Design Tools:**

| Tool | Best For | Cost |
|------|----------|------|
| Canva | Speed, templates, beginners | Free / $13/mo Pro |
| Photoshop | Precision, advanced compositing | $23/mo |
| Adobe Express | Quick edits with Adobe ecosystem | Free / $10/mo |
| Figma | Template-based, team collaboration | Free / $15/mo |

**AI Image Generation:**

| Tool | Strength | Cost |
|------|----------|------|
| Midjourney | Strongest aesthetic sense, scroll-stopping visuals | $10/mo |
| DALL-E 3 | Best at rendering text within images | Pay-per-use via API |
| Stable Diffusion | Most customizable, runs locally, no subscription | Free (local) |
| Flux 2 | Best photorealistic thumbnails | ~$1.50/batch |
| Ideogram V3 | Best for text-heavy thumbnails | Varies |

**Background Removal:**
- Photoshop Select & Mask
- remove.bg (API available)
- Canva background remover

**Thumbnail Analysis & Testing:**
- TubeBuddy (A/B testing, thumbnail analyzer)
- VidIQ (thumbnail scoring)
- ThumbnailTest (dedicated testing tool)

### 11. Programmatic Thumbnail Generation

**Template-Based API Services:**

| Service | Approach | Best For |
|---------|----------|----------|
| Bannerbear | API-driven, template-based, Zapier integration | Automated pipelines with no-code |
| DynaPictures | REST API, bulk generation, template library | High-volume batch generation |
| Placid | Web-based templates, API + no-code (Zapier/Make) | Workflow integration |

**Code Libraries:**

| Library | Language | Use Case |
|---------|----------|----------|
| Pillow (PIL) | Python | Text overlay, compositing, image manipulation |
| Sharp | Node.js | High-performance image resizing, compositing |
| ImageMagick | CLI / bindings | General-purpose image processing |
| Puppeteer | Node.js | HTML/CSS-to-image (design thumbnails as HTML) |
| node-canvas | Node.js | Canvas API for server-side image generation |

**Recommended Pipeline for This Project:**

```
1. Extract best frame (FFmpeg)
2. Remove/replace background (remove.bg API or rembg Python lib)
3. Generate AI background if needed (Stable Diffusion / Flux via API)
4. Composite layers (Pillow or Sharp):
   - Background layer
   - Subject/face cutout (middle)
   - Text overlay (top, bold sans-serif, 3-5 words)
   - Branding elements (consistent template)
5. Export at 1280x720, JPG, <2MB
6. Generate 2-3 variants for A/B testing
7. Upload via YouTube Data API
```

**Puppeteer Approach (HTML-to-Image):**
- Design thumbnail as an HTML template with CSS
- Render at 1280x720 using Puppeteer screenshot
- Swap text, images, colors via template variables
- Advantages: full CSS styling, easy to iterate on design, web fonts

## System Spec (Updated)

- Extract a representative frame from the video (high-energy moment, clear face, genuine expression)
- Use a template system with layered composition: background + subject cutout + bold text overlay + branding
- Follow the 60-30-10 color rule: blue primary (trust/tech), yellow or orange accent text, white outlines
- Generate title text: 3-5 words max, bold sans-serif (Bebas Neue or Montserrat Extra Bold), 4-8px contrasting outline
- Position text in upper-left or lower-left third; face in upper third with direct eye contact
- Produce 2-3 thumbnail variants for A/B testing via YouTube's Test & Compare
- Include "Day X" branding element for series consistency
- Output at 1280x720 resolution, JPG format, under 2MB
- Validate readability at 168x94px (mobile preview size)

## Tools/APIs Needed
- FFmpeg (frame extraction from video)
- Pillow or Sharp (text overlay, compositing, layering)
- rembg or remove.bg API (background removal)
- Stable Diffusion or Flux API (AI background generation, optional)
- Claude API (thumbnail text generation — short, punchy, curiosity-driving)
- YouTube Data API (upload and A/B testing)
- Puppeteer (alternative: HTML template to image approach)

## Scripts

### `/thumbnail` skill (`.claude/commands/thumbnail.md`)
Claude Code skill that reads today's `daily/` file and generates a Nano Banana prompt.

**Usage:** `/thumbnail 5` (where 5 is the day number)

**What it does:**
1. Reads today's daily file to understand what the video covers
2. Reads thumbnail research + channel branding for context
3. Picks the best-fitting thumbnail framework for today's topic
4. Generates a ready-to-paste Nano Banana prompt (natural language, not tag soup)
5. Outputs iterative refinement prompts and an A/B test variant idea

**Also generates thumbnails as part of:** `/changes` skill (headline + thumbnail + talking points together).
