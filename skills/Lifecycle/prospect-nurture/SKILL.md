---
name: prospect-nurture
description: |
  Design MQL-to-SQL email nurture flows that move prospects toward Imgix signup. Use when building lead scoring triggers, content-based nurture sequences, or automated email flows for top-of-funnel leads. Coordinates with HubSpot for automation. Triggers: "nurture sequence," "drip campaign," "MQL flow," "lead nurture," "email automation."
---

# Prospect Nurture

## Goal
Build automated nurture sequences that move prospects from initial interest (content download, docs visit, pricing page visit) to self-serve signup or sales-qualified lead. Imgix's PLG motion means most nurtures should push toward self-serve trial, not "book a demo."

## Imgix Nurture Context

**Who enters nurture:**
- Blog readers who subscribe or download a resource
- Developers who visit docs or API reference pages
- Pricing page visitors who don't sign up
- Comparison page visitors (imgix vs Cloudinary, etc.)
- Webinar or event attendees (future)
- HubSpot form submissions

**Key principle:** Developers hate long drip campaigns. Keep sequences short (3-5 emails max), value-dense, and respect that your audience is technical. Every email should teach something useful about image/video optimization, not just pitch Imgix.

## Nurture Sequence Types

### 1. Content-Based Nurture
**Trigger:** Blog engagement, resource download
**Length:** 4 emails over 2 weeks
**Emails:**
1. Related content that deepens the topic they engaged with
2. Technical how-to that demonstrates Imgix's URL-based approach
3. Case study from a relevant vertical (Ikyu for performance, Unsplash for scale, Skims for ecommerce)
4. CTA to start a free trial with a specific use case in mind

### 2. Product Interest Nurture
**Trigger:** Pricing page visit, docs visit, signup abandonment
**Length:** 3 emails over 10 days
**Emails:**
1. Address the likely question: "How does Imgix pricing work?" or "How do I get started?" Direct, specific, no fluff.
2. Technical quick-win: show a single URL parameter that solves a common problem (e.g., `auto=format` for automatic WebP/AVIF delivery)
3. Social proof + CTA: customer example with metrics, link to start trial

### 3. Competitor Evaluation Nurture
**Trigger:** Visited comparison page (imgix vs Cloudinary, imgix vs ImageKit)
**Length:** 3 emails over 10 days
**Emails:**
1. Honest, helpful framing of the key differences (URL-based vs. API-based, BYOS vs. vendor lock-in)
2. Migration guide or "switching from [competitor]" content
3. Trial CTA with positioning: "See the difference for yourself"

### 4. Re-engagement
**Trigger:** No engagement in 30+ days
**Length:** 2 emails
**Emails:**
1. "What's new at Imgix" — latest feature launches, new capabilities
2. If no response, remove from active nurture (don't keep emailing unengaged contacts)

## PLG Nurture Principles
- Short sequences (3-5 emails max). Developers don't want a 12-email drip.
- Value-first: every email teaches something useful about image or video optimization
- Include code examples and URL parameter demos where possible
- Primary CTA: self-serve signup (not "book a demo") for PLG motion
- Segment by signal: docs visitor gets technical content, pricing visitor gets ROI content
- All CTAs include UTM parameters: `utm_source=email&utm_medium=email&utm_campaign=[sequence_name]`

## HubSpot Implementation
- Create workflows for each sequence type
- Use contact properties to track which nurture a prospect is in
- Suppress nurture emails when a prospect enters the trial (hand off to trial-activation)
- Score leads based on engagement: email opens, link clicks, docs visits, pricing page returns

## Related Skills
- **Lifecycle/email-sequence** — General email design framework
- **Lifecycle/trial-activation** — Hands off to activation after signup
- **Acquisition/lead-magnets** — Lead magnets trigger nurture sequences
- **Content/content-strategy** — Nurture content comes from the content calendar
- **Conversion/analytics-tracking** — Track nurture to signup conversion
