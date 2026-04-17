# Technical SEO Fixes

## Goal
Fix on-site technical SEO issues on imgix.com that are hurting crawlability, indexation, and rankings. These are quick wins with outsized impact.

## Connected Tools
- **Webflow MCP** — Direct access to read and update page metadata, SEO titles, descriptions, and Open Graph tags
  - Site ID: `6705f4b15aee7ca914fff083`
  - Use `data_pages_tool` to list pages, get metadata, and update SEO settings
  - Use `data_sites_tool` to publish changes after updates
- **Jira MCP** — Create tickets for changes that need Michelle's review before publishing
- **Slack MCP** — Notify Michelle when fixes are applied or when review is needed

## Tasks

### Task 1: Fix Broken SEO Metadata — RESOLVED
~~Several pages appeared to have template syntax in SEO titles.~~
**Resolution (March 23, 2026):** These are all CMS collection templates — the `{{wf...}}` syntax is by design and gets replaced with real content when Webflow renders the page. No action needed.

### Task 2: Fix Mismatched SEO Descriptions
- "demo dev" page has description "Press releases and mentions of Imgix in the press." — wrong page
- "formtest" has no description at all
- Several internal pages have generic or missing descriptions

**How to fix:**
1. Identify all pages where SEO description doesn't match the page content
2. Either fix the description or mark the page as draft if it's not meant to be public
3. Update via Webflow MCP

### Task 3: Noindex Internal/Utility Pages
These pages should not be indexed by search engines:
- NPS score pages (11 pages: nps-score-0 through nps-score-10) — thin content
- "demo dev" — test page
- "formtest" — test page
- "Classic Gear" — internal swag page
- "Imgix Beta Testing Interest Form" — internal
- Feedback submission page
- Various "Content Request" gated pages that duplicate "Content" pages

**How to fix:**
Note — Webflow's page settings may not expose noindex directly via API. Options:
1. Set these pages to `draft: true` if they shouldn't be public at all
2. Or use Webflow's custom code injection to add `<meta name="robots" content="noindex">` via the page's custom head code
3. Create a Jira ticket for Michelle to review which approach she prefers

### Task 4: Audit and Improve Key Landing Page SEO
Priority pages that need SEO optimization:

| Page | Current SEO Title | Recommended SEO Title |
|------|------------------|----------------------|
| Home | (check current) | Imgix — The Visual Media Platform for Performance |
| /solutions/ecommerce | Imgix Solutions for eCommerce Success | eCommerce Image Optimization — Boost Conversions \| Imgix |
| /solutions/media | Imgix Solutions for Media Platforms | Media Image Optimization at Scale \| Imgix |
| /solutions/real-estate | Imgix Solutions for Real Estate Professionals | Real Estate Image Processing & Optimization \| Imgix |
| /solutions/automotive | Imgix Solutions for Automotive Visuals | Automotive Image Processing & AI Enhancement \| Imgix |
| /how-it-works/ai-transformation | Intelligently Transform Your Visuals with Imgix | AI Image Transformation — Edit, Enhance, Deliver \| Imgix |

**Principles for SEO titles:**
- Put the keyword first, brand last
- Include the primary action or benefit
- Keep under 60 characters
- Use pipe separator before "Imgix"

**Principles for SEO descriptions:**
- Start with the value prop or pain point
- Include primary and secondary keywords naturally
- Include a metric or proof point where possible (e.g., "8B+ images daily")
- End with implicit CTA
- Keep between 120-160 characters

### Task 5: Check and Fix Open Graph Tags
For every page where SEO metadata is updated, also verify Open Graph tags are set correctly. Many pages have `titleCopied: true` and `descriptionCopied: true` which means OG inherits from SEO — this is fine as long as the SEO data is correct.

## Execution Order
1. Task 1 (broken templates) — immediate, highest impact
2. Task 3 (noindex utility pages) — immediate, prevents thin content penalties
3. Task 2 (mismatched descriptions) — same session as Task 1
4. Task 4 (landing page optimization) — next session, requires more thought
5. Task 5 (OG tags) — verify alongside Task 4

## Quality Check
After making changes:
1. Pull the updated page metadata to verify changes took effect
2. Spot-check 3-5 pages to make sure nothing broke
3. Post a summary to Slack with what was changed
4. Create a Jira ticket with the full change log

## Related Skills
- **Discoverability/schema-markup** — Structured data is a technical SEO element
- **Discoverability/site-architecture** — URL structure and crawl paths
- **Discoverability/technical-performance** — Core Web Vitals and page speed
- **Discoverability/internal-linking** — Crawlability depends on internal link structure
- **Discoverability/imgix-aeo** — Technical foundations enable AEO visibility
- **Discoverability/reporting** — Technical health metrics tracked over time
