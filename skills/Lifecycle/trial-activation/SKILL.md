---
name: trial-activation
description: |
  Design PLG activation emails and usage-based nudges that guide new signups to their "aha moment." Use when building onboarding email sequences, defining activation metrics, or optimizing time-to-value for self-serve users.
status: planned
---

# Trial Activation

## Goal
Get new self-serve signups to their first successful image transformation as fast as possible. Every hour of delay between signup and first API call increases churn risk.

## Activation Framework
1. **Define the "aha moment"** — For Imgix, this is likely: first image served through Imgix CDN with a transformation applied
2. **Map the activation path** — Signup → connect storage → configure source → serve first image → apply first transformation
3. **Identify drop-off points** — Where do users get stuck? (PostHog funnel analysis)
4. **Design nudges** — Email + in-app prompts at each drop-off point
5. **Measure and iterate** — Track activation rate and time-to-activation

## Email Sequence (Post-Signup)
- **Immediate:** Welcome + quickstart guide (connect your S3 bucket in 2 minutes)
- **Day 1:** "Your first transformation" — code example with URL parameters
- **Day 3:** If no API calls yet → "Need help connecting your storage?"
- **Day 7:** If activated → advanced features. If not → personal check-in offer.
- **Day 14:** If still not activated → last attempt with case study proof point.

## Related Skills
- **Lifecycle/email-sequence** — Email design framework
- **Lifecycle/prospect-nurture** — Hands off from nurture after signup
- **Lifecycle/expansion-upsell** — After activation, guide toward expansion
- **Conversion/onboarding-cro** — In-app onboarding (this skill handles email/messaging side)
- **Conversion/analytics-tracking** — Track activation events in PostHog
