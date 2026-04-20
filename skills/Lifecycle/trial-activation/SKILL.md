---
name: trial-activation
description: |
  Design activation emails and usage-based nudges that guide new Imgix signups to their "aha moment." Use when building onboarding email sequences, defining activation metrics, or optimizing time-to-value for self-serve users. Triggers: "activation flow," "onboarding emails," "time to value," "aha moment," "trial conversion," "post-signup sequence."
---

# Trial Activation

## Goal
Get new self-serve signups to their first successful image transformation as fast as possible. Every hour of delay between signup and first API call increases churn risk. Imgix offers a free trial (not a free tier), so the activation window is limited and every day matters.

## Imgix Activation Context

**The "aha moment":** First image served through Imgix with a transformation applied via URL parameters. When a developer appends `?w=400&auto=format` to a URL and sees the optimized image load instantly, they get it. Everything before that moment is friction.

**The activation path:**
1. Sign up at dashboard.imgix.com
2. Connect a storage source (S3 bucket, GCS, Azure Blob, web folder, or web proxy)
3. Configure a source in the dashboard
4. Serve first image through Imgix
5. Apply first transformation via URL parameter
6. See the result and understand the URL-based workflow

**Common drop-off points:**
- Storage connection (S3 bucket permissions are the #1 blocker for developers)
- Source configuration (CNAME setup can be confusing)
- Not understanding URL-based API model (developers expecting a traditional REST API)

## Email Sequence (Post-Signup)

All emails follow Imgix brand voice: benefit-first, short, no hype. See the `imgix-brand-voice` skill.

**Immediate (welcome):**
Subject: "Your Imgix account is ready"
Content: One sentence on what Imgix does, direct link to quickstart guide. CTA: "Connect your first source." Keep it under 3 sentences.

**Day 1 (first transformation):**
Subject: "Your first transformation in 30 seconds"
Content: Show a before/after URL example. `https://your-source.imgix.net/photo.jpg?w=400&auto=format,compress` — that's it. No SDK required, no build step. CTA: "Try it with your images."

**Day 3 (stuck check):**
If no API calls yet:
Subject: "Need help connecting your storage?"
Content: Link to the most common integration guide for their likely stack. Mention that Imgix supports S3, GCS, Azure, web folders, and web proxies. Offer a link to support if they're stuck on permissions.

If activated:
Subject: "What else you can do"
Content: Introduce 2-3 advanced features (auto=format for WebP/AVIF, face detection cropping, background removal). Show URL examples for each.

**Day 7 (engagement or re-engagement):**
If activated: Advanced features email — AI transforms, video capabilities, responsive image patterns. Position as "one platform" for all visual media.
If not activated: Personal check-in offer. "Having trouble getting set up? Reply to this email and our team will help."

**Day 14 (last attempt):**
If still not activated: Case study proof point (Ikyu serves 6B+ images with 16ms response times). Frame as "here's what teams are building with Imgix." Final CTA to connect a source or talk to the team.

## Activation Metrics to Track

Track these in PostHog:
- **Time to first image served** (signup to first API call)
- **Time to first transformation** (signup to first URL with parameters)
- **Source connection rate** (% of signups who connect at least one source)
- **Day 1/3/7 activation rates** (% active by each milestone)
- **Storage type distribution** (which sources do trial users connect?)
- **Drop-off funnel** (where exactly do users abandon?)

## Segmentation

Different users need different nudges:
- **Developer (docs visitor before signup):** Technical quickstart, code examples, SDK links
- **Marketing/product (pricing page visitor):** Use-case focused, ROI framing, visual before/afters
- **Evaluator (comparison page visitor):** Competitive advantages, migration guide if coming from Cloudinary/ImageKit

## Related Skills
- **Lifecycle/email-sequence** — Email design framework
- **Lifecycle/prospect-nurture** — Hands off from nurture after signup
- **Lifecycle/expansion-upsell** — After activation, guide toward expansion
- **Conversion/onboarding-cro** — In-app onboarding (this skill handles email/messaging side)
- **Conversion/analytics-tracking** — Track activation events in PostHog
