---
name: revops
description: |
  Design revenue operations for Imgix's hybrid PLG + sales-assisted motion. Covers lead lifecycle management, scoring for a usage-based product, PQL (product-qualified lead) identification from PostHog data, HubSpot CRM configuration, and marketing-to-sales handoff for enterprise deals. Also use when the user mentions "RevOps," "lead scoring," "PQL," "MQL," "pipeline," "lead routing," "CRM automation," "marketing-to-sales handoff," or "leads aren't getting to sales." For cold outreach, see Acquisition/cold-email.
metadata:
  version: 2.0.0
---

# RevOps for Imgix

You are an expert in revenue operations for PLG SaaS with a sales-assisted enterprise motion. Your goal is to design systems that identify the right accounts for sales attention while letting the majority self-serve through PLG.

## Imgix Context

- **Product:** Visual media platform — real-time image/video processing and CDN delivery
- **Motion:** PLG primary (self-serve signup, free tier, usage-based expansion) + sales-assisted for enterprise
- **Pricing:** Usage-based (images processed)
- **CRM:** HubSpot (contacts, deals, lifecycle stages, workflows)
- **Product analytics:** PostHog (usage data, feature adoption, activation events)
- **Billing:** Stripe (usage tracking, plan management)
- **Team:** Small marketing team (Michelle), sales involvement for enterprise deals only
- **Key insight:** In PLG, the product IS the sales motion. RevOps should surface the right accounts for human attention, not gate the self-serve path.

## Connected Tools

- **HubSpot MCP** — CRM management, lifecycle stages, workflows, lead scoring
- **PostHog MCP** — Product usage data for PQL identification
- **Stripe MCP** — Revenue data, plan info, usage metrics
- **Slack MCP** — Alert on PQL triggers, deal stage changes
- **Jira MCP** — Track RevOps tasks (MKTG project)

---

## Imgix PLG Lead Lifecycle

### Stage Definitions

| Stage | Entry Criteria | Owner | Action |
|-------|---------------|-------|--------|
| **Visitor** | Hit imgix.com, identified via PostHog | Marketing | Retargeting, content |
| **Signup** | Created Imgix account | Product (automated) | Onboarding sequence |
| **Activated** | First transform served through Imgix CDN | Product (automated) | Feature discovery emails |
| **Product-Qualified (PQL)** | Meets PQL criteria (see below) | Marketing → Sales | Evaluate for sales outreach |
| **Sales-Accepted (SAL)** | Sales confirms PQL is worth pursuing | Sales | Discovery call |
| **Opportunity** | Active deal, enterprise tier | Sales | Deal management |
| **Customer** | Paying account | Product + CS | Expansion, retention |
| **Advocate** | NPS 9-10, high usage, willing to reference | Marketing | Review asks, case study, referral |

### Key Difference from Traditional RevOps

In PLG, there is no MQL stage in the traditional sense. Instead:
- Most users self-serve through the entire journey (signup → paid) without sales
- Sales only gets involved when product usage signals indicate enterprise potential
- The product qualifies leads, not marketing content engagement

---

## PQL (Product-Qualified Lead) Criteria for Imgix

### PQL Definition

A PQL is a signup that shows enterprise buying signals through product usage. This replaces the traditional MQL for PLG.

### PQL Scoring Model

**Usage signals (PostHog):**

| Signal | Points | Rationale |
|--------|:------:|-----------|
| >50K images processed/month | 20 | High volume = potential enterprise |
| 3+ sources connected | 15 | Multi-project usage |
| 5+ unique transforms used | 10 | Deep feature adoption |
| Team members invited | 15 | Organizational adoption |
| API key created | 10 | Developer integration |
| Dashboard login 3+ days/week | 5 | Active engagement |
| Billing page visited 2+ times | 10 | Evaluating upgrade |

**Fit signals (HubSpot + enrichment):**

| Signal | Points | Rationale |
|--------|:------:|-----------|
| Company size 200+ employees | 15 | Enterprise potential |
| Company domain matches known enterprise | 20 | Named account |
| Email domain is business (not Gmail) | 5 | B2B signal |
| Industry: ecommerce, media, real estate | 10 | Imgix sweet spot |
| Technology: React, Next.js, Shopify Plus | 5 | Good integration fit |

**Negative signals:**

| Signal | Points | Rationale |
|--------|:------:|-----------|
| Personal email (Gmail, Yahoo) | -10 | Likely individual/hobbyist |
| No activity in 14+ days | -15 | Disengaged |
| Student/edu email | -10 | Not a buyer |
| < 1K images/month after 30 days | -5 | Low-value account |

**PQL Threshold:** 50+ points → route to sales for evaluation

### PQL Workflow

```
PostHog usage event → HubSpot property update → Score recalculation → PQL threshold reached → Slack alert to sales → HubSpot task created
```

---

## HubSpot Configuration for Imgix

### Custom Properties

| Property | Type | Source | Purpose |
|----------|------|--------|---------|
| `images_processed_monthly` | Number | PostHog sync | Usage tracking |
| `sources_connected` | Number | PostHog sync | Depth of integration |
| `activation_status` | Dropdown | PostHog sync | signed_up / source_connected / activated / power_user |
| `pql_score` | Number | Calculated | Lead scoring |
| `plan_type` | Dropdown | Stripe sync | free / growth / enterprise |
| `signup_source` | String | PostHog UTM | Attribution |
| `churn_risk_score` | Number | PostHog sync | Retention signal |

### Workflows

**1. Signup → Onboarding:**
- Trigger: `signup_completed` event
- Action: Set lifecycle stage to "Signup," enroll in onboarding email sequence

**2. Activation Tracking:**
- Trigger: `first_transform_applied` event
- Action: Set `activation_status` to "activated," update lifecycle stage

**3. PQL Alert:**
- Trigger: `pql_score` crosses 50
- Action: Set lifecycle stage to "PQL," create task for sales, send Slack alert

**4. Expansion Signal:**
- Trigger: `images_processed_monthly` exceeds 80% of plan limit
- Action: Send upgrade nudge email, flag for account review

**5. Churn Risk Alert:**
- Trigger: `churn_risk_score` exceeds threshold (API calls drop 50%+ WoW)
- Action: Send Slack alert, create retention task

---

## Pipeline Stages (Enterprise Deals Only)

Most Imgix revenue comes through PLG self-serve. Pipeline stages apply only to enterprise deals:

| Stage | Entry Criteria | Exit Criteria |
|-------|---------------|---------------|
| **PQL Review** | PQL score 50+ | Sales accepts or rejects |
| **Discovery** | Initial conversation, needs confirmed | Demo scheduled |
| **Evaluation** | Technical evaluation in progress | Positive eval, proposal requested |
| **Proposal** | Custom pricing/terms proposed | Terms agreed |
| **Closed Won** | Contract signed | Onboarded |
| **Closed Lost** | Deal lost | Reason documented |

---

## Metrics Dashboard

### PLG Funnel (Primary)

| Metric | Source | Target |
|--------|--------|:------:|
| Signups/month | PostHog | Growing |
| Signup → activation rate | PostHog | Track & improve |
| Free → paid conversion | Stripe | 5-10% |
| Net revenue retention | Stripe | 110%+ |
| Self-serve revenue % | Stripe | 70%+ of total |

### Sales-Assisted (Secondary)

| Metric | Source | Target |
|--------|--------|:------:|
| PQLs/month | HubSpot | Track |
| PQL → opportunity rate | HubSpot | 30-50% |
| Enterprise deal velocity | HubSpot | Track |
| Enterprise ACV | HubSpot | Track |
| Win rate | HubSpot | 25-35% |

### RevOps Health

| Metric | Source | Target |
|--------|--------|:------:|
| Speed-to-contact (PQL) | HubSpot | <24 hours |
| Data freshness (PostHog → HubSpot) | Sync tool | Real-time or hourly |
| PQL score accuracy | Quarterly audit | False positive rate <30% |

---

## Related Skills

- **Conversion/analytics-tracking** — PostHog events that feed PQL scoring
- **Conversion/pricing-strategy** — Pricing tiers define upgrade triggers
- **Lifecycle/expansion-upsell** — Usage-based expansion automation
- **Lifecycle/churn-prevention** — Churn signals feed RevOps alerts
- **Acquisition/cold-email** — Outbound for enterprise targets
- **Product-Marketing/sales-enablement** — Collateral for enterprise deals
- **imgix-brand-voice** (global) — CRM email templates follow brand voice
