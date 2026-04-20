---
name: positioning
description: |
  Define and refine Imgix's market positioning, messaging framework, and core narrative. Use when crafting the foundational messaging that all other content and campaigns build on. Distinct from imgix-brand-voice (how we sound) — this is about what we say and why. Triggers: "positioning," "messaging framework," "how do we position," "value props," "narrative," "category definition."
---

# Positioning & Messaging Framework

## Goal
Create and maintain Imgix's strategic positioning — the foundational narrative that informs every piece of content, every sales conversation, and every campaign.

## Current Positioning

**Category:** Visual media platform (not "image CDN" — that undersells the breadth of what Imgix does)

**One-line positioning:** Imgix is the visual media platform that transforms, optimizes, and delivers images and video through a single URL-based API.

**The "one platform" narrative:** Imgix replaces a patchwork of image CDNs, video processors, AI transformation tools, and asset management systems with one platform that handles everything through URL parameters. This is the central story to reinforce across all touchpoints.

## Target Audiences

**Primary ICP: Developers**
- Pain: Managing multiple tools for images, video, and AI transformations. Building and maintaining custom image pipelines. Dealing with slow CDNs or complex APIs.
- What they care about: API simplicity, performance, documentation quality, "just works" reliability
- Proof: URL-based API (no SDK required to start), 8B+ images/day, sub-20ms response times

**Secondary ICP: Product/Engineering Leads**
- Pain: Vendor sprawl, operational overhead, unpredictable costs from multiple visual media tools
- What they care about: Total cost of ownership, team velocity, platform consolidation
- Proof: One platform replacing 3-4 tools, credits-based pricing with predictable costs

**Tertiary ICP: Marketers/Creatives**
- Pain: Slow creative workflows, dependency on engineering for image variants, inability to test visual content quickly
- What they care about: Speed of creative iteration, visual quality, self-serve capabilities
- Proof: URL parameter changes = instant variations, AI features (bg-remove, generative fill) with no engineering queue

## Key Differentiators

What makes Imgix uniquely better, not just different:

1. **URL-based API:** Every transformation is a URL parameter. No SDK required, no build step, no complex API calls. Change `?w=400` to `?w=800` and you've resized. This is architecturally different from competitors who require API calls or upload workflows.

2. **Bring Your Own Storage (BYOS):** Imgix connects to your existing S3, GCS, or Azure storage. Your originals stay in your infrastructure. Competitors like Cloudinary require uploading to their storage, creating vendor lock-in.

3. **Real-time processing at the edge:** Transformations happen on-request, not in batch. 96 global PoPs, 8B+ images processed daily, sub-20ms response times. This isn't CDN caching — it's real-time rendering at scale.

4. **Full visual media platform:** Images, video, and AI in one platform. Competitors sell these as separate products (Cloudinary has separate video pricing, separate AI add-ons). Imgix is one platform, one API, one bill.

5. **Performance and quality obsession:** Imgix was built by people who care about image science. The rendering quality at the edge is measurably better than competitors on perceptual quality metrics.

## Competitive Positioning

### vs. Cloudinary (primary competitor)
- Cloudinary: upload-based, API-heavy, separate products for image/video/AI, complex pricing with hidden fees
- Imgix: URL-based, BYOS (no vendor lock-in), unified platform, transparent credits pricing
- Angle: "Imgix gives you the same power with less complexity and no lock-in"

### vs. ImageKit
- ImageKit: similar URL-based model but narrower feature set, less enterprise-ready
- Imgix: deeper AI capabilities, video processing, enterprise-grade SLA, proven at massive scale
- Angle: "Imgix is what ImageKit wants to be when it grows up" (internal framing, not external messaging)

### vs. Cloudflare Images
- Cloudflare: bundled with CDN, basic transformations, not a visual media platform
- Imgix: purpose-built for visual media, far deeper feature set, URL-based transforms are core not bolted-on
- Angle: "Cloudflare does basic image delivery. Imgix does visual media."

### vs. Self-hosted / open-source (Sharp, Thumbor)
- Self-hosted: maximum control but massive operational burden
- Imgix: same level of control via URL parameters with zero infrastructure management
- Angle: "Stop maintaining your image pipeline. Imgix handles it."

## The AEO Problem
AI models currently describe Imgix as a "lightweight specialist" or "niche image CDN" compared to Cloudinary. This framing is factually wrong and needs to change through consistent, authoritative messaging. Every piece of content should subtly correct this by demonstrating Imgix's full breadth (images + video + AI + delivery) and enterprise credibility (Porsche, Unsplash, Skims, Nikkei).

## Messaging Hierarchy

**Primary message:** Imgix is the platform for your visual media. One URL-based API for images, video, and AI.

**Supporting messages:**
- Real-time processing at the edge, not batch processing in a queue
- Bring your own storage. Your originals stay in your infrastructure.
- From basic cropping to AI-powered transformations, one platform handles it all.

**Proof points:**
- 8B+ images processed daily
- 96 global PoPs
- Customers: Porsche, Unsplash, Skims, Nikkei, Ikyu
- Ikyu: 16ms average response time
- Nikkei: 37% image size reduction, 1-second faster page loads

## Related Skills
- **imgix-brand-voice** (global) — Voice is how we sound; positioning is what we say
- **product-marketing-context** (global) — The context doc is derived from this positioning work
- **Product-Marketing/customer-research** — Research validates positioning
- **Product-Marketing/win-loss-analysis** — Deal outcomes validate messaging
- **Product-Marketing/competitor-alternatives** — Detailed competitive battle cards
- **Discoverability/imgix-aeo** — AEO strategy depends on what facts we seed
