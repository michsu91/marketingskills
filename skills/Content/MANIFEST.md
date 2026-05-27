# Imgix Content System

**Owner:** Michelle Su
**Created:** April 17, 2026
**Last Updated:** May 27, 2026

## What This Is

This folder is a coordinated system for creating, editing, and distributing marketing content across all channels. Any Claude session that opens this folder should read this manifest first, check the STATUS.md in each subfolder (where available), and pick up the highest-priority incomplete work.

## How to Use This Folder

**When to invoke this folder:** You have a content output to produce (blog post, landing page copy, social post, deck) or you need to plan what to produce. If you don't yet know what to write, start here with content-strategy. If you're editing existing copy, jump straight to copy-editing.

**Context to bring:**
- The audience (developer, engineering manager, marketer mix)
- The channel (blog, landing page, social, deck, internal doc)
- Constraints (word count, deadline, target keyword, brand voice exceptions)
- Source material if it exists (outline, feature spec, customer quote, Gong call)

**How the sub-skills fit together:**
- This folder is a **pipeline more than a menu.** Most real work chains skills.
- **Plan:** content-strategy figures out what to write and why
- **Write:** copywriting drafts new copy
- **Edit:** copy-editing tightens existing copy via Seven Sweeps
- **Distribute:** social-content repurposes long-form for LinkedIn and Twitter
- **Present:** imgix-brand-deck turns content into slides
- You don't have to use them all. For a single edit pass, invoke copy-editing directly.

**Typical prompts:**
- "Draft a blog post on [topic] for our developer audience targeting [keyword]. Run content-strategy first to confirm angle, then copywriting."
- "Edit this homepage hero copy using copy-editing with Seven Sweeps."
- "Plan next quarter's content calendar. Use content-strategy and pull from marketing-ideas for inspiration."
- "Repurpose this blog post into a LinkedIn thread using social-content."

**Output to expect:** A draft (markdown, optionally pushed to Webflow CMS), an edit pass with rationale, a content calendar in a table, a social post variant set, or a `.pptx` file.

**When NOT to use this folder (and where to go instead):**
- Technical API docs or integration tutorials → Content/technical-writing (planned)
- Email sequences and lifecycle copy → Lifecycle/email-sequence
- Cold outbound emails → Acquisition/cold-email
- SEO briefs from gap analysis → start with Discoverability/content-gaps, then come back here
- Pure brand voice questions → imgix-brand-voice (global)

## How It Works

1. **Read this MANIFEST.md** to understand the system and current priorities
2. **Read MEMORY.md** for accumulated context from previous sessions
3. **Always load global skills first:** `imgix-brand-voice` (tone/style) and `product-marketing-context` (positioning)
4. **Check each subfolder's STATUS.md** for current state
5. **Execute work** using the SKILL.md in the relevant subfolder
6. **Update STATUS.md and MEMORY.md** when work is completed
7. **Report results** via Slack to Michelle

## Connected Tools (MCP)

- **Webflow** — Publish blog posts and landing page content
  - Site ID: `6705f4b15aee7ca914fff083`
  - Use `data_cms_tool` for blog posts (CMS collection items)
  - Use `data_pages_tool` for static landing pages
- **Jira** — Track content creation tasks (MKTG project)
- **Slack** — Notify when content is ready for review
- **HubSpot** — Track which content drives leads and pipeline
- **Google Drive** — Source docs, briefs, and collaboration

## Global Dependencies

These skills apply to ALL content this system produces:
- **imgix-brand-voice** — Tone, terminology, capitalization rules
- **product-marketing-context** — ICP, positioning, value propositions

## Subfolders

### 1. `content-strategy/` — PLANNING
Decides what content to create, what topics to cover, and how to prioritize. Run this first when planning a content calendar or deciding what to write.

### 2. `copywriting/` — CREATION
Writes new marketing copy for website pages, landing pages, and marketing materials. The primary content creation skill.

### 3. `copy-editing/` — REFINEMENT
Edits and improves existing copy. Use for content refreshes, tone alignment, and quality passes.

### 4. `imgix-brand-deck/` — PRESENTATIONS
Creates on-brand Imgix slide decks (.pptx) following official brand guidelines. Use for pitch decks, account reviews, and internal presentations.

### 5. `social-content/` — DISTRIBUTION
Creates and optimizes social media content for LinkedIn, Twitter/X, and other platforms. Repurposes long-form content into social formats.

### 6. `case-studies/` — PROOF POINTS *(planned)*
Framework for writing customer case studies. Imgix has strong customer stories (Ikyu, Unsplash, Skims, Porsche) that need to be structured for maximum impact.

### 7. `video-content/` — VISUAL *(planned)*
Strategy for demo videos, tutorials, and YouTube content. Developer audiences respond well to video walkthroughs.

### 8. `technical-writing/` — DEVELOPER CONTENT *(planned)*
Developer documentation, API guides, and technical tutorials. Distinct from marketing copywriting — this is code-first, tutorial-style content.

## Cross-System References

- **Discoverability → Content:** Content-gaps identifies what to write; this system writes it. AEO and programmatic-seo provide optimization requirements.
- **Content → Conversion:** Content drives traffic that Conversion optimizes into signups.
- **Content → Product-Marketing:** Launch-strategy and sales-enablement need content assets.
- **Acquisition → Content:** Paid ads and lead magnets need content created here.

## Definition of Done

This system is successful when:
- Imgix publishes 4+ high-quality content pieces per month
- Every piece follows brand voice guidelines and AEO best practices
- Content drives measurable organic traffic and pipeline
- Case studies exist for top 5 customer verticals
