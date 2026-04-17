# Blog Post Guide for Product Launches

This guide covers how to write Imgix product launch blog posts. All posts must follow the Imgix brand voice (read the `imgix-brand-voice` skill for full details).

## Structure

Every launch blog post follows this pattern:

### 1. Title + Subtitle
Title is benefit-driven, title case. Communicates what the reader gets, not what Imgix built. Keep it under ~15 words.

Subtitle sits beneath the title and gives a conversational preview of what's in the post. It can be slightly informal. Think of it as the "here's what you'll find" line.

**Good title examples:**
- "Q2 2026 Release: What's New for Video, AI, and Your Visual Workflow"
- "Smarter Video, Same Simplicity"
- "Take Full Control with Smarter, Faster Visual Editing"

**Good subtitle example:**
- "Our biggest video release yet. Check out what you can do with longer video, adaptive streaming, global captions, and smarter upscaling."

**What to avoid:**
- "We're Excited to Announce..." (throat-clearing)
- Feature-first headlines that don't convey value
- Superlatives you can't back up

### 2. Opening: Problem Setup + Empathy Bridge + Feature Preview
The opening is 2-3 paragraphs that do three things:

**Paragraph 1: The reader's reality.** Address the reader directly with "you/your." Describe the real tensions they face. Be specific and grounded, not abstract. Name concrete scenarios: devices, teams, workflows.

**Paragraph 2: Empathy bridge → feature preview.** Start with a short empathy sentence ("We get it.") then name the specific problems this release solves. Then preview what's in the release as a flowing sentence, not a bulleted list. End with a transition line like "Here's a look at what's new."

The opening should map the tensions in paragraph 1 to the solutions in paragraph 2. If paragraph 1 mentions quality, speed, and cost, the feature preview should address all three.

**Example of a strong opening:**
> Your product videos need to look sharp on a phone in New York and a monitor in Jakarta. Your content team is creating more assets than ever, but captioning, localizing, and reformatting eat up time they don't have. Your developers are stitching together separate tools for images and video, and the overhead adds up every time you ship.
>
> We get it. Getting every asset to show up exactly right, everywhere, while balancing quality, speed, and cost is one of the hardest problems in visual media, and it only gets harder as you scale. This release is designed to take that off your plate. [Feature preview sentence.] Here's a look at what's new.

### 3. Feature Sections
Each feature gets its own section with a subheading. Follow this rhythm:

1. **Feature name as subheading** — benefit-framed, not technical. E.g., "Longer Video, No Limits on What You Can Build" not "Video V3 Cache Layer Update"
2. **The problem** (1-2 sentences) — what was hard before, what the limitation was
3. **The solution** (2-3 sentences) — how Imgix solves it, with enough specifics to be credible
4. **Inline design direction** — `[Casey: brief visual description]`
5. **Social proof or stat placeholder** — if available, drop it in naturally. If not, use `[X]` with a question to the relevant person
6. **Closing line** — one sentence connecting back to the reader's workflow or the broader platform

Keep each section to 3-5 short paragraphs. Don't over-explain. Link to docs for technical depth.

### 4. Existing Features Recap (if applicable)
When launching new features in a category, include a short recap of existing features in that category. Use **one-liner format**: feature name in bold, one sentence, "Docs →" link. No full paragraphs. This section is a quick scan.

Close the recap with a single "one platform" sentence: "All of these work alongside the new features in this release. One platform, same URLs, same API."

### 5. Closing
Split by audience. Two short paragraphs, one action each:

1. **Existing customers:** "Already an Imgix customer? Check the docs or reach out to your account manager..."
2. **New visitors:** "New here? Start a free trial and see what changes when..."

One sentence tying back to the platform narrative before the split is fine. Don't restate the whole post. Every CTA link must include UTM parameters.

## Formatting Rules

- Paragraphs: 2-4 sentences max
- No code examples in the blog post (link to docs instead)
- Feature names should be descriptive: "Smart Cropping" not "AutoCrop v2"
- Use bold sparingly for emphasis on key phrases, not entire sentences
- No exclamation points in body copy (OK sparingly in headlines or CTAs)
- Subheadings break up content for scannability
- Target length: 3-minute read for announcements (roughly 600-800 words)

## Visuals

- Include inline Casey directions `[Casey: ...]` for each major feature section
- Directions should describe the visual concretely: subjects, layout, context
- Consider animated/GIF format for video-heavy launches
- For hero image, think about whether a compilation of capabilities works better than a single feature shot
- Host final visuals via Imgix CDN
- Add alt text that describes what the visual shows

## UTM for Blog CTAs

Campaign format: `q[quarter]_[year]_[feature]_launch`
Source/medium: `utm_source=blog&utm_medium=organic`
Content: describe the CTA (e.g., `utm_content=hero_cta`, `utm_content=footer_cta`)
