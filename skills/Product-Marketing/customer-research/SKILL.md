---
name: customer-research
description: |
  Conduct and analyze customer research for Imgix — interview analysis, Gong call mining, G2 review analysis, Reddit/HN research, survey synthesis, and persona building. Use when building personas, extracting voice of customer, understanding why developers choose (or don't choose) Imgix, or mining developer communities for insights. Also use when the user mentions "customer research," "ICP research," "voice of customer," "customer interviews," "Gong analysis," "G2 reviews," "personas," or "what do customers say."
metadata:
  version: 2.0.0
---

# Customer Research for Imgix

You are an expert customer researcher for developer-focused B2B products. Your goal is to uncover what developers and engineering teams actually think, need, and say about image/video optimization, so Imgix's positioning, product, and copy are grounded in reality.

## Imgix Context

- **Product:** Visual media platform — real-time image/video processing and CDN delivery
- **ICP:** Developers and engineering teams at companies with high image/video volume
- **Industries:** Ecommerce, media/publishing, real estate, travel, user-generated content
- **Competitors:** Cloudinary, ImageKit, Cloudflare Images, BunnyCDN, self-hosted (ImageMagick, Sharp)
- **Key customers:** Porsche, Unsplash, Skims, Nikkei, Ikyu

## Connected Tools

- **HubSpot MCP** — CRM data, deal notes, customer contact info
- **Slack MCP** — Internal discussions about customers, support escalations
- **Jira MCP** — Product feedback tickets, feature requests
- **PostHog MCP** — Usage patterns, feature adoption, behavioral cohorts

## Global Dependencies

Always load before research:
- **product-marketing-context** — Current ICP, positioning, competitive landscape
- **imgix-brand-voice** — Customer vocabulary vs. Imgix vocabulary comparison

---

## Research Sources for Imgix

### Internal Sources

| Source | What to Extract | Where |
|--------|----------------|-------|
| Gong calls | Why they evaluated Imgix, objections, competitor mentions, decision criteria | Gong |
| HubSpot deal notes | Win/loss reasons, deal timeline, competitive intelligence | HubSpot MCP |
| Support tickets | Recurring pain points, feature requests, confusion patterns | Zendesk/Intercom |
| Slack (internal) | Customer anecdotes, escalations, product feedback | Slack MCP |
| NPS responses | Promoter language (for marketing), detractor pain (for product) | Survey tool |
| PostHog behavior | What activated users do differently, feature adoption patterns | PostHog MCP |

### External Sources (Developer Communities)

| Source | What to Look For | Search Approach |
|--------|-----------------|----------------|
| Reddit (r/webdev, r/nextjs, r/frontend) | Image optimization discussions, tool recommendations, Imgix mentions | `site:reddit.com imgix OR "image cdn" OR "image optimization"` |
| Hacker News | Image CDN discussions, performance conversations | Search HN for "imgix," "image cdn," "cloudinary" |
| Stack Overflow | Questions about image optimization Imgix could solve | Tags: image-optimization, cdn, responsive-images |
| G2 / Capterra | Imgix reviews, competitor reviews (mine 3-4 star for nuance) | Filter by "Image Optimization" category |
| GitHub | SDK issues, integration challenges, feature requests | imgix org repos, issues and discussions |
| Dev.to / Hashnode | Developer blog posts mentioning Imgix or image optimization | Search by keyword |
| Twitter/X | Developer opinions, complaints, recommendations | Search "imgix" and competitor names |

---

## Imgix-Specific Extraction Framework

For each source, extract:

### 1. Jobs to Be Done

**Functional jobs developers hire Imgix for:**
- Serve optimized images without building a processing pipeline
- Deliver images in the right format for each browser automatically
- Resize and crop images on-the-fly without pre-generating variants
- Reduce bandwidth costs and improve load times

**Emotional jobs:**
- Confidence that images won't break or slow down the site
- Relief from maintaining image processing infrastructure
- Pride in shipping a fast, well-optimized product

### 2. Trigger Events

What makes developers start looking for an image CDN?
- Performance audit reveals images are the LCP bottleneck
- Traffic growth makes self-hosted processing expensive/fragile
- New project with high image volume (ecommerce launch, media platform)
- Frustration with current solution complexity (Cloudinary credit system, self-hosted maintenance)
- Team growth means less time for infrastructure management
- Core Web Vitals requirements from Google

### 3. Language and Vocabulary

Capture exact developer language:
- How do they describe the problem? ("Our images are massive," "LCP is killing us," "I hate writing image processing code")
- How do they describe the solution? ("Just works," "URL params are genius," "no infra to manage")
- What terms do they use? (CDN, transforms, responsive images, srcset, WebP, AVIF, lazy loading)
- What Imgix terminology do they use vs. not use?

### 4. Alternatives Considered

- Cloudinary (most common comparison)
- Self-hosted ImageMagick/Sharp on Lambda/Cloud Functions
- Cloudflare Images (for teams already on Cloudflare)
- ImageKit (price-sensitive teams)
- Doing nothing (serving raw images from S3/GCS)
- Building custom (especially at larger companies)

### 5. Objections and Concerns

- "What happens to my images if I leave?" → BYOS addresses this
- "Is it worth the cost vs. self-hosted?" → TCO comparison needed
- "How does it compare to Cloudinary?" → Feature comparison needed
- "Will it scale?" → 8B+ images/day proof point
- "Can it handle video?" → Growing capability, be honest about maturity

---

## Imgix Persona Templates

### Primary Persona: Senior Frontend Developer

```
## Senior Frontend Developer

**Profile:**
- Title: Senior Software Engineer, Staff Engineer, Frontend Lead
- Company: 100-2000 employees, Series B+ or established
- Industry: Ecommerce, media, SaaS with user-generated content
- Reports to: Engineering Manager or VP Engineering
- Tech stack: React/Next.js, TypeScript, AWS/GCP

**Primary Job to Be Done:**
Ship a fast, visually excellent product without building and maintaining image infrastructure.

**Trigger Events:**
- LCP audit shows images are the bottleneck
- Image processing Lambda/server is failing under load
- New project with high image volume
- Team can't justify time on image pipeline maintenance

**Top Pains:**
1. "I'm spending time writing image processing code instead of building product features"
2. "Every time we add a new image size, I have to update the build pipeline"
3. "Our images are way too large but I don't have time to optimize each one"

**Desired Outcomes:**
- Images just work — right size, right format, fast delivery
- Zero infrastructure to maintain
- Simple integration with existing codebase

**Key Vocabulary:**
- "Just add a URL parameter"
- "No build step"
- "Works with our existing S3 bucket"
```

### Secondary Persona: Engineering Manager / Tech Lead

```
## Engineering Manager / Tech Lead

**Profile:**
- Title: Engineering Manager, VP Engineering, CTO
- Company: 200-5000 employees
- Evaluates tools for team adoption

**Primary Job to Be Done:**
Reduce infrastructure complexity and let the team focus on core product.

**Trigger Events:**
- Image processing costs growing faster than revenue
- Team complaining about maintenance burden
- Performance requirements from business stakeholders

**Top Pains:**
1. "We're paying an engineer to maintain an image pipeline that isn't our core competency"
2. "I need reliability at scale — we can't have images go down"
3. "I don't want vendor lock-in on our asset storage"

**Key Vocabulary:**
- "Total cost of ownership"
- "Vendor lock-in"
- "Enterprise SLA"
```

---

## Research Quality Guardrails

| Confidence | Criteria |
|------------|----------|
| **High** | Theme in 3+ independent sources, mentioned unprompted, consistent across segments |
| **Medium** | Theme in 2 sources, or only prompted, or single segment |
| **Low** | Single source, could be outlier, needs validation |

**Imgix-specific biases to account for:**
- G2 reviewers skew toward power users with strong opinions
- Reddit skews technical and skeptical
- Gong calls only capture people who got far enough to talk to sales
- Support tickets skew toward problems, not value

---

## Deliverables

1. **Research synthesis** — Themes, quotes, patterns, implications for Imgix
2. **VOC quote bank** — Organized verbatim quotes for use in copy and sales
3. **Persona documents** — 2-3 personas built from research
4. **Competitive intelligence** — What developers say about Imgix vs. competitors
5. **Messaging recommendations** — What language to use (and avoid) based on research

---

## Related Skills

- **Product-Marketing/positioning** — Research validates and refines positioning
- **Product-Marketing/win-loss-analysis** — Win/loss is a research subset
- **Product-Marketing/competitor-alternatives** — Competitive intel feeds comparison pages
- **Product-Marketing/sales-enablement** — VOC feeds objection handling
- **Content/copywriting** — VOC language directly informs copy
- **Lifecycle/churn-prevention** — Churn research feeds retention strategy
- **imgix-brand-voice** (global) — Research reveals if brand voice matches customer language
