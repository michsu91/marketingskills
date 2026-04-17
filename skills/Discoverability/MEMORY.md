# Claude Memory — imgix Discoverability

**Purpose:** This is a living reference document that Claude maintains for itself. It captures context, learnings, decisions, and institutional knowledge that persist across sessions. Claude should read this file at the start of every session and update it at the end of any session where meaningful new information was learned.

**Rules for updating this file:**
- Replace outdated information in place — don't append endlessly
- Keep each section concise (aim for the minimum context a new session would need)
- Date-stamp any significant changes
- Remove information that is no longer relevant
- This file should never exceed ~200 lines

---

## About Michelle

- **Role:** Growth marketing at imgix
- **Email:** michelle.su@imgix.com
- **Working style:** Wants to understand systems before running them. Values transparency about what Claude can and can't do. Asks good clarifying questions — don't rush past them.
- **Key collaborator:** Glenn — advises Michelle on building AI-powered systems and workflows. His "folder as instruction set" concept is the foundation of this system.
- **Tools she uses daily:** Webflow (site management), Jira (MKTG project), Slack, HubSpot, Google Drive, Google Calendar

## About imgix

- **What it is:** Visual media platform — real-time image and video processing, optimization, and delivery via CDN
- **How to refer to it:** Always lowercase "imgix" — never "Imgix" mid-sentence, never "IMGIX"
- **Scale:** 8B+ images processed daily, 60,000+ customers
- **Key customers:** Porsche, Unsplash, Skims, Eventbrite, ExpressVPN, TV Tokyo, Nikkei
- **How it works:** Connects to customer's existing storage (S3, GCS, Azure), processes images on-the-fly via URL parameters, delivers via global CDN
- **Differentiators vs competitors:** Speed (millisecond delivery), simplicity (URL-based transforms), no vendor lock-in (BYOS), AI-powered transformations
- **Category framing:** "Visual media platform" — NOT "image CDN" or "image optimizer"

## Competitive Landscape (Last updated: March 23, 2026)

- **Cloudinary:** Primary competitor. Dominates search. Owns comparison narrative with dedicated /vs/ pages. Positions as "comprehensive media experience platform." More features but more complex and expensive at scale.
- **Cloudflare Images:** Leverages massive parent brand domain authority. Basic transformations only. No AI features. Cheap but limited.
- **ImageKit:** Growing, developer-focused, competitive pricing. Not proven at imgix's scale.
- **BunnyCDN:** Winning "best value" positioning in 2026 listicles. Different market segment but stealing developer mindshare.

## Current SEO/AEO State (Last updated: March 23, 2026)

**Biggest problem:** Cloudinary controls the comparison narrative. They have "cloudinary-vs-imgix" pages; imgix has zero comparison content.

**What AI models currently say about imgix:** "Lightweight specialist, less feature-rich than Cloudinary." This framing is wrong and needs to change.

**What we've done so far:**
- Optimized SEO titles + descriptions on 8 key landing pages (keyword-first, brand-last) — published March 23, 2026
- Created Jira ticket MKTG-102 for manual noindex/draft of 13 test/NPS pages
- Established baseline keyword visibility and AEO snapshot

**What hasn't been done yet:**
- No comparison pages created (this is #1 priority)
- No structured data / JSON-LD on any pages
- No FAQ schema implementation
- No AEO-optimized content
- No competitive battlecards formalized

## Webflow Site Details

- **Site ID:** 6705f4b15aee7ca914fff083
- **Domains:** imgix.com, www.imgix.com, blog.imgix.com
- **Locales:** English (primary), Japanese (secondary)
- **Total pages:** ~100 (includes templates and drafts)
- **CMS collections:** Blog, FAQs, FAQ Categories, Events, API Reference, Credit Consumption Values
- **Important:** CMS template pages show `{{wf...}}` syntax in API responses — this is normal Webflow behavior, not broken
- **API limitation:** Cannot change draft status on published pages via API — must be done in Webflow Designer

## Jira

- **Project:** MKTG (Marketing Team)
- **Cloud ID:** imgix.atlassian.net (resolves to e007f0b6-3c97-4dc2-83c0-c6b01b25ed52)
- **Issue types available:** Task, Sub-task, Epic
- **Open tickets from this system:**
  - MKTG-102: SEO cleanup — noindex/draft 13 pages (test + NPS)

## Key Decisions Made

- **March 23, 2026:** Framing this as "Discoverability" (not just SEO) to cover both traditional search and AI answer engines
- **March 23, 2026:** Using Glenn's "stateful folders with living manifest" pattern — folders contain SKILL.md (what to do) and STATUS.md (what's been done)
- **March 23, 2026:** CMS template SEO titles are NOT broken — they're Webflow dynamic content working as intended. Don't try to fix them.
- **March 23, 2026:** Brand voice approach — keyword-first SEO titles, proof points in descriptions, developer-first tone

## Lessons Learned

- Webflow API rate limits are strict — batch page updates carefully, wait between calls, especially before publishing
- Webflow API returns pre-update state in responses — always verify with a separate GET call
- Draft status cannot be changed via API on published pages — flag these for manual action via Jira
- The "imgix vs Cloudinary" comparison content gap is the single highest-leverage content to create — Cloudinary literally owns the narrative right now
