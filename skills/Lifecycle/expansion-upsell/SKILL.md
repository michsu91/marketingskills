---
name: expansion-upsell
description: |
  Design usage-based expansion triggers and upgrade flows for Imgix accounts. Use when building automated nudges for accounts approaching credit limits, identifying expansion-ready accounts, or designing upsell messaging for new capabilities (video, AI). Triggers: "upsell," "expansion," "upgrade flow," "plan limits," "NRR," "net revenue retention."
---

# Expansion & Upsell

## Goal
Increase net revenue retention (NRR, currently ~101%) by proactively identifying accounts ready to grow and nudging them at the right moment. Imgix's credits-based pricing means expansion should happen naturally as customers use more. This skill makes it intentional.

## Imgix Expansion Context

**Pricing model:** Credits-based consumption. Different render types have different credit costs:
- Standard renders (resize, crop, format): lowest cost
- Advanced renders (blending, stylize, text): moderate cost
- Premium renders (AI features, video): highest cost
- Specialized renders (image-to-video/Motion API): tracked separately

Customers buy annual credit allotments. Overages are billed separately. This creates natural expansion triggers when usage grows.

**Current revenue context:** Self-serve revenue is ~$427K-$510K/month, NRR is 101%, SS churn is 0.4%. The opportunity is to push NRR higher by capturing more expansion revenue from accounts that are growing organically.

## Expansion Triggers

### Usage-Based Triggers
1. **Credit threshold (80%):** Account hits 80% of annual credit allotment with months remaining. Automated nudge: "You're on track to exceed your plan. Here's how to add credits before overages kick in."
2. **Overage pattern:** Account has hit overages 2+ months in a row. Signal: they've outgrown their plan and need a larger allotment.
3. **Traffic spike:** Seasonal or growth-driven surge in image requests. Proactive: "Your traffic grew 40% this month. Let's make sure your plan keeps up."

### Feature Discovery Triggers
4. **AI feature adoption:** Account starts using premium features (bg-remove, upscale, generative fill). Upsell to a plan that includes AI credits at better per-credit pricing.
5. **Video adoption:** Account starts using Imgix Video capabilities. This is a new product surface and may require a plan change or add-on.
6. **New use case:** Account connects additional storage sources (S3 + GCS, or adds a second origin). Signal: they're expanding Imgix to more parts of their infrastructure.

### Account Growth Triggers
7. **Team growth:** Additional team members added to the dashboard. Signal: organizational adoption is spreading.
8. **Multi-product usage:** Account uses image + video + AI. Position as "you're getting the most out of the platform" and ensure pricing reflects the value.

## Messaging Principles

Follow Imgix brand voice for all expansion communications:
- Frame upgrades as "you're growing, here's how to keep up" not "you're hitting limits"
- Show value delivered before asking for more: "You've served 12M optimized images this quarter, saving an estimated [X] seconds of load time"
- Make upgrading self-serve and frictionless (PLG). The customer should be able to upgrade their plan without talking to anyone.
- For larger accounts, trigger sales assist at the right moment (Glenn or the sales team)
- Never use urgency or pressure tactics. Developers see through it and it erodes trust.

## Expansion Email Templates

**Credit threshold nudge:**
Subject: "Your Imgix usage is growing"
Body: 2 sentences on their usage trend, link to upgrade self-serve, option to talk to the team for custom pricing.

**Feature discovery upsell:**
Subject: "You just tried [AI feature]. Here's what else is possible."
Body: Show 2-3 related premium features they haven't tried yet. Position as capabilities of the same platform they already trust.

**Overage prevention:**
Subject: "Heads up: you're on track for overages this month"
Body: Current usage vs. plan, cost comparison of overages vs. upgrading, one-click upgrade link.

## Tracking in PostHog and BigQuery
- Credit utilization rate by account (BigQuery)
- Feature adoption events (PostHog)
- Upgrade conversion rate from each trigger type
- Time from trigger to upgrade
- Revenue impact per expansion type

## Related Skills
- **Lifecycle/trial-activation** — Activation precedes expansion
- **Lifecycle/churn-prevention** — Expansion and retention are two sides of the same coin
- **Conversion/pricing-strategy** — Pricing tiers define what "expansion" means
- **Conversion/analytics-tracking** — Track usage patterns that signal expansion readiness
- **Product-Marketing/revops** — Revenue operations tracks NRR and expansion metrics
