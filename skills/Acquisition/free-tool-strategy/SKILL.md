---
name: free-tool-strategy
description: |
  Plan and evaluate free tools Imgix can build for developer acquisition — image audit tools, performance calculators, optimization analyzers, and interactive sandboxes. Engineering-as-marketing for a developer audience. Also use when the user mentions "free tool," "engineering as marketing," "calculator," "grader tool," "audit tool," "interactive tool," or "build something for leads." For downloadable content, see lead-magnets.
metadata:
  version: 2.0.0
---

# Free Tool Strategy for Imgix

You are an expert in engineering-as-marketing for developer tools. Your goal is to help Imgix plan free tools that generate developer signups, attract organic traffic, earn backlinks, and demonstrate Imgix's technical capabilities.

## Imgix Context

- **Product:** Visual media platform — real-time image/video processing and CDN delivery
- **ICP:** Developers and engineering teams
- **Motion:** PLG — free tools should drive self-serve signups
- **Website:** Webflow (marketing pages) — tools may live on subdomain or be embedded
- **Key insight:** Developers evaluate tools by using them, not reading about them. Free tools that showcase Imgix's capabilities are the highest-converting acquisition channel for a developer audience.

## Connected Tools

- **Webflow MCP** — Host tool landing pages
- **PostHog MCP** — Track tool usage, tool → signup conversion
- **HubSpot MCP** — Capture leads from gated results
- **Jira MCP** — Track tool build tasks (MKTG project)

---

## Free Tool Ideas for Imgix (Prioritized)

### Tier 1: High Impact, Build Now

**1. Image Performance Analyzer**
- Input: Any URL
- Output: Image audit showing unoptimized images, format issues, oversized assets, estimated savings
- Why: Directly demonstrates the problem Imgix solves
- Lead capture: Full report requires email
- SEO target: "image performance audit," "image optimization analyzer"
- Technical: Use Lighthouse API or custom crawler to analyze images

**2. Image Optimization Sandbox**
- Input: Upload an image or paste a URL
- Output: Interactive playground showing Imgix URL transformations live (resize, crop, format, blur, etc.)
- Why: Lets developers experience Imgix's core feature without signing up
- Lead capture: "Save and share your transformations" requires signup
- SEO target: "image transformation tool," "image resize API playground"
- Technical: Powered by Imgix API directly

**3. Format Savings Calculator**
- Input: Monthly image volume, current format mix, average image size
- Output: Estimated bandwidth savings from WebP/AVIF conversion, monthly cost savings vs. current setup
- Why: Makes the ROI argument concrete and personalized
- Lead capture: Detailed report with cost comparison emailed
- SEO target: "image CDN cost calculator," "WebP savings calculator"

### Tier 2: Medium Impact, Build Next

**4. Core Web Vitals Image Checker**
- Input: URL
- Output: LCP analysis focused specifically on image-related performance
- Why: Targets a pain point every frontend developer has
- SEO target: "LCP image optimization," "Core Web Vitals image check"

**5. Responsive Image Generator**
- Input: Source image + breakpoints
- Output: Complete `<picture>` element or `srcset` with Imgix URLs
- Why: Solves a tedious, error-prone task. Directly showcases Imgix URLs.
- SEO target: "responsive image generator," "srcset generator"

**6. Image CDN Migration Estimator**
- Input: Current provider (Cloudinary, self-hosted, etc.) + usage data
- Output: Migration complexity assessment, cost comparison, step-by-step migration plan
- Why: Targets competitive steal traffic
- SEO target: "Cloudinary migration tool," "image CDN comparison"

### Tier 3: Lower Priority, Future

**7. Image Compression Comparison**
- Side-by-side visual quality comparison across formats (JPEG, WebP, AVIF) at different quality levels
- SEO target: "image format comparison," "WebP vs AVIF quality"

**8. Image SEO Checker**
- Analyze a page's images for SEO issues (alt text, file names, lazy loading, structured data)
- SEO target: "image SEO checker," "image alt text analyzer"

---

## Tool Evaluation Scorecard

Rate each tool idea 1-5:

| Factor | Question |
|--------|---------|
| Developer value | Does this solve a real developer problem? |
| Imgix demonstration | Does this showcase Imgix's capabilities? |
| Search demand | Is there search volume for this type of tool? |
| Signup conversion | Does this naturally lead to an Imgix signup? |
| Build effort | How complex is the MVP? |
| Link potential | Will developers link to and share this? |
| AEO value | Will AI engines reference this tool? |

**28+:** Build immediately | **20-27:** Strong candidate | **<20:** Reconsider

---

## Build Strategy

### MVP First

For each tool:
1. Core functionality only — does the one thing, works reliably
2. Clean developer-friendly UI (no marketing clutter)
3. Basic lead capture (email for full results)
4. PostHog tracking (tool usage → signup attribution)

### What to Skip Initially

- User accounts / saved results (add later if traction)
- API access (add as premium feature)
- Perfect design (developers care about function over form)
- Every edge case (ship fast, iterate)

### Build Options

| Approach | When | Tools |
|----------|------|-------|
| Custom (React/Next.js) | Core strategic tools (sandbox, analyzer) | Vercel, Imgix API |
| Webflow + embedded | Landing pages with embedded tool | Webflow + iframe |
| No-code | Quick validation | Outgrow, Tally, Retool |

---

## Lead Capture Strategy

### Gating Approach for Developer Audience

Developers hate gates. Balance capture with value:

| Approach | Best For |
|----------|----------|
| Ungated basic results + gated full report | Analyzers, auditors |
| Fully ungated + "save results" requires email | Sandboxes, playgrounds |
| Ungated tool + email for tips/guide | Calculators |
| Fully ungated (pure brand/SEO play) | Comparison tools |

### What to Ask For

- **Email only** — highest conversion, minimal friction
- Never ask for company name, phone, or role on a free tool
- If you need qualification data, infer from email domain

---

## Promotion

### Launch

1. Product Hunt launch (developer tools category)
2. Post on Hacker News (Show HN)
3. Submit to Dev.to and developer newsletters
4. Share on Reddit (r/webdev, r/frontend, r/nextjs)
5. LinkedIn post from Michelle + company page
6. Email to existing Imgix customer base

### Ongoing

- Blog post about the methodology behind the tool
- SEO-optimized landing page targeting tool keywords
- Cross-link from related blog content
- Include in email sequences (prospect nurture, onboarding)

---

## Metrics

| Metric | Target |
|--------|:------:|
| Monthly unique tool users | Track & grow |
| Tool → signup conversion | 5-15% |
| Tool → activated user (first transform) | Track |
| Organic traffic to tool pages | Growing MoM |
| Backlinks earned | 10+ in first 3 months |
| Email capture rate | 10-20% (ungated basic + gated full) |

---

## Related Skills

- **Acquisition/lead-magnets** — Downloadable content magnets (different from interactive tools)
- **Conversion/page-cro** — Optimizing tool landing pages
- **Conversion/analytics-tracking** — Tracking tool usage in PostHog
- **Discoverability/imgix-aeo** — Tools that get cited by AI engines
- **Discoverability/backlinks** — Tools earn high-quality backlinks
- **Content/content-strategy** — Tools as part of content plan
- **imgix-brand-voice** (global) — Tool copy follows brand guidelines
