# Content Gap Analysis & Creation

## Goal
Identify keywords and topics where imgix should rank but doesn't, and create content that fills those gaps. Focus on high-intent terms that drive signups and pipeline.

## Connected Tools
- **Webflow MCP** — Create new pages or blog posts directly in the CMS
  - Site ID: `6705f4b15aee7ca914fff083`
  - Use `data_cms_tool` for blog posts (CMS collection items)
  - Use `data_pages_tool` for static landing pages
- **Jira MCP** — Create content tickets with briefs for Michelle's review
- **Slack MCP** — Notify when content briefs are ready for review
- **HubSpot MCP** — Check which existing content drives the most leads to inform priorities
- **Claude in Chrome** — Research competitor content, check current SERPs for target keywords

## Priority Content Gaps (From Baseline)

### Gap 1: Comparison Pages (CRITICAL — Week 1)
imgix has ZERO comparison content. Cloudinary has dedicated pages for every competitor. This is the single biggest content gap.

**Pages to create:**
1. **"imgix vs Cloudinary"** — Target: developers evaluating options
   - Key angle: imgix is faster, simpler, no vendor lock-in (BYOS — bring your own storage)
   - Include: feature table, pricing comparison, migration guide, use case recommendations
   - Proof points: 8B+ images/day, customer names, speed benchmarks

2. **"imgix vs Cloudflare Images"** — Target: teams already on Cloudflare
   - Key angle: imgix offers 100x more transformation capabilities and AI features
   - Include: transformation comparison table, real examples of what imgix can do that CF can't

3. **"imgix vs ImageKit"** — Target: budget-conscious teams
   - Key angle: imgix is enterprise-proven at massive scale (60,000+ customers)
   - Include: scale comparison, enterprise features, customer logos

**Content structure for all comparison pages:**
```
H1: imgix vs [Competitor]: An Honest Comparison
H2: Quick Summary (TL;DR table)
H2: Where imgix Excels
H2: Where [Competitor] Excels
H2: Feature-by-Feature Comparison (detailed table)
H2: Pricing Comparison
H2: Who Should Choose imgix
H2: Who Should Choose [Competitor]
H2: Migration Guide (if switching from [Competitor])
H2: FAQ (target featured snippets and AI citations)
```

### Gap 2: "Alternatives to X" Pages (Week 2)
When developers search "Cloudinary alternatives," imgix should appear.

**Pages to create:**
1. "Cloudinary Alternatives" — Position imgix as the top alternative for teams who want speed + simplicity
2. "ImageKit Alternatives" — Position imgix for teams outgrowing ImageKit
3. "Cloudflare Images Alternatives" — Position imgix for teams needing more transformation power

### Gap 3: Core Capability Landing Pages (Week 2-3)
imgix doesn't have dedicated pages for its most differentiating capabilities.

**Pages to create:**
1. **"Real-Time Image Processing"** — This is imgix's core capability and there's no dedicated page
   - Target keywords: "real-time image processing API," "on-the-fly image processing"
2. **"Image Optimization API"** — Cloudinary dominates this term
   - Target keywords: "image optimization API," "image optimization platform"
3. **"AVIF and WebP Conversion"** — Format conversion is a hot topic in 2026
   - Target keywords: "automatic AVIF conversion," "WebP image optimization"

### Gap 4: Developer Tutorial Content (Month 2)
Create search-optimized tutorials that developers actually find useful.

**Topics:**
- "How to optimize images for Next.js with imgix"
- "Image optimization for Shopify stores"
- "Lazy loading images with imgix"
- "Responsive images with srcset and imgix"
- "Migrating from Cloudinary to imgix"

### Gap 5: Vertical-Specific SEO Content (Month 2-3)
Create content targeting vertical-specific searches.

**Topics:**
- "Image optimization for ecommerce product pages" (link to /solutions/ecommerce)
- "Real estate listing photo optimization" (link to /solutions/real-estate)
- "Automotive inventory image processing" (link to /solutions/automotive)
- "Media and publishing image delivery at scale" (link to /solutions/media)

## Content Creation Process

### For each piece of content:
1. **Research:** Search current SERPs for the target keyword. Note what's ranking, what format they use, what's missing.
2. **Brief:** Create a content brief with target keyword, secondary keywords, recommended word count, content structure, and key points to hit.
3. **Draft:** Write the content following imgix brand voice (see MANIFEST.md for reference).
4. **SEO optimization:** Ensure title tag, meta description, H1, and first paragraph all include the primary keyword naturally.
5. **Review:** Create a Jira ticket with the draft for Michelle's review. Post to Slack.
6. **Publish:** Once approved, create the page in Webflow via MCP.

### Brand Voice Reminders for Content
- Lead with the reader's problem, not imgix's features
- Use specific numbers: "8B+ images daily," "60,000+ customers," "millisecond delivery"
- Developer tone: direct, no fluff, show don't tell
- Include code examples where relevant (URL parameter examples are imgix's strength)
- Always lowercase "imgix"

## Measurement
- Track new page indexation via Google Search Console (manual check)
- Monitor ranking for target keywords (weekly search spot-checks)
- Track clicks from new content to signup (HubSpot attribution)

## Related Skills
- **Discoverability/imgix-programmatic-seo** — Programmatic pages fill content gaps at scale
- **Content/content-strategy** — Content strategy decides how to fill identified gaps
- **Content/copywriting** — Copywriting creates the content to fill gaps
- **Discoverability/competitive-intel** — Competitor analysis reveals where gaps exist
- **Discoverability/imgix-aeo** — AEO requirements inform which gaps to prioritize
- **Discoverability/reporting** — Track whether filled gaps improve rankings
