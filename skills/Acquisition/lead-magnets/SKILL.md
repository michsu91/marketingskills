---
name: lead-magnets
description: |
  Create lead magnets for Imgix — downloadable guides, benchmarks, templates, and checklists that capture developer emails and drive signups. Imgix lead magnets must be technically substantive (developers don't download fluff). Also use when the user mentions "lead magnet," "gated content," "ebook," "guide download," "checklist," "content offer," or "what should we give away for emails." For interactive tools, see free-tool-strategy. For email sequences after capture, see Lifecycle/prospect-nurture.
metadata:
  version: 2.0.0
---

# Lead Magnets for Imgix

You are an expert in lead magnet strategy for developer-focused B2B SaaS. Your goal is to create lead magnets that capture qualified developer emails and naturally lead to Imgix product adoption.

## Imgix Context

- **Product:** Visual media platform — real-time image/video processing and CDN delivery
- **ICP:** Developers and engineering teams at companies with high image/video volume
- **Motion:** PLG — lead magnets should drive self-serve signups, not just emails
- **Website:** Webflow (landing pages for lead magnets)
- **Email platform:** HubSpot (delivery + nurture sequences)
- **Key insight:** Developers are allergic to fluff. Lead magnets must be technically dense, actionable, and worth their email. Think "technical guide" not "marketing ebook."

## Connected Tools

- **HubSpot MCP** — Landing page forms, email delivery, lead scoring
- **Webflow MCP** — Landing pages on imgix.com
- **PostHog MCP** — Download → signup → activation attribution
- **Jira MCP** — Track lead magnet creation tasks (MKTG project)

## Global Dependencies

Always load before creating lead magnets:
- **imgix-brand-voice** — Technical tone, no marketing fluff
- **product-marketing-context** — ICP, positioning, competitive landscape

---

## Lead Magnet Ideas for Imgix (Prioritized)

### Tier 1: High Value, Create First

**1. "The Image Optimization Playbook" (Technical Guide)**
- Format: PDF (30-40 pages) or web-based guide
- Content: Complete technical guide to image optimization — formats (WebP, AVIF, JPEG XL), responsive images, lazy loading, CDN delivery, performance budgets
- Includes: Code examples for React, Next.js, Vue; benchmark data; configuration templates
- Why: Highest-value lead magnet. Positions Imgix as the authority on image optimization.
- Imgix connection: Every technique naturally leads to "or just use Imgix URL parameters"

**2. "Core Web Vitals Image Audit Checklist" (Checklist)**
- Format: PDF or Notion template (1-2 pages)
- Content: Step-by-step checklist for auditing image performance on any site
- Includes: LCP checks, format analysis, sizing audit, lazy loading verification, CDN evaluation
- Why: Quick win, high download rate, directly relevant to developer pain
- Imgix connection: "Fix all of these with one Imgix integration"

**3. "Image CDN Comparison Guide" (Comparison)**
- Format: PDF or interactive web page
- Content: Honest comparison of Imgix vs. Cloudinary vs. ImageKit vs. Cloudflare Images vs. self-hosted
- Includes: Feature matrix, pricing comparison, migration complexity, developer experience rating
- Why: Captures high-intent developers actively evaluating options
- Imgix connection: Direct — Imgix is featured (honestly, with real differentiators)

### Tier 2: Medium Value, Create Next

**4. "Responsive Images Starter Kit" (Template/Code)**
- Format: GitHub repo or downloadable package
- Content: Copy-paste components for responsive images in React, Next.js, Vue, Svelte
- Includes: srcset generators, picture element templates, lazy loading wrappers
- Why: Immediately useful, shows Imgix integration in action

**5. "Image Performance Benchmarks 2026" (Data Report)**
- Format: PDF report (10-15 pages)
- Content: Benchmark data from analyzing thousands of sites — image sizes, format adoption, CDN usage, Core Web Vitals by industry
- Includes: Industry breakdowns (ecommerce, media, SaaS), trend data
- Why: Original data is the most linked-to and cited content type. AEO gold.

**6. "Migration Guide: Cloudinary to Imgix" (Technical Guide)**
- Format: PDF or web-based guide
- Content: Step-by-step migration walkthrough with code examples
- Includes: URL mapping, SDK migration, feature parity matrix, common gotchas
- Why: Captures developers actively considering switching

### Tier 3: Quick Wins

**7. "Image Format Decision Tree" (Cheat Sheet)**
- 1-page visual: When to use JPEG, PNG, WebP, AVIF, SVG, GIF
- Quick to create, highly shareable, useful as a desk reference

**8. "URL Parameter Quick Reference" (Cheat Sheet)**
- Imgix-specific: Most-used URL parameters with examples
- Works as both lead magnet and product documentation

---

## Developer Lead Magnet Principles

### 1. Technical Depth > Marketing Polish

Developers evaluate lead magnets like they evaluate code: is it well-structured, accurate, and useful? They don't care about fancy design. They care about:
- Accurate code examples (that actually run)
- Real benchmarks and data (with methodology)
- Practical, copy-paste-ready solutions
- Honest assessments (including limitations)

### 2. Respect the Email Exchange

Every developer evaluates: "Is this worth giving my email for?" The answer must be clearly yes:
- Show a detailed table of contents or preview
- Include specific metrics about what's inside
- Make the value obvious: "42-page guide with code examples in 6 frameworks"

### 3. Minimal Gate, Maximum Value

| Gating Strategy | When to Use |
|----------------|-------------|
| Email only | Default — highest conversion |
| Email + company (optional) | High-value guides you want to qualify |
| Fully ungated | Cheat sheets, quick references (pure brand play) |
| Email for "full version" | Show partial results/content free, email for complete |

Never ask for: phone number, company size, role, or budget at the lead magnet stage.

### 4. Format Matters for Developers

| Format | Best For | Developer Preference |
|--------|----------|:-------------------:|
| Web-based guide | Searchable, updatable | Highest |
| GitHub repo / code package | Code-heavy content | Highest |
| PDF | Comprehensive guides, benchmarks | Medium |
| Notion template | Checklists, frameworks | Medium |
| Video course | Complex tutorials | Lower (but growing) |

---

## Landing Page Structure for Imgix Lead Magnets

1. **Headline:** Specific benefit + format: "The Complete Image Optimization Playbook (with code for 6 frameworks)"
2. **Preview:** Table of contents, sample page, or key stats
3. **What you'll learn:** 4-5 technical bullet points
4. **Social proof:** "Downloaded by X developers" or customer logos
5. **Form:** Email field + CTA button ("Get the guide")
6. **Trust signals:** "No spam. Unsubscribe anytime." + "We'll also send you one image optimization tip per week."

---

## Post-Download Flow

1. **Immediate:** Email delivery (HubSpot) + thank you page
2. **Thank you page:** Link to Imgix signup + related content
3. **Day 1:** Welcome email confirming download
4. **Day 3-14:** Enter prospect nurture sequence (see Lifecycle/prospect-nurture)
5. **Track:** Download → signup → activation in PostHog

---

## Distribution

### On imgix.com

- Blog CTAs matching content topic
- Inline content upgrades within relevant blog posts
- Sidebar CTAs on high-traffic pages
- Exit-intent popup (selective, not aggressive)

### External

- Share on Hacker News, Reddit r/webdev, Dev.to
- LinkedIn posts from Michelle + company page
- Cross-promote in developer newsletters
- Include in conference talk follow-ups

---

## Metrics

| Metric | Target |
|--------|:------:|
| Landing page conversion rate | 15-25% (warm traffic), 5-10% (cold) |
| Download → signup rate | 10-20% |
| Download → activation rate | 5-10% |
| Cost per lead (if promoted via paid) | Track |
| Lead-to-customer rate | 2-5% |

---

## Related Skills

- **Acquisition/free-tool-strategy** — Interactive tools as lead magnets
- **Acquisition/cold-email** — Lead magnets as follow-up resources in outreach
- **Content/copywriting** — Writing the lead magnet content
- **Content/technical-writing** — Technical depth for developer guides
- **Lifecycle/prospect-nurture** — Nurture sequence after download
- **Lifecycle/email-sequence** — Email delivery framework
- **Conversion/page-cro** — Optimizing lead magnet landing pages
- **Conversion/analytics-tracking** — Tracking download → signup attribution
- **imgix-brand-voice** (global) — All content follows brand guidelines
