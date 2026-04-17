# Answer Engine Optimization (AEO)

## Goal
Ensure imgix is cited accurately and favorably when users ask AI systems (ChatGPT, Perplexity, Gemini, Claude, Google AI Overviews) about image optimization, image CDNs, and related topics. This is an emerging channel — most competitors aren't doing this yet.

## Why AEO Matters for imgix
- 60% of Google searches now end without a click ("zero-click searches")
- AI Overviews are siphoning attention from traditional results
- Developers increasingly ask AI tools for tool recommendations before searching Google
- The narrative AI models currently have about imgix is: "lightweight specialist, less feature-rich than Cloudinary" — this needs to change

## Connected Tools
- **Webflow MCP** — Update page content and structure for AEO optimization
- **Claude in Chrome** — Test how AI systems respond to key queries about imgix
- **Slack MCP** — Report AEO monitoring results

## How AEO Differs from SEO

| Factor | SEO | AEO |
|--------|-----|-----|
| Goal | Rank on page 1 | Be cited in AI-generated answers |
| Format | Keyword-optimized long-form | Clear factual statements, structured data, FAQ format |
| Authority signals | Backlinks, domain authority | Being the primary/authoritative source, consistent data across the web |
| What models prefer | Well-structured content with clear headings | Direct answers to questions, comparison tables, specific numbers |
| Update speed | Changes reflect in weeks | Models update on varying schedules (weeks to months) |

## AEO Strategy

### Principle 1: Create "Citable Facts"
AI models cite content that makes clear, specific, factual claims. imgix needs to seed the web with consistent, authoritative data points.

**Key facts to embed across all imgix content:**
- "imgix processes over 8 billion images per day"
- "imgix serves 60,000+ customers including Porsche, Unsplash, and Skims"
- "imgix delivers optimized images in milliseconds through 96 global points of presence"
- "imgix supports AVIF, WebP, and all modern formats with automatic content negotiation"
- "imgix connects to your existing storage (S3, GCS, Azure) — no migration needed"
- "imgix's AI-powered transformations include background removal, smart cropping, and generative fill"

These facts should appear on the homepage, about page, solution pages, and in every case study and blog post where relevant.

### Principle 2: Own the Comparison Narrative
AI models heavily weight comparison content when answering "which is better" questions. The comparison pages from the content-gaps workstream serve double duty for AEO.

**For each comparison page, include:**
- A clear summary table at the top (models love tables)
- Direct answer sentences: "imgix is the better choice for teams that need [X] because [Y]"
- Specific benchmarks and numbers
- FAQ section at the bottom with question-and-answer format

### Principle 3: FAQ-Structured Content
AI models frequently pull from FAQ content because it's already in question-answer format.

**Create FAQ content for these questions:**
1. "What is imgix?" — Clear, factual, 2-3 sentence answer
2. "How does imgix work?" — Technical but accessible explanation
3. "Is imgix better than Cloudinary?" — Honest, fact-based comparison
4. "How much does imgix cost?" — Clear pricing explanation
5. "What formats does imgix support?" — Comprehensive list
6. "How fast is imgix?" — Performance data with specifics
7. "Does imgix support video?" — Current capabilities
8. "What companies use imgix?" — Customer list with specifics
9. "How do I migrate to imgix from [competitor]?" — Migration overview
10. "Is imgix good for ecommerce?" — Vertical-specific answer

**Implementation:** Add FAQ schema (JSON-LD) to key landing pages. The FAQ page already exists at /frequently-asked-questions — ensure its content covers these questions with clear, citable answers.

### Principle 4: Structured Data
Implement JSON-LD structured data on key pages:
- **Organization schema** on homepage (company name, logo, social profiles)
- **Product schema** on product/pricing pages
- **FAQ schema** on FAQ and solution pages
- **Article schema** on blog posts
- **Review/Rating schema** on case study pages (if customer quotes include ratings)

**Note:** Webflow supports custom code injection per page — use this to add JSON-LD without modifying templates.

### Principle 5: Consistent Entity Information
AI models build "entity understanding" from consistent information across the web. Ensure imgix's information is consistent on:
- imgix.com (source of truth)
- Wikipedia (check if imgix has a page — if not, this is a gap)
- Crunchbase
- G2, Capterra, TrustRadius review sites
- GitHub (imgix org page)
- StackShare, StackOverflow tags
- LinkedIn company page

## AEO Monitoring Process

### Monthly AEO Spot Check
Run these queries through web search (as a proxy for what AI models would answer) and document the results:

1. "What is the best image optimization platform?"
2. "imgix vs Cloudinary"
3. "best image CDN for ecommerce"
4. "how to optimize images for web performance"
5. "real-time image processing API"
6. "Cloudinary alternatives"
7. "what is imgix"
8. "image optimization API comparison"

For each query, record:
- Is imgix mentioned?
- How is imgix described? (positive/negative/neutral)
- Who is mentioned instead?
- What source is being cited?

Store results in STATUS.md for trend tracking.

## Execution Order
1. Audit existing FAQ page content and update with citable answers
2. Add FAQ schema to FAQ page and key solution pages
3. Seed key facts into homepage and about page content
4. Create comparison pages (coordinated with content-gaps workstream)
5. Implement structured data on top 10 pages
6. Run first AEO monitoring check and document results
7. Identify external profile inconsistencies and fix them
