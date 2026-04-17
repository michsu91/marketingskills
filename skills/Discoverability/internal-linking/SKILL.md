# Internal Linking Strategy

## Goal
Optimize how pages on imgix.com link to each other. Good internal linking helps search engines understand site hierarchy, distributes page authority, and helps users find related content. It's one of the most underrated SEO tactics because it's entirely within your control.

## Connected Tools
- **Webflow MCP** — Read page content to audit current internal links, update content to add new links
- **Claude in Chrome** — Crawl pages and map internal link structure visually
- **Jira MCP** — Create tickets for internal linking improvements

## Why This Matters for imgix

imgix has ~100 pages including blog posts, case studies, solution pages, API docs, and resources. If these pages don't link to each other strategically, Google treats them as isolated islands instead of a connected authority on image optimization.

The key principle: **every page should link to related pages, and your most important pages should receive the most internal links.**

## Tasks

### Task 1: Map Current Internal Link Structure
Crawl key pages and document which pages link to which.

**How to execute:**
1. Start with the homepage — what does it link to?
2. Check each solution page — do they link to relevant case studies? To the API docs? To blog posts?
3. Check case studies — do they link back to the relevant solution page?
4. Check blog posts — do they link to product pages, solution pages, or related blog posts?
5. Document orphan pages (pages that no other page links to)

**Create a link matrix:**
| From Page | Links To | Missing Links (Should Link To) |
|-----------|----------|-------------------------------|
| Homepage | Solutions, Pricing, ... | Should link to top case studies |
| /solutions/ecommerce | ... | Should link to ecommerce case studies (Skims, Culture Kings, Queensmith) |
| Case study - Unsplash | ... | Should link to /solutions/media |

### Task 2: Define Internal Linking Rules

**Hub-and-spoke model:**
- **Hub pages** = Solution pages (/solutions/ecommerce, /solutions/media, etc.)
- **Spoke pages** = Case studies, blog posts, tutorials related to that vertical
- Every spoke should link to its hub. Every hub should link to its spokes.

**Cross-linking rules:**
- Every case study should link to the relevant solution page
- Every solution page should link to 2-3 relevant case studies
- Blog posts should link to relevant product/solution pages within the first 2 paragraphs
- The API page should link to developer-focused solution page
- FAQ answers should link to relevant product pages

**Anchor text rules:**
- Use descriptive anchor text, not "click here" or "learn more"
- Include target keywords in anchor text naturally
- Vary anchor text (don't use the exact same text for every link to the same page)
- Example: link to /solutions/ecommerce with text like "ecommerce image optimization," "product image performance," or "how imgix boosts ecommerce conversions"

### Task 3: Fix Orphan Pages
Any published page that receives zero internal links is an orphan. Search engines have a harder time finding and valuing orphan pages.

**Common orphans to check for:**
- Newer blog posts that haven't been linked from older content
- Case studies that aren't referenced from solution pages
- API reference pages not linked from developer docs
- Resource pages (webinars, infographics) not linked from related content

### Task 4: Add Contextual Internal Links to Existing Content
Go through existing blog posts and case studies and add internal links where natural.

**Process:**
1. Read the content of a blog post or case study
2. Identify mentions of topics that have dedicated pages (ecommerce, AI transforms, real-time processing, etc.)
3. Add links on first mention of each topic
4. Don't overdo it — 3-5 internal links per page is a good range for most content

### Task 5: Create a "Related Content" Strategy
For each solution page and blog post, define what related content should be surfaced.

**Template for solution pages:**
- 2-3 case studies from that vertical
- 2-3 relevant blog posts
- Link to pricing
- Link to free trial / signup

**Template for blog posts:**
- Link to the most relevant solution page
- Link to 1-2 related blog posts
- Link to a relevant case study
- Link to free trial at the end (CTA)

## Execution Cadence
- **One-time:** Map current internal link structure (Task 1)
- **One-time:** Fix orphan pages (Task 3)
- **Ongoing:** Every new piece of content should follow the linking rules before publishing
- **Monthly:** Audit 10 existing pages for internal linking opportunities

## Related Skills
- **Discoverability/site-architecture** — Site architecture defines the hub-and-spoke model
- **Discoverability/imgix-programmatic-seo** — New programmatic pages need internal links
- **Discoverability/content-gaps** — New content needs to be linked into the existing structure
- **Discoverability/technical-seo** — Internal linking affects crawlability and PageRank flow
- **Discoverability/content-refresh** — Refreshed pages may need updated internal links
