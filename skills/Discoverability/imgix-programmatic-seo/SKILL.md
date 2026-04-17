---
name: imgix-programmatic-seo
description: |
  Build SEO-optimized pages at scale for Imgix using templates and data. Covers comparison pages, integration pages, persona/vertical pages, glossary pages, and alternatives pages. Designed to fill content gaps identified in the Discoverability system and generate high-intent organic traffic.
---

# Programmatic SEO for Imgix

## Goal
Create SEO-optimized pages at scale using templates and data to capture high-intent search traffic. Focus on page types that drive signups and pipeline: comparison pages, integration pages, vertical-specific landing pages, and educational glossary content.

## Connected Tools
- **Webflow MCP** — Create and publish pages directly in the CMS
  - Site ID: `6705f4b15aee7ca914fff083`
  - Use `data_cms_tool` for blog posts (CMS collection items)
  - Use `data_pages_tool` for static landing pages
- **Jira MCP** — Track page creation and review tasks
- **Slack MCP** — Notify Michelle when pages are ready for review
- **HubSpot MCP** — Track which pages drive leads and signups
- **Claude in Chrome** — Research current SERPs for target keywords before creating pages

## Core Principles

### 1. Unique Value Per Page
- Every page must provide value specific to that page
- Not just swapped variables in a template
- Imgix has real differentiators per use case — use them

### 2. Proprietary Data Wins
Imgix's strongest data assets for pSEO:
1. **Proprietary** — 8B+ images/day processing data, performance benchmarks
2. **Product-derived** — Real transformation examples, URL parameter demos
3. **Customer-derived** — Case study metrics (Ikyu: 16ms response time, Nikkei: 37% size reduction)
4. **Public** — Competitor feature comparisons (weakest, but still valuable)

### 3. Quality Over Quantity
Better to have 20 great pages than 200 thin ones. Google's thin content penalties are real and Imgix's brand credibility matters more than traffic volume.

### 4. Clean URL Structure
Use subfolders to consolidate domain authority:
- Good: `imgix.com/compare/imgix-vs-cloudinary/`
- Good: `imgix.com/integrations/shopify/`
- Bad: `compare.imgix.com/cloudinary/`

## Imgix pSEO Playbooks

### Playbook 1: Comparisons (HIGHEST PRIORITY)
**Pattern:** "[imgix] vs [competitor]" and "[competitor] alternatives"
**Why:** Imgix has ZERO comparison content. Cloudinary has dedicated /guides/vs/ pages for every competitor. This is the single biggest content gap.

**Pages to create:**

| Page | Target Keyword | Priority |
|------|---------------|----------|
| imgix vs Cloudinary | "imgix vs cloudinary" | Critical — Week 1 |
| imgix vs Cloudflare Images | "cloudflare images vs imgix" | Critical — Week 1 |
| imgix vs ImageKit | "imgix vs imagekit" | High — Week 2 |
| imgix vs BunnyCDN | "bunnycdn vs imgix" | Medium — Month 1 |
| Cloudinary Alternatives | "cloudinary alternatives" | Critical — Week 2 |
| ImageKit Alternatives | "imagekit alternatives" | Medium — Month 1 |
| Cloudflare Images Alternatives | "cloudflare images alternatives" | Medium — Month 1 |

**Template structure for comparison pages:**
```
H1: imgix vs [Competitor]: An Honest Comparison
H2: Quick Summary (TL;DR table)
H2: Where Imgix Excels
H2: Where [Competitor] Excels
H2: Feature-by-Feature Comparison (detailed table)
H2: Pricing Comparison
H2: Who Should Choose Imgix
H2: Who Should Choose [Competitor]
H2: Migration Guide (if switching from [Competitor])
H2: FAQ (target featured snippets and AI citations)
```

**Content rules for comparison pages:**
- Be honest — acknowledge where competitors are genuinely better
- Lead with the reader's problem, not Imgix features
- Include real numbers: "8B+ images daily," "60,000+ customers," "millisecond delivery"
- Add code examples showing URL-based transformations (Imgix's core differentiator)
- FAQ section with natural-language questions for AEO
- Update quarterly when competitors change pricing or features

### Playbook 2: Integrations
**Pattern:** "imgix + [platform]" or "image optimization for [platform]"
**Why:** Developers search for how to use image tools with their existing stack.

**Pages to create:**

| Page | Target Keyword | Priority |
|------|---------------|----------|
| imgix + Next.js | "imgix nextjs", "next.js image optimization" | High |
| imgix + Shopify | "shopify image optimization", "imgix shopify" | High |
| imgix + React | "imgix react", "react image optimization" | High |
| imgix + Webflow | "webflow image optimization" | Medium |
| imgix + WordPress | "wordpress image cdn" | Medium |
| imgix + Gatsby | "gatsby image optimization" | Medium |
| imgix + Vercel | "vercel image optimization alternative" | Medium |
| imgix + AWS S3 | "s3 image processing", "imgix s3" | High |

**Template structure for integration pages:**
```
H1: How to Use imgix with [Platform]
H2: Why Use imgix with [Platform]
H2: Setup Guide (step-by-step with code examples)
H2: Common Use Cases
H2: Performance Results (before/after with specific metrics)
H2: Configuration Options
H2: FAQ
```

**Content rules for integration pages:**
- Include working code examples (Imgix's URL-based API makes this easy)
- Show before/after performance metrics where possible
- Link to relevant Imgix SDK/library on GitHub
- Reference real customer use cases for that platform

### Playbook 3: Personas/Verticals
**Pattern:** "[image optimization] for [industry/role]"
**Why:** Imgix already has solution pages (/solutions/ecommerce, /solutions/media, etc.) but they're thin and not keyword-optimized.

**Pages to create or expand:**

| Page | Target Keyword | Priority |
|------|---------------|----------|
| Image Optimization for eCommerce | "ecommerce image optimization" | High |
| Image Processing for Real Estate | "real estate listing photo optimization" | Medium |
| Image Delivery for Media & Publishing | "media image delivery at scale" | Medium |
| Image Optimization for Automotive | "automotive inventory image processing" | Medium |
| Image Optimization for Travel | "travel website image optimization" | Low |
| Image CDN for Developers | "image cdn for developers" | High |
| Image API for Marketers | "image optimization no-code" | Medium |

**Template structure for persona pages:**
```
H1: [Industry/Role] Image Optimization with imgix
H2: The Challenge (pain points specific to this vertical)
H2: How imgix Solves It (with specific examples)
H2: Customer Results (case studies from this vertical)
H2: Key Features for [Industry]
H2: Getting Started
H2: FAQ
```

### Playbook 4: Glossary
**Pattern:** "what is [image term]"
**Why:** Establishes Imgix as the authoritative source on image processing concepts. Top-of-funnel awareness with natural internal linking to product pages.

**Terms to define:**

| Term | Target Keyword |
|------|---------------|
| Image CDN | "what is an image cdn" |
| Image Optimization | "what is image optimization" |
| AVIF | "what is avif format" |
| WebP | "what is webp" |
| Responsive Images | "what are responsive images" |
| srcset | "what is srcset" |
| Content Negotiation | "image content negotiation" |
| Lazy Loading | "what is lazy loading images" |
| Core Web Vitals | "core web vitals images" |
| LCP | "largest contentful paint images" |
| BYOS (Bring Your Own Storage) | "byos image processing" |
| Real-Time Image Processing | "real-time image processing" |
| Image Transformation API | "image transformation api" |

**Template structure for glossary pages:**
```
H1: What is [Term]?
[Clear 2-3 sentence definition — optimized for AI extraction]
H2: How [Term] Works
H2: Why [Term] Matters
H2: [Term] Best Practices
H2: How imgix Handles [Term] (natural product tie-in)
H2: Related Terms (internal links to other glossary entries)
```

**URL structure:** `/glossary/[term]/`

## Implementation Framework

### 1. Research Before Creating
For each page:
1. Search the target keyword and note what's ranking
2. Check what format top results use (guide, comparison, tutorial)
3. Identify what's missing from existing results that Imgix can provide
4. Note if AI Overviews appear for this query (coordinate with AEO workstream)

### 2. Internal Linking Architecture
Hub-and-spoke model:
- **Hub pages** = Solution pages (/solutions/ecommerce, etc.) and the glossary index
- **Spoke pages** = Individual comparison, integration, and glossary pages
- Every spoke links to its hub. Every hub links to its spokes.
- Cross-link between related spokes (e.g., "imgix vs Cloudinary" links to "Cloudinary Alternatives")
- Coordinate with the internal-linking workstream

### 3. Indexation Strategy
- Add all new pages to XML sitemap
- Prioritize high-volume patterns first (comparisons, then integrations)
- Noindex very thin variations — only publish pages with genuine unique value
- Use breadcrumbs with structured data

### 4. Brand Voice
Follow Imgix brand voice guidelines:
- Lead with the reader's problem, not Imgix features
- Developer tone: direct, no fluff, show don't tell
- Use specific numbers: "8B+ images daily," "60,000+ customers," "millisecond delivery"
- Include code examples where relevant (URL parameter examples are Imgix's strength)
- Always capitalize "Imgix" with a capital I

## Quality Checks

### Pre-Publish Checklist
- [ ] Each page provides unique value beyond variable swapping
- [ ] Answers real search intent for the target keyword
- [ ] Includes Imgix-specific data, examples, or code
- [ ] Unique title tag (keyword first, "| Imgix" last, under 60 chars)
- [ ] Unique meta description (value prop + proof point, 120-160 chars)
- [ ] Proper H1 > H2 > H3 hierarchy
- [ ] FAQ schema (JSON-LD) if FAQ section exists
- [ ] Internal links to related hub and spoke pages
- [ ] In XML sitemap
- [ ] Reviewed by Michelle before publishing

### Post-Publish Monitoring
Track per page: indexation, ranking for target keyword, organic traffic, signups attributed (HubSpot)
Watch for: thin content warnings, ranking drops, keyword cannibalization with existing pages

## Execution Cadence
- **Weeks 1-2:** Comparison pages (imgix vs Cloudinary, vs Cloudflare Images, vs ImageKit) + Cloudinary Alternatives
- **Weeks 3-4:** Top integration pages (Next.js, Shopify, React, S3)
- **Month 2:** Remaining comparison and alternatives pages + persona pages
- **Month 3:** Glossary pages (batch of 5-10) + remaining integration pages
- **Ongoing:** Update comparison pages quarterly, add new integrations as partnerships develop

## Related Skills
- **imgix-content-gaps** — Identifies what pages to create (this skill executes the creation)
- **imgix-aeo** — AEO optimization for all new pages
- **imgix-internal-linking** — Hub-and-spoke linking for new pages
- **imgix-competitive-intel** — Keeps comparison pages accurate
- **imgix-technical-seo** — Meta tags and technical optimization
