# imgix Discoverability Baseline

**Captured:** March 23, 2026
**Method:** Web search visibility checks, AI answer engine spot checks, Webflow site audit (100 pages)

---

## SEO Baseline

### Current Search Visibility by Keyword Category

#### Category 1: Core Product Terms
| Keyword | imgix Visibility | Who's Ranking Instead | Notes |
|---------|-----------------|----------------------|-------|
| "image CDN" | imgix.com/solutions/cdn-delivery ranks | BunnyCDN, Cloudflare, ImageKit dominate listicles | imgix has a dedicated page but listicle sites outrank |
| "best image CDN" | Not in top results | theimagecdn.com, theguidex.com, scaleflex.com | Dominated by comparison/listicle sites |
| "best image CDN 2026" | Mentioned in some listicles | BunnyCDN, ImageKit, Cloudflare recommended first | imgix often listed but rarely #1 recommendation |
| "image optimization API" | imgix not prominent | Cloudinary, LetsEnhance, Abstract API | Cloudinary owns this category |
| "real-time image processing" | imgix not in top results | Cloudinary, ImageKit, Uploadcare, Google Cloud Vision | Major gap — this is imgix's core differentiator |

#### Category 2: Comparison/Decision Terms
| Keyword | imgix Visibility | Who's Ranking Instead | Notes |
|---------|-----------------|----------------------|-------|
| "imgix vs Cloudinary" | Cloudinary owns their comparison page | cloudinary.com/guides/vs/cloudinary-vs-imgix | Cloudinary controls the narrative on their own domain |
| "imgix alternatives" | imgix absent | programminginsider.com, gumlet.com, aijourn.com | Third parties frame imgix as the thing to replace |
| "Cloudinary vs imgix" | Same as above | cloudinary.com, bytescale.com, stackshare.io | imgix has no counter-content |

#### Category 3: Use Case Terms
| Keyword | imgix Visibility | Who's Ranking Instead | Notes |
|---------|-----------------|----------------------|-------|
| "ecommerce image optimization" | imgix has /solutions/ecommerce | Cloudinary, Shopify docs, generic listicles | Page exists but unclear if ranking |
| "image optimization for web performance" | imgix blog content exists | Cloudinary guides, web.dev, various blogs | Content exists but competing poorly |

### Key SEO Findings

**Strengths:**
- imgix.com has strong domain with custom domains properly configured (imgix.com, www.imgix.com, blog.imgix.com)
- Extensive case study library (20+ case studies with good SEO metadata)
- Dedicated solution pages for verticals (ecommerce, media, automotive, real estate, agencies)
- Japanese localization in place (secondary locale)

**Critical Gaps:**
1. **No comparison/vs content.** Cloudinary has pages like "cloudinary-vs-imgix" — imgix has nothing equivalent. This means Cloudinary controls the narrative for every comparison search.
2. **No "alternatives to X" content.** When people search "Cloudinary alternatives" or "ImageKit alternatives," imgix doesn't show up with its own content.
3. **Missing core keyword pages.** No dedicated page targeting "real-time image processing" despite it being imgix's core capability.
4. **Template SEO titles leaking.** Multiple pages show raw Webflow template syntax in SEO titles (e.g., `{{wf {"path":"name","type":"PlainText"} }}`) — this is a technical SEO problem.
5. **Test/internal pages published.** Pages like "demo dev," "formtest," and "Ecommerce Copy" are live with poor or missing SEO metadata.
6. **NPS pages indexed.** 11 NPS score pages (nps-score-0 through nps-score-10) are likely being indexed with thin content.
7. **Inconsistent SEO descriptions.** "demo dev" page has the description "Press releases and mentions of Imgix in the press" — clearly wrong metadata.
8. **No structured data detected** in page metadata (FAQ schema, product schema, etc. would need manual verification via site inspection).

### Webflow Site Technical Summary
- **Total pages:** 100 (includes drafts and templates)
- **Published pages with SEO issues:** ~15-20 pages with missing, incorrect, or template-broken SEO metadata
- **Localization:** English (primary) + Japanese (secondary)
- **Last published:** March 20, 2026

---

## AEO Baseline (Answer Engine Optimization)

### AI Answer Engine Spot Checks

| Query | imgix Mentioned? | Who Gets Cited Instead | Source |
|-------|-----------------|----------------------|--------|
| "best image optimization platform" | NO | Cloudinary, TinyPNG, Squoosh, Optimole, ShortPixel, ImageOptim | Web search proxy for AI answers |
| "best image CDN 2026" | Sometimes (in listicles) | BunnyCDN, ImageKit, Cloudflare recommended first | Listicle aggregation |
| "imgix vs Cloudinary which is better" | Yes (but Cloudinary framed as winner) | Cloudinary positioned as "more complete," imgix as "lightweight specialist" | Third-party comparison sites |
| "real-time image processing API" | NO | Cloudinary, ImageKit, Uploadcare, Google Cloud Vision | General search results |
| "image optimization for ecommerce" | NOT prominent | Cloudinary, Shopify native tools, various plugins | Category searches |

### Key AEO Findings

**Critical insight:** imgix is being described by AI systems as a "lightweight specialist" and a "focused" alternative to Cloudinary. The framing is: Cloudinary = full-featured, imgix = niche. This is the narrative that AI models are absorbing from the web, and it will persist until imgix creates content that reframes this.

**What AI models are saying about imgix (based on web content they train on):**
- "Choose imgix if you have existing storage and need fast real-time processing"
- "imgix is a lightweight specialist" vs Cloudinary as "full-featured platform"
- "imgix doesn't store images — you connect your existing storage"
- "imgix felt constrained" as teams need more than just image processing

**What AI models should be saying:**
- "imgix is the visual media platform trusted by Porsche, Unsplash, and 60,000+ customers"
- "imgix processes 8B+ images daily with AI-powered transformations"
- "imgix delivers the fastest image processing with the simplest integration"

**AEO Opportunity:** Most competitors are not optimizing for AEO yet. imgix can gain first-mover advantage by creating content specifically structured for AI citation — clear factual statements, structured comparisons, FAQ-formatted content, and authoritative data points.

---

## Competitor Visibility Summary

| Competitor | Search Presence | AEO Presence | Content Strategy |
|-----------|----------------|-------------|-----------------|
| **Cloudinary** | DOMINANT — owns comparison pages, guides, extensive SEO content | HIGH — frequently cited as the "comprehensive" option | Massive content library with vs/ pages, guides, tutorials |
| **ImageKit** | STRONG — shows up in listicles, has good developer content | MEDIUM — mentioned as budget alternative | Developer-focused blog, comparison content |
| **Cloudflare Images** | STRONG — benefits from Cloudflare's massive domain authority | MEDIUM-HIGH — bundled into Cloudflare recommendations | Leverages parent brand's content ecosystem |
| **BunnyCDN** | GROWING — winning "best value" positioning in 2026 listicles | MEDIUM — recommended for value/simplicity | Community-driven, value-focused messaging |
| **Uploadcare** | MODERATE — owns some comparison and best-practices content | LOW-MEDIUM | Focused blog content on specific use cases |

---

## Priority Actions (Derived from Baseline)

### Immediate (Week 1-2)
1. Fix broken SEO metadata — template syntax in titles, wrong descriptions, test pages
2. Noindex NPS pages, test pages, and internal forms
3. Create imgix vs. Cloudinary comparison page
4. Create imgix vs. Cloudflare Images comparison page

### Short-term (Month 1)
5. Create "Cloudinary alternatives" and "ImageKit alternatives" content
6. Build dedicated "real-time image processing" landing page
7. Add FAQ schema to key landing pages
8. Create AEO-optimized content with clear factual statements about imgix's capabilities

### Medium-term (Month 2-3)
9. Build keyword-targeted blog content for gap terms
10. Create developer-focused tutorials optimized for search
11. Implement structured data across solution pages
12. Launch competitive monitoring workflow

---

*This baseline should be re-measured quarterly. Next measurement: June 2026.*
