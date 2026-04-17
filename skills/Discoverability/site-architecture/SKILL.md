---
name: site-architecture
description: |
  Plan, map, and optimize imgix.com's page hierarchy, navigation, URL structure, and internal linking strategy. Imgix runs on Webflow with ~100 pages across solutions, case studies, blog, resources, and API docs. Also use when the user mentions "sitemap," "site structure," "page hierarchy," "information architecture," "navigation design," "URL structure," "breadcrumbs," "what pages do I need," or "how should I organize the site." NOT for XML sitemaps (that's technical-seo). For structured data, see schema-markup.
metadata:
  version: 2.0.0
---

# Site Architecture for Imgix

You are an information architecture expert. Your goal is to optimize imgix.com's site structure so it's intuitive for developers evaluating image optimization solutions and optimized for search engines and AI answer engines.

## Imgix Context

- **Product:** Visual media platform — real-time image/video processing and CDN delivery
- **Website:** Webflow (Site ID: 6705f4b15aee7ca914fff083)
- **Primary audience:** Developers and engineering teams
- **Secondary audience:** Engineering managers, CTOs evaluating enterprise solutions
- **Motion:** PLG — site structure should guide visitors toward free signup
- **Current state:** ~100 pages including blog, case studies, solutions, product pages, resources, legal
- **Localization:** English (primary) + Japanese (/jp/)

## Connected Tools

- **Webflow MCP** — Read page structure, update navigation, create new pages
- **Claude in Chrome** — Crawl pages visually, audit navigation, inspect URL patterns
- **Jira MCP** — Track architecture tasks (MKTG project)
- **Slack MCP** — Notify Michelle of architecture recommendations

## Global Dependencies

Always load before planning architecture changes:
- **imgix-brand-voice** — Navigation labels and page titles follow brand voice
- **product-marketing-context** — ICP and positioning inform page priority

---

## Current Imgix.com Structure

### Page Hierarchy (Actual)

```
imgix.com (/)
├── Solutions (/solutions)
│   ├── Ecommerce (/solutions/ecommerce)
│   ├── Media (/solutions/media)
│   ├── Real Estate (/solutions/real-estate)
│   └── Automotive (/solutions/automotive)
├── How It Works
│   └── AI Transformation (/how-it-works/ai-transformation)
├── Pricing (/pricing)
├── Customers (/customers)
│   ├── [Case studies by slug]
│   └── Key: Porsche, Unsplash, Skims, Nikkei, Ikyu
├── Blog (/blog)
│   └── [Posts by slug]
├── Resources (/resources)
│   └── [eBooks, whitepapers, webinars]
├── Docs (docs.imgix.com — external)
├── About (/about)
│   └── Careers
├── Contact (/contact)
├── Legal
│   ├── Privacy (/legal/privacy)
│   ├── Terms (/legal/terms)
│   └── Japanese Info Request
└── /jp/ (Japanese locale mirror)
```

### Known Architecture Issues

1. **No comparison pages** — Cloudinary has dedicated /vs/ pages; Imgix has none
2. **No dedicated features page** — Individual capabilities aren't showcased with their own pages
3. **No "How It Works" hub** — Only AI transformation has a dedicated page
4. **Thin resources section** — Limited gated content
5. **No developer-specific landing page** — Despite developers being the primary ICP

---

## Recommended Architecture

### Target Page Hierarchy

```
imgix.com (/)
├── Product (/product) [NEW - Hub]
│   ├── Image Optimization (/product/image-optimization) [NEW]
│   ├── Video Processing (/product/video) [NEW]
│   ├── AI Transforms (/product/ai-transforms) [MOVE from /how-it-works/]
│   ├── CDN Delivery (/product/cdn) [NEW]
│   └── Integrations (/product/integrations) [NEW]
├── Solutions (/solutions)
│   ├── Ecommerce (/solutions/ecommerce)
│   ├── Media & Publishing (/solutions/media)
│   ├── Real Estate (/solutions/real-estate)
│   ├── Automotive (/solutions/automotive)
│   └── User-Generated Content (/solutions/ugc) [NEW]
├── Developers (/developers) [NEW - Hub]
│   ├── Getting Started (/developers/getting-started) [NEW]
│   ├── SDKs & Libraries (/developers/sdks) [NEW]
│   └── Links to docs.imgix.com
├── Pricing (/pricing)
├── Customers (/customers)
│   └── [Case studies by slug]
├── Compare (/compare) [NEW - Hub]
│   ├── Imgix vs Cloudinary (/compare/cloudinary) [NEW]
│   ├── Imgix vs ImageKit (/compare/imagekit) [NEW]
│   ├── Imgix vs Cloudflare Images (/compare/cloudflare-images) [NEW]
│   └── Imgix vs Self-Hosted (/compare/self-hosted) [NEW]
├── Blog (/blog)
│   └── [Posts by slug, organized by topic]
├── Resources (/resources)
│   ├── Guides (/resources/guides) [NEW]
│   ├── Case Studies (→ /customers)
│   └── Tools (/resources/tools) [NEW - Free tools]
├── About (/about)
├── Contact (/contact)
└── Legal (/legal)
```

### Key Changes Explained

**Add /product hub**: Developers exploring Imgix need feature-specific pages to understand capabilities. Each product page targets a keyword cluster (e.g., "image optimization API," "real-time image processing").

**Add /compare hub**: Comparison pages are the highest-intent content Imgix is missing. These pages rank for "[competitor] alternative" keywords and directly address the evaluation stage.

**Add /developers hub**: The primary ICP (developers) needs a dedicated entry point with getting-started guides and SDK links. This also supports SEO for "image optimization for developers" queries.

**Reorganize /how-it-works**: Move AI transformation under /product to create a coherent product hierarchy instead of a standalone section.

---

## URL Structure Rules for Imgix

### Patterns

| Page Type | URL Pattern | Example |
|-----------|------------|---------|
| Product page | `/product/{feature}` | `/product/image-optimization` |
| Solution page | `/solutions/{vertical}` | `/solutions/ecommerce` |
| Case study | `/customers/{slug}` | `/customers/unsplash` |
| Blog post | `/blog/{slug}` | `/blog/avif-image-format` |
| Comparison page | `/compare/{competitor}` | `/compare/cloudinary` |
| Resource/guide | `/resources/guides/{slug}` | `/resources/guides/image-optimization-playbook` |
| Developer page | `/developers/{slug}` | `/developers/getting-started` |
| Legal | `/legal/{page}` | `/legal/privacy` |
| Japanese locale | `/jp/{same-path}` | `/jp/solutions/ecommerce` |

### URL Rules

1. **Lowercase always** — Redirect uppercase to lowercase
2. **Hyphens, not underscores** — `/image-optimization` not `/image_optimization`
3. **Short but descriptive** — `/blog/optimize-images-nextjs` not `/blog/how-to-optimize-images-for-nextjs-applications`
4. **Consistent trailing slash** — Pick one policy and enforce in Webflow
5. **No dates in blog URLs** — `/blog/slug` not `/blog/2026/04/slug`
6. **No IDs or query params for content** — Always use human-readable slugs

---

## Navigation Design for Imgix

### Header Navigation (Recommended)

Target 5-6 items plus CTA:

| Position | Item | Dropdown Contents |
|----------|------|------------------|
| 1 | Product | Image Optimization, Video, AI Transforms, CDN, Integrations |
| 2 | Solutions | Ecommerce, Media, Real Estate, Automotive |
| 3 | Developers | Getting Started, SDKs, Docs (external link) |
| 4 | Pricing | — (direct link) |
| 5 | Customers | — (direct link to case studies) |
| CTA | Start Free | — (signup link, rightmost) |

### Footer Organization

| Column 1: Product | Column 2: Solutions | Column 3: Developers | Column 4: Company |
|-------------------|--------------------|--------------------|-------------------|
| Image Optimization | Ecommerce | Getting Started | About |
| Video Processing | Media & Publishing | SDKs & Libraries | Careers |
| AI Transforms | Real Estate | Documentation | Contact |
| CDN Delivery | Automotive | API Reference | Blog |
| Integrations | | GitHub | |
| Pricing | | Status Page | |

### Breadcrumb Implementation

Every page should have breadcrumbs matching the URL hierarchy:

| URL | Breadcrumb |
|-----|-----------|
| `/product/image-optimization` | Home > Product > Image Optimization |
| `/solutions/ecommerce` | Home > Solutions > Ecommerce |
| `/compare/cloudinary` | Home > Compare > Imgix vs Cloudinary |
| `/blog/avif-format` | Home > Blog > AVIF Image Format |
| `/customers/unsplash` | Home > Customers > Unsplash |

---

## Internal Linking Strategy

### Hub-and-Spoke Model for Imgix

**Hub: /product/image-optimization**
- Spokes: Blog posts about image formats, compression, responsive images
- Cross-links: Solution pages, comparison pages, case studies mentioning image optimization

**Hub: /solutions/ecommerce**
- Spokes: Ecommerce case studies (Skims, etc.), blog posts about product image optimization
- Cross-links: Product pages, pricing, relevant comparison pages

**Hub: /compare/cloudinary**
- Spokes: Blog posts comparing approaches, migration guide
- Cross-links: Product feature pages (as evidence), pricing, case studies

### Cross-Section Linking Rules

| From | Should Link To |
|------|---------------|
| Product pages | Relevant solution pages, case studies, comparison pages |
| Solution pages | 2-3 case studies from that vertical, product pages, pricing |
| Case studies | Relevant solution page, product features used, signup CTA |
| Blog posts | Most relevant product or solution page (in first 2 paragraphs) |
| Comparison pages | Product feature pages as evidence, pricing, case studies |
| Developer pages | Docs, SDKs, getting-started guide, signup |

---

## Migration Plan (Current → Recommended)

### Phase 1: Quick Wins (Week 1-2)

1. Create /compare hub and first comparison page (vs Cloudinary)
2. Add breadcrumbs to all existing pages
3. Audit and fix orphan pages

### Phase 2: Product Hub (Week 3-4)

1. Create /product hub page
2. Create individual product capability pages
3. Move /how-it-works/ai-transformation to /product/ai-transforms (set up 301 redirect)

### Phase 3: Developer Hub (Month 2)

1. Create /developers hub
2. Create getting-started and SDK pages
3. Add developer navigation item

### Redirects

Every URL change needs a 301 redirect. Track all redirects:

| Old URL | New URL | Reason |
|---------|---------|--------|
| `/how-it-works/ai-transformation` | `/product/ai-transforms` | Moved to product hub |

---

## Metrics

| Metric | Target |
|--------|:------:|
| Pages with breadcrumbs | 100% |
| Orphan pages (0 internal links) | 0 |
| Average internal links per page | 5-10 |
| Navigation items | 5-6 + CTA |
| Page depth (clicks from homepage) | ≤3 for all important pages |

---

## Related Skills

- **Discoverability/internal-linking** — Internal link strategy within the architecture
- **Discoverability/schema-markup** — Breadcrumb schema mirrors architecture
- **Discoverability/technical-seo** — URL structure and crawlability
- **Discoverability/content-gaps** — New pages identified by gap analysis fit into architecture
- **Discoverability/imgix-programmatic-seo** — Programmatic pages at scale need architecture planning
- **Conversion/page-cro** — Each page type has CRO patterns
- **Product-Marketing/competitor-alternatives** — Comparison page hub structure
- **imgix-brand-voice** (global) — Navigation labels follow brand voice
