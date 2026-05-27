# Imgix Conversion System

**Owner:** Michelle Su
**Created:** April 17, 2026
**Last Updated:** May 27, 2026

## What This Is

This folder is a coordinated system for optimizing the full conversion funnel — from landing page visit to activated user. Covers page optimization, signup flows, onboarding, experimentation, pricing, and measurement.

## How to Use This Folder

**When to invoke this folder:** A page isn't performing, you want to run an experiment, signup or onboarding has drop-off, you're rethinking pricing, or tracking is broken. Start with the sub-skill that matches the surface (page, signup, onboarding) or the activity (experiment, pricing, tracking).

**Context to bring:**
- The specific page or flow in question (URL or screenshot)
- Current metrics (conversion rate, drop-off point, sample size)
- The hypothesis or pain point ("I think users bounce because…")
- Target metric and what improvement would matter
- PostHog and Webflow access confirmed

**How the sub-skills fit together:**
- This folder is **hybrid.** Each sub-skill is mostly standalone, but three of them form a tight optimization loop: ab-test-setup + analytics-tracking + page-cro (or signup-flow-cro / onboarding-cro).
- For a quick page audit, page-cro alone is enough.
- For a structured experiment, run ab-test-setup first to define hypothesis and metrics, then the relevant surface skill, then analytics-tracking to confirm the test is wired up correctly.
- pricing-strategy stands alone. Use it when packaging or tiers are in question.

**Typical prompts:**
- "Audit the pricing page for CRO opportunities and propose three variants to test."
- "Design an A/B test for the signup form. Hypothesis: removing the company name field will lift signups 10%."
- "Improve activation by reducing time to first transform. Use onboarding-cro to map the current path and find the biggest drop-off."
- "Audit our PostHog tracking on the signup funnel. Are all events firing?"

**Output to expect:** Page audits with prioritized opportunities, A/B test briefs with hypothesis and success criteria, copy variant sets, tracking specifications, pricing tier proposals. Tests get implemented in PostHog, page changes in Webflow.

**When NOT to use this folder (and where to go instead):**
- Writing new pages or campaign copy → Content/copywriting
- Lifecycle and post-signup emails → Lifecycle/email-sequence
- Top-of-funnel traffic generation → Acquisition or Discoverability
- Sales enablement and enterprise objection handling → Product-Marketing/sales-enablement

## How Claude Runs this Folder

1. **Read this MANIFEST.md** to understand the system and current priorities
2. **Read MEMORY.md** for accumulated context from previous sessions
3. **Always load global skills first:** `imgix-brand-voice` and `product-marketing-context`
4. **Check each subfolder's STATUS.md** for current state
5. **Execute work** using the SKILL.md in the relevant subfolder
6. **Update STATUS.md and MEMORY.md** when work is completed
7. **Report results** via Slack to Michelle

## Connected Tools (MCP)

- **Webflow** — Modify landing pages, CTAs, and signup flows
  - Site ID: `6705f4b15aee7ca914fff083`
- **PostHog** — Run experiments, track conversion events, analyze funnels
- **HubSpot** — Track lead-to-signup conversion, form submissions
- **Jira** — Track optimization tasks (MKTG project)
- **Slack** — Report experiment results and wins

## Global Dependencies

- **imgix-brand-voice** — All page copy must follow brand guidelines
- **product-marketing-context** — Positioning informs value props on every page

## Subfolders

### 1. `page-cro/` — PAGE OPTIMIZATION
Optimize any marketing page for conversions — homepage, landing pages, pricing, feature pages. Start here when a page isn't performing.

### 2. `signup-flow-cro/` — SIGNUP OPTIMIZATION
Optimize the signup and registration flow. Reduce friction, improve completion rates, streamline the path from interest to account creation.

### 3. `onboarding-cro/` — ACTIVATION
Post-signup onboarding and user activation. Get new users to their "aha moment" as fast as possible. Critical for PLG.

### 4. `ab-test-setup/` — EXPERIMENTATION
Plan, design, and run A/B tests. Build a systematic experimentation program with hypothesis-driven testing.

### 5. `pricing-strategy/` — PACKAGING & PRICING
Pricing decisions, tier structure, value metrics, and packaging. Informs both the pricing page and in-product upgrade moments.

### 6. `analytics-tracking/` — MEASUREMENT
Set up and audit analytics tracking. Ensure every conversion event is properly measured so the other skills in this system can be data-driven.

## Cross-System References

- **Discoverability → Conversion:** Discoverability drives organic traffic; this system converts it.
- **Content → Conversion:** Content creates the pages; this system optimizes them.
- **Conversion → Lifecycle:** After signup and activation, Lifecycle takes over with nurture and retention.
- **Acquisition → Conversion:** Paid traffic and lead gen feed into pages this system optimizes.

## Definition of Done

This system is successful when:
- Signup conversion rate improves 20%+ from baseline
- Time-to-activation decreases for new PLG signups
- Experimentation velocity reaches 2+ tests/month
- Every key conversion event is tracked and measured
