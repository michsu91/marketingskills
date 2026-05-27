# Imgix Discoverability System

**Owner:** Michelle Su
**Created:** March 23, 2026
**Last Updated:** May 27, 2026

## What This Is

This folder is a self-executing system for improving imgix's discoverability — across both traditional search engines (SEO) and AI answer engines (AEO). Any Claude session that opens this folder should read this manifest first, check the STATUS.md in each subfolder, and pick up the highest-priority incomplete work.

## How to Use This Folder

**When to invoke this folder:** You want to improve how Imgix shows up in search engines and AI answer engines, audit imgix.com for technical SEO issues, find new keyword opportunities, or run the weekly Discoverability pulse. This is the most continuous discipline in the repo and should be invoked at least weekly.

**Context to bring:**
- The activity (audit, content brief, refresh, monitoring, fix)
- Specific target if any (a keyword, a page, a competitor, a Core Web Vital)
- Current data if iterating (ranking position, traffic trend, citation status)
- Webflow access and Jira (MKTG) access confirmed

**How the sub-skills fit together:**
- This folder is **hybrid.** Some sub-skills run standalone (technical-seo audits, content-refresh, technical-performance, reporting). Others chain.
- The main chain: content-gaps identifies a keyword opportunity, then either imgix-programmatic-seo (for scalable templated pages) or hand-off to Content/copywriting (for one-off long-form), then schema-markup to optimize for AEO.
- reporting supports every other skill by tracking impact over time.
- The Tier 4 sub-skills (distribution, backlinks, international-seo) are specialized. Don't try to do all 14 every week.

**Typical prompts:**
- "Run a weekly Discoverability pulse. Check ranking changes, AEO citation status, and any technical issues on imgix.com."
- "Audit imgix.com for technical SEO issues that are hurting crawlability or rankings."
- "Find content gaps where Cloudinary ranks page 1 but Imgix doesn't. Prioritize by intent and traffic potential."
- "Refresh the 10 oldest blog posts. Flag outdated product mentions and propose updates."
- "Add FAQ schema to the top 5 traffic pages and measure AEO impact at 4 weeks."

**Output to expect:** Audit reports with prioritized fixes, content briefs (often handed to Content), Jira tickets for engineering fixes, ranking and AEO citation summaries, schema markup JSON, refreshed copy diffs.

**When NOT to use this folder (and where to go instead):**
- Writing the content itself → Content/copywriting after a brief is produced here
- Paid traffic and channel diversification → Acquisition
- Brand voice and messaging → imgix-brand-voice (global), product-marketing-context (global)
- Sales-facing competitive battle cards → Product-Marketing/competitor-alternatives (public comparison pages live here; sales battle cards live there)

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
Fix on-site technical SEO issues that are hurting crawlability and rankings. Quick wins with outsized impact.

### 2. `content-gaps/` — HIGH PRIORITY
Identify and fill keyword gaps where Imgix should rank but doesn't. Create content briefs and draft content targeting high-intent terms.

### 3. `technical-performance/` — HIGH PRIORITY
Monitor and improve imgix.com's Core Web Vitals (LCP, INP, CLS). Brand-critical for an image optimization platform: a slow marketing site undermines the product narrative.

### 4. `imgix-aeo/` — MEDIUM-HIGH PRIORITY
Answer Engine Optimization. Ensure Imgix is cited accurately across AI answer engines (ChatGPT, Perplexity, Gemini, Claude, Google AI Overviews) with platform-specific optimization, content patterns, and monitoring. The emerging frontier where most competitors aren't yet playing.

### 5. `imgix-programmatic-seo/` — MEDIUM-HIGH PRIORITY
Build SEO-optimized pages at scale using templates and data. Five playbooks: comparison, integration, persona/vertical, glossary, and alternatives pages. Coordinates with content-gaps on what to build.

### 6. `content-refresh/` — MEDIUM-HIGH PRIORITY
Audit and update existing content as products change or rankings decay. Prevents loss of ranking on terms Imgix already wins.

### 7. `schema-markup/` — MEDIUM-HIGH PRIORITY
Structured data implementation (JSON-LD) across key pages. Organization, FAQ, HowTo, Article, BreadcrumbList. Supports rich results and AEO citation accuracy.

### 8. `site-architecture/` — MEDIUM PRIORITY
Page hierarchy, URL structure, navigation, and information architecture. Hub-and-spoke model coordinated with internal-linking.

### 9. `internal-linking/` — MEDIUM PRIORITY
Fix orphan pages, audit link distribution, reinforce the "one platform" narrative through linking. Tactical execution of site-architecture decisions.

### 10. `competitive-intel/` — MEDIUM PRIORITY
Monitor competitor positioning (Cloudinary, ImageKit, Cloudflare Images, BunnyCDN), content strategy, and search visibility. Update battlecards and identify opportunities competitors are missing.

### 11. `reporting/` — MEDIUM PRIORITY
Track progress against the baseline. Generate weekly pulses, monthly reports, and quarterly re-measurements on ranking changes, traffic, and AEO citations. Supports every other skill.

### 12. `distribution/` — LOWER PRIORITY
Distribute Imgix content across owned, earned, and paid channels to drive initial engagement and support SEO. Owned/earned/paid playbook for new content.

### 13. `backlinks/` — LOWER PRIORITY
Build domain authority and referral traffic by earning high-quality backlinks. Competitor backlink gap analysis and outreach. Slow compound build that requires consistent outreach capacity.

### 14. `international-seo/` — LOWER PRIORITY
Japanese locale optimization, hreflang tags, and `/jp/` pages. Defer unless Imgix is actively investing in the Japan market.

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
