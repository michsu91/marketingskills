---
name: paid-ads
description: |
  Plan and optimize paid advertising for Imgix — Google Ads (search), LinkedIn (B2B targeting), and retargeting. Imgix's developer audience and PLG motion mean paid ads should drive free signups and tool trials, not demo requests. Also use when the user mentions "PPC," "Google Ads," "LinkedIn ads," "paid media," "ad budget," "retargeting," "CPA," "ROAS," or "should we run ads." For landing page optimization, see Conversion/page-cro.
metadata:
  version: 2.0.0
---

# Paid Ads for Imgix

You are an expert performance marketer for developer-focused B2B SaaS. Your goal is to help Imgix run paid campaigns that drive efficient developer signups through high-intent search and targeted retargeting.

## Imgix Context

- **Product:** Visual media platform — real-time image/video processing and CDN delivery
- **Motion:** PLG — ads should drive free signups, not demo requests
- **ICP:** Developers and engineering teams at companies with high image/video volume
- **Website:** Webflow (landing pages)
- **Analytics:** PostHog (product), GA4 (marketing site), HubSpot (CRM)
- **Budget consideration:** Likely modest paid budget — efficiency over volume
- **Competitors bidding:** Cloudinary (heavy Google Ads presence), ImageKit, Cloudflare

## Connected Tools

- **PostHog MCP** — Conversion tracking, signup attribution, retargeting cohorts
- **GA4 MCP** — Campaign performance, traffic attribution
- **HubSpot MCP** — Lead tracking, deal attribution
- **Jira MCP** — Track ad campaign tasks (MKTG project)

---

## Platform Strategy for Imgix

### Google Ads (Primary — Highest Intent)

**Why:** Developers searching for image optimization solutions have the highest purchase intent. Google captures existing demand.

**Campaign types:**
1. **Brand search:** Capture "imgix" and "imgix pricing" searches
2. **Competitor search:** "cloudinary alternative," "cloudinary vs" queries
3. **Category search:** "image CDN," "image optimization API," "image processing service"
4. **Problem search:** "slow image loading," "optimize images for web," "reduce image size"

### LinkedIn (Secondary — B2B Targeting)

**Why:** Target engineering leads and CTOs at companies that match Imgix's ICP. Good for awareness and retargeting.

**Campaign types:**
1. **Job title targeting:** Engineering managers, CTOs, VP Engineering at companies with 50-5000 employees
2. **Skill targeting:** React, Next.js, frontend engineering
3. **Retargeting:** Website visitors who didn't sign up

### Retargeting (Essential)

**Why:** Most developers research tools across multiple sessions. Retargeting captures return visits.

**Platforms:** Google Display Network, LinkedIn, Meta (limited)

---

## Google Ads for Imgix

### Keyword Strategy

**Brand Keywords (Always On):**
- `imgix`, `imgix pricing`, `imgix review`, `imgix vs cloudinary`
- Bid: Moderate (protect brand, capture high-intent)

**Competitor Keywords (High ROI):**
- `cloudinary alternative`, `cloudinary pricing`, `cloudinary vs`
- `imagekit alternative`, `cloudflare images alternative`
- Bid: Aggressive — these are actively evaluating
- Landing page: Comparison page showing Imgix advantages

**Category Keywords (Core):**
- `image CDN`, `image optimization API`, `image processing service`
- `real-time image transformation`, `image delivery network`
- `responsive image service`, `WebP CDN`
- Bid: Moderate — broader intent but relevant

**Problem Keywords (Top of Funnel):**
- `slow images website`, `optimize images for web performance`
- `reduce image load time`, `core web vitals images`
- `how to serve WebP`, `responsive images solution`
- Bid: Conservative — longer conversion path
- Landing page: Blog content or free tool, not direct signup

### Ad Copy for Developer Audience

**Principles:**
- Technical specificity over marketing fluff
- Include "Free" and "No credit card" in description
- Show technical credibility (8B+ images/day, 96 PoPs)
- Link to docs as sitelink (developers click docs links)

**Example ads:**

**Category search:**
```
Image Optimization API | Imgix
Real-time transforms via URL parameters.
WebP/AVIF auto-negotiation. 96 global PoPs.
Start free — no credit card required.
```

**Competitor search:**
```
Cloudinary Alternative | Imgix
URL-based transforms. Bring your own storage.
No vendor lock-in. Free tier available.
See why teams switch to Imgix.
```

**Problem search:**
```
Fix Slow Image Loading | Imgix
Add ?auto=format to any URL. 30-50% smaller.
No build step. No server code. Works instantly.
Free to start — optimize your first image today.
```

### Sitelinks

- Pricing
- Documentation
- Image Sandbox (free tool)
- Case Studies
- GitHub SDKs

### Negative Keywords

Exclude to save budget:
- `free image editor`, `image editing software`, `photoshop`
- `stock images`, `free images`, `image download`
- `image viewer`, `image converter` (desktop tools)
- `imgix careers`, `imgix jobs`

---

## LinkedIn Ads for Imgix

### Targeting

**Job titles:** Engineering Manager, CTO, VP Engineering, Lead Developer, Senior Frontend Engineer, Staff Engineer

**Company size:** 50-5000 employees (PLG sweet spot — enough traffic to need image optimization, not so large they have custom solutions)

**Industries:** Technology, Ecommerce, Media/Publishing, Real Estate, Travel

**Skills:** React, Next.js, Vue.js, Frontend Development, Web Performance

### Ad Formats

**Sponsored Content (primary):**
- Technical insight post promoting a lead magnet or blog
- Before/after image performance showcase
- Customer case study metrics (with permission)

**Conversation Ads (selective):**
- Only for high-value retargeting (visited pricing page)
- "Saw you were looking at image optimization. Here's a free performance audit of your site."

### Ad Copy Tone

LinkedIn for developers should still be technical and direct. Avoid:
- "Revolutionize your image pipeline" (too salesy)
- Generic stock imagery of people in meetings

Use:
- Code snippets in ad images
- Specific metrics and benchmarks
- Customer logos as social proof

---

## Retargeting Strategy

### Audience Segments

| Segment | Window | Message | Bid |
|---------|--------|---------|-----|
| Pricing page visitors | 1-14 days | "Ready to start? Free tier, no credit card." | High |
| Docs visitors | 1-30 days | "Try Imgix with your own images" + sandbox link | High |
| Blog readers (image topics) | 7-30 days | Educational content + free tool | Medium |
| Homepage visitors | 7-30 days | Core value prop + signup CTA | Medium |
| All visitors (broad) | 30-90 days | Brand awareness / case study | Low |

### Exclusions

- Exclude existing Imgix customers (match by email domain or customer list)
- Exclude recent signups (7-day window)
- Exclude bounced visitors (<10 seconds on site)
- Exclude careers page visitors

---

## Budget Allocation

### For a Modest Budget ($3-5K/month)

| Channel | Allocation | Rationale |
|---------|:----------:|-----------|
| Google Search (brand) | 15% | Protect brand, low cost |
| Google Search (competitor) | 30% | Highest-intent, best ROI |
| Google Search (category) | 25% | Core demand capture |
| Retargeting (Google + LinkedIn) | 20% | Convert research visitors |
| LinkedIn (prospecting) | 10% | Awareness, supplement |

### For a Larger Budget ($10K+/month)

Add:
- Google Search (problem keywords): 15%
- LinkedIn prospecting: Expand to 20%
- Experiment budget: 10% for testing new audiences/creatives

---

## Metrics

### Key Metrics

| Metric | Target |
|--------|:------:|
| Google Search CPC (category) | $3-8 (developer/B2B keywords) |
| Google Search CPC (competitor) | $5-15 |
| Landing page → signup rate | 5-15% |
| Cost per signup | Track & optimize |
| Signup → activation rate | Compare to organic baseline |
| Retargeting CTR | 0.5-1% |
| LinkedIn CPL | $30-80 (B2B developer) |

### Attribution

- UTM parameters on all ad URLs (track in PostHog + GA4)
- Compare ad-attributed signups to organic signups for quality
- Track signup → activation → paid conversion by ad source
- Use HubSpot source attribution for revenue tracking

---

## Common Mistakes for Developer Tool Ads

- **Driving to "Book a demo":** PLG = drive to free signup, not sales calls
- **Generic creative:** Developers ignore stock photos and buzzword headlines
- **Broad targeting:** Waste budget on non-developers who search image-related terms
- **No docs sitelink:** Developers click docs links — this is a positive signal
- **Ignoring retargeting:** Developer tool evaluation cycles are long (weeks-months)
- **Same landing page for all keywords:** Match landing page to search intent

---

## Related Skills

- **Conversion/page-cro** — Optimize landing pages for ad traffic
- **Conversion/signup-flow-cro** — Optimize signup flow for ad-driven visitors
- **Conversion/analytics-tracking** — UTM setup, conversion tracking
- **Acquisition/free-tool-strategy** — Free tools as ad destinations
- **Acquisition/lead-magnets** — Lead magnets for top-of-funnel ads
- **Content/copywriting** — Landing page copy for ad campaigns
- **imgix-brand-voice** (global) — Ad copy follows brand guidelines
