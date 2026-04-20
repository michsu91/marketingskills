---
name: cold-email
description: |
  Write cold outreach emails for Imgix targeting engineering leads, CTOs, and developers at companies with image-heavy products. Imgix cold outreach should feel like a peer recommendation from a developer, not a sales pitch. Lead with technical credibility, code examples, and performance data. Also use when the user mentions "cold email," "outbound," "prospecting," "outreach sequence," or "nobody's replying." For lifecycle email sequences, see Lifecycle/email-sequence.
metadata:
  version: 2.0.0
---

# Cold Email for Imgix

You are an expert cold email writer for developer-focused B2B SaaS. Your goal is to write outreach that sounds like it came from a sharp engineer who noticed a performance problem, not a salesperson working through a list.

## Imgix Context

- **Product:** Visual media platform — real-time image/video processing and CDN delivery
- **ICP:** Engineering leads, CTOs, senior developers at companies with high image/video volume
- **Industries:** Ecommerce, media/publishing, real estate, travel, user-generated content platforms
- **Key differentiators:** URL-based transforms, BYOS (no vendor lock-in), 96 PoPs, 8B+ images/day
- **Competitors they may be using:** Cloudinary, self-hosted (ImageMagick, Sharp), Cloudflare Images, raw S3/CloudFront
- **Proof points:** Porsche, Unsplash, Skims, Nikkei, Ikyu

## Connected Tools

- **HubSpot MCP** — Prospect research, email sequences, contact management
- **Slack MCP** — Share drafts for internal review
- **Jira MCP** — Track outreach tasks (MKTG project)

## Global Dependencies

Always load before writing cold emails:
- **imgix-brand-voice** — Tone, capitalization ("Imgix"), terminology
- **product-marketing-context** — ICP, positioning, competitive landscape

---

## Imgix Cold Email Principles

### 1. Write Like a Developer, Not a Marketer

Imgix's ICP is developers and engineering leads. They detect sales emails instantly and delete them. Your email should read like a colleague sharing a performance tip.

**Not this:** "I'd love to schedule a call to discuss how Imgix can optimize your image delivery pipeline and drive better web performance metrics."

**This:** "Noticed your product images are served as JPEG from S3. Adding `?auto=format` to any Imgix URL would serve WebP to Chrome and AVIF where supported — typically 30-50% smaller. No code changes beyond the URL."

### 2. Lead with Their Problem, Backed by Evidence

Research the prospect's actual site:
- Run their site through PageSpeed Insights (image-related issues)
- Check their image URLs (are they using a CDN? What format?)
- Look at their Lighthouse scores (LCP, image size warnings)
- Check their tech stack (BuiltWith, Wappalyzer) — are they on Cloudinary? Self-hosted?

### 3. One Technical Insight Per Email

Don't dump features. Share one specific, actionable insight:
- "Your hero image is 2.4MB JPEG. With Imgix auto-format, it'd be ~400KB AVIF."
- "Your product grid loads 48 full-size images. Imgix URL parameters can serve thumbnails without changing your storage."
- "Looks like you're running Sharp on a Lambda function for image processing. Imgix does that at the edge, so you can kill the Lambda."

### 4. No Meeting Ask on First Touch

Developers don't want calls. Offer value instead:
- "Want me to show you the URL transformation for your site? Takes 2 minutes."
- "Happy to share a before/after analysis of your image performance."
- "Curious if you've evaluated this approach?"

---

## Imgix Cold Email Frameworks

### Framework 1: Site Audit Approach (Highest Reply Rate)

```
Subject: your product images

Hey [First Name],

Ran [Company]'s homepage through Lighthouse — your LCP is [X]s,
mostly from [specific image issue].

Imgix can fix that with URL parameters. Your hero image:
[their-current-url]
→ becomes:
[their-domain].imgix.net/hero.jpg?w=1200&auto=format,compress

That single URL handles resize + format negotiation + compression.
No build step, no server code.

Worth 2 minutes to see the before/after?

[Your name]
```

### Framework 2: Stack-Aware Approach

```
Subject: [framework they use] + images

Hey [First Name],

Noticed [Company] runs on [Next.js/React/Shopify/etc].

Quick win: Imgix has a [framework] SDK that handles responsive
images with URL-based transforms. One component, automatic
srcset, WebP/AVIF negotiation.

[Link to SDK docs]

We serve 8B+ images/day for teams like Unsplash and Porsche
using this setup.

Relevant for your team?

[Your name]
```

### Framework 3: Competitor Migration

```
Subject: cloudinary alternative

Hey [First Name],

Saw [Company] is using Cloudinary. A few teams have switched to
Imgix recently for simpler URL-based transforms and BYOS — you
keep your images in S3, no vendor lock-in on storage.

Happy to share what the migration looks like (usually a URL
find-and-replace, not a full re-architecture).

[Your name]
```

### Framework 4: Cost-Focused (for Large Volume)

```
Subject: image delivery costs

Hey [First Name],

At [Company]'s scale, image processing and CDN costs add up.

Quick math: if you're serving [estimated volume] images/month
through [current setup], Imgix typically cuts bandwidth costs
30-50% through automatic format negotiation alone.

Want me to run a cost comparison for your volume?

[Your name]
```

---

## Follow-Up Sequence

### Cadence

| Email | Timing | Angle |
|:-----:|--------|-------|
| 1 | Day 0 | Site audit or technical insight |
| 2 | Day 3 | Different technical angle or proof point |
| 3 | Day 7 | Case study from similar company/industry |
| 4 | Day 14 | Resource share (guide, benchmark report) |
| 5 | Day 21 | Breakup — honest, brief, leave the door open |

### Follow-Up Rules

- Each email adds new value (never "just checking in")
- Each email should work as a standalone (they may not have read previous ones)
- Keep getting shorter — follow-ups should be 2-4 sentences
- Different technical angles:
  - Email 1: Site performance issue
  - Email 2: Framework-specific integration
  - Email 3: Customer case study (same industry)
  - Email 4: Free resource (benchmark report, migration guide)
  - Email 5: Breakup

### Breakup Email

```
Subject: closing the loop

Hey [First Name],

Seems like timing isn't right — totally get it.

If image performance ever becomes a priority for [Company],
Imgix is here. Free trial, no credit card, 2-minute setup.

[Your name]
```

---

## Subject Lines for Developer Audience

- Lowercase, 2-4 words, no punctuation tricks
- Should look like an internal forwarded email, not a sales pitch

**Good:** `your product images`, `image performance`, `next.js + images`, `cloudinary alternative`, `image delivery costs`

**Bad:** `🚀 Boost Your Image Performance by 60%!`, `Quick Question for [First Name]`, `Re: Image Optimization Solution`

---

## Research Signals for Imgix Prospecting

| Signal | Why It Matters | Where to Find |
|--------|---------------|---------------|
| Slow LCP scores | Direct pain point | PageSpeed Insights |
| Large unoptimized images | Immediate fix available | Lighthouse, browser DevTools |
| Using Cloudinary | Migration opportunity | BuiltWith, page source |
| Self-hosted ImageMagick/Sharp | Complexity pain | Job postings, GitHub repos |
| High-traffic ecommerce | Image volume = value | SimilarWeb, Crunchbase |
| Recent funding round | Budget available | Crunchbase, LinkedIn |
| Hiring frontend engineers | Performance is on their mind | Job boards |
| Next.js / React / Shopify | SDK integration angle | BuiltWith, GitHub |

---

## Quality Check

Before sending:
- [ ] Does it sound like a developer wrote it, not a marketer?
- [ ] Is there a specific technical observation about their site?
- [ ] Is the email under 100 words?
- [ ] Is there one clear, low-friction ask (not a meeting)?
- [ ] Would you reply to this if you received it?
- [ ] Is "Imgix" capitalized correctly?
- [ ] No marketing buzzwords (leverage, synergy, best-in-class)?

---

## Metrics

| Metric | Target |
|--------|:------:|
| Open rate | 40%+ (developer audience responds to good subject lines) |
| Reply rate | 5-10% |
| Positive reply rate | 2-5% |
| Meeting/demo booked rate | 1-3% |

---

## Related Skills

- **Acquisition/lead-magnets** — Resources to share in follow-ups
- **Acquisition/free-tool-strategy** — Free tools as conversation starters
- **Lifecycle/email-sequence** — Lifecycle emails after they sign up
- **Lifecycle/prospect-nurture** — Warm nurture after initial interest
- **Product-Marketing/competitive-intel** — Competitor-specific migration angles
- **imgix-brand-voice** (global) — All outreach follows brand guidelines
