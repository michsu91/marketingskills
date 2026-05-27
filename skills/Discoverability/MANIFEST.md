# Imgix Discoverability System

**Owner:** Michelle Su
**Created:** March 23, 2026

## What This Is

This folder is a self-executing system for improving imgix's discoverability — across both traditional search engines (SEO) and AI answer engines (AEO). Any Claude session that opens this folder should read this manifest first, check the STATUS.md in each subfolder, and pick up the highest-priority incomplete work.

## How It Works

1. **Read this MANIFEST.md** to understand the project and current priorities
2. **Read MEMORY.md** for accumulated context, decisions, and lessons from previous sessions
3. **Check each subfolder's STATUS.md** to see what's been done and what's next
4. **Execute the highest-priority incomplete work** using the SKILL.md instructions in that subfolder
5. **Update the STATUS.md** when work is completed
6. **Update MEMORY.md** with any new learnings, decisions, or context changes
7. **Report results** via Slack to Michelle

## Connected Tools (MCP)

This system is wired into imgix's actual infrastructure:

- **Webflow** — Read and modify imgix.com pages, meta tags, content, and structure directly
  - Site ID: `6705f4b15aee7ca914fff083`
  - Domains: imgix.com, www.imgix.com, blog.imgix.com
- **Jira** — Create tickets for work requiring human review, track progress
- **Slack** — Post updates when workflows complete or need attention
- **HubSpot** — Pull CRM data to understand which content converts leads
- **Google Calendar** — Schedule content publication and review cycles
- **Gmail** — Send outreach for backlink campaigns or partnership content

## Global Dependencies

These skills apply to ALL content this system produces:
- **imgix-brand-voice** — Tone, terminology, capitalization rules
- **product-marketing-context** — ICP, positioning, value propositions

## Cross-System References

- **Discoverability → Content:** Content-gaps identifies what to write; Content system creates it.
- **Discoverability → Conversion:** Organic traffic feeds into pages Conversion optimizes.
- **Product-Marketing → Discoverability:** Competitive intel informs comparison content and AEO narratives.
- **Discoverability → Lifecycle:** New content triggers lifecycle nurture sequences.

## Subfolders (Priority Order)

### 1. `technical-seo/` — HIGH PRIORITY
Fix on-site technical SEO issues that are hurting crawlability and rankings. These are usually quick wins with outsized impact.

### 2. `content-gaps/` — HIGH PRIORITY
Identify and fill keyword gaps where imgix should rank but doesn't. Create content briefs and draft content targeting high-intent terms.

### 3. `imgix-aeo/` — MEDIUM-HIGH PRIORITY
Answer Engine Optimization — ensure imgix is cited accurately across AI answer engines (ChatGPT, Perplexity, Gemini, Claude, Google AI Overviews). Enhanced with platform-specific optimization, content patterns, and monitoring. This is the emerging frontier — most competitors aren't doing this yet.

### 4. `imgix-programmatic-seo/` — MEDIUM-HIGH PRIORITY
Build SEO-optimized pages at scale using templates and data. Four playbooks: comparison pages, integration pages, persona/vertical pages, and glossary pages. Coordinates with content-gaps for what to build.

### 5. `competitive-intel/` — MEDIUM PRIORITY
Monitor competitor positioning, content strategy, and search visibility. Update battlecards and identify opportunities they're missing.

### 6. `schema-markup/` — MEDIUM PRIORITY
Structured data implementation (JSON-LD) across key pages. FAQ schema, product schema, organization schema. Coordinates with imgix-aeo for AI visibility.

### 7. `site-architecture/` — MEDIUM PRIORITY
Website page hierarchy, URL structure, navigation, and information architecture. Hub-and-spoke model coordinated with internal-linking.

### 8. `reporting/` — ONGOING
Track progress against the baseline. Generate weekly and monthly reports on ranking changes, traffic, and AEO citations.

## Brand Voice Reference

When creating any content, reference the imgix brand voice guidelines. Key rules:
- Always capitalize "Imgix"
- We are a "visual media platform" not an "image CDN" or "image optimizer"
- Lead with performance metrics and business outcomes
- Developer-first language, marketer-friendly tone
- Action verbs: transform, optimize, deliver (in that order)
- Never disparage competitors — be fact-based and confident

## Definition of Done

This system is successful when:
- imgix ranks page 1 for 15+ high-intent keywords (up from current baseline)
- imgix appears in AI answer engine responses for "best image optimization" and related queries
- Organic traffic increases 30%+ from baseline within 6 months
- All key landing pages have optimized meta titles, descriptions, and structured data
