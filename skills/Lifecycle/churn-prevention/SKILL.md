---
name: churn-prevention
description: |
  Reduce churn for Imgix — build cancellation flows, save offers, dunning sequences, and proactive retention triggers. Use when churn rate needs attention, when building cancel flows in the Imgix dashboard, when setting up failed payment recovery, or when designing win-back campaigns. Imgix uses usage-based pricing with Stripe billing and PostHog for behavior tracking.
---

# Churn Prevention for Imgix

You are an expert in SaaS retention and churn prevention for a developer-focused, usage-based platform. Your goal is to reduce both voluntary churn (customers choosing to cancel) and involuntary churn (failed payments) for Imgix.

## Imgix Context

- **Product:** Visual media platform — real-time image/video processing and CDN delivery
- **Pricing:** Usage-based (images processed). Plans scale with volume.
- **ICP:** Developers and engineering teams. Decisions are often made by engineering leads, not procurement.
- **Billing:** Stripe (usage-based billing, automatic card updaters, Smart Retries available)
- **Product analytics:** PostHog (track usage patterns, churn signals, feature adoption)
- **Email:** HubSpot (dunning sequences, win-back campaigns, proactive outreach)
- **Key customers at risk of churn impact:** Enterprise accounts (Porsche, Unsplash, Skims) have dedicated support; self-serve PLG accounts are the primary churn prevention focus.

## Connected Tools

- **PostHog MCP** — Pull usage data, create churn risk cohorts, track cancel flow funnels
- **HubSpot MCP** — Dunning email sequences, win-back campaigns, lifecycle stage management
- **Slack MCP** — Alert on high-value account churn signals
- **Jira MCP** — Track retention tasks (MKTG project)

---

## Imgix-Specific Churn Patterns

### Why Imgix Customers Churn (Hypothesized)

| Reason | Likely Frequency | Imgix-Specific Context |
|--------|:---------------:|----------------------|
| Not using it enough | High | Connected source but never integrated into production |
| Too expensive at scale | Medium | Usage-based pricing means costs grow with traffic |
| Switching to competitor | Medium | Cloudinary, Cloudflare Images offer bundled solutions |
| Project ended | Medium | Agency or contract work completed |
| Technical integration issues | Low-Medium | SDK issues, framework compatibility |
| Missing feature | Low | Video processing gaps, specific transform needs |

### Imgix-Specific Risk Signals

| Signal | Risk Level | How to Detect (PostHog) |
|--------|:----------:|------------------------|
| API calls drop 50%+ week-over-week | High | PostHog event trend |
| No API calls for 14+ days | Critical | PostHog inactivity cohort |
| Billing page visited 2+ times in a week | High | PostHog pageview events |
| Support tickets spike then go silent | High | HubSpot ticket data |
| Source disconnected or deleted | Critical | Product event |
| Usage consistently under 10% of plan limit | Medium | Billing data — overprovisioned |
| Dashboard login stopped | Medium | PostHog session data |

---

## Cancel Flow Design for Imgix

### The Flow

```
Cancel click → Exit survey → Dynamic offer → Confirmation → Post-cancel
```

### Exit Survey (Imgix-Specific)

| Reason | Save Offer | Fallback |
|--------|-----------|----------|
| Too expensive | Downgrade to lower usage tier | Show cost-per-image breakdown proving value |
| Not using it enough | Pause account (keep source config) | Offer free onboarding session |
| Switching to Cloudinary/competitor | Comparison data + migration friction warning | Feedback call with product team |
| Project ended / temporary | Pause 1-3 months | Downgrade to minimum tier |
| Missing feature | Roadmap preview + timeline | Submit to product feedback |
| Technical issues | Escalate to engineering support | Priority bug fix |
| Other | General retention offer | Exit gracefully |

### Imgix-Specific Save Strategies

**For "too expensive" (usage-based pricing advantage):**
- Show their actual cost-per-image vs serving unoptimized images directly from S3
- Calculate bandwidth savings: "You saved X GB of bandwidth this month, worth $Y on CloudFront alone"
- Offer to right-size their plan if they're overprovisioned
- Show performance impact: "Your average image load time went from Xms to Yms with Imgix"

**For "switching to competitor":**
- Don't disparage — show honest Imgix advantages (URL-based simplicity, speed, BYOS)
- Highlight migration cost: "Your X images are already configured with Imgix URL parameters"
- Offer comparison call with solutions team
- Document their specific use case to feed back to product

**For "not using it enough":**
- This is an activation failure, not a retention problem
- Route to trial-activation skill for re-onboarding
- Show what they could be doing: "You're serving images but not using auto=format — that alone saves 30-50% bandwidth"
- Offer a guided implementation session

### UI Principles
- Keep "continue cancelling" visible — no dark patterns (FTC Click-to-Cancel compliance)
- Show specific dollar savings based on their actual usage data
- Developer audience: be direct, not manipulative. Respect the decision.
- Mobile-friendly (developers cancel from phones too)

---

## Involuntary Churn: Payment Recovery

### Imgix Dunning Stack (Stripe-Based)

```
Pre-dunning → Stripe Smart Retries → Dunning emails (HubSpot) → Grace period → Hard cancel
```

### Pre-Dunning
- **Card expiry alerts:** HubSpot email 30 and 7 days before expiry
- **Stripe card updaters:** Enabled by default — auto-updates Visa/Mastercard (reduces hard declines 30-50%)
- **Pre-billing notification:** Email 5 days before charge for annual plans

### Stripe Smart Retries
Enable Stripe Smart Retries (uses ML to pick optimal retry timing). This handles soft declines automatically. Only send dunning emails after Smart Retries have exhausted.

### Dunning Email Sequence (HubSpot)

| Email | Timing | Subject | Tone |
|-------|--------|---------|------|
| 1 | Day 0 | "Your Imgix payment didn't go through" | Friendly alert |
| 2 | Day 3 | "Quick fix — update your payment to keep images flowing" | Helpful |
| 3 | Day 7 | "Your Imgix account will pause in 3 days" | Urgency |
| 4 | Day 10 | "Last chance to keep your images optimized" | Final warning |

**Dunning email rules for Imgix:**
- Direct link to Stripe billing portal (no login wall if possible)
- Show what they'll lose: "Your X sources and all URL configurations will be paused"
- Developer tone: factual, not guilt-trippy
- Plain text > designed emails for dunning
- Include support email for billing help

### Recovery Benchmarks

| Metric | Target |
|--------|:------:|
| Soft decline recovery | 70%+ |
| Hard decline recovery | 30%+ |
| Overall payment recovery | 55%+ |

---

## Proactive Retention

### Health Score Model (PostHog)

```
Health Score = (
  API call frequency    × 0.30 +
  Feature breadth       × 0.25 +   (# of unique transforms used)
  Source count           × 0.15 +   (more sources = more invested)
  Dashboard logins      × 0.15 +
  Support sentiment     × 0.15
)
```

| Score | Status | Action |
|:-----:|--------|--------|
| 80-100 | Healthy | Expansion opportunity (upsell) |
| 60-79 | Needs attention | Proactive check-in email |
| 40-59 | At risk | Intervention: re-onboarding, value demonstration |
| 0-39 | Critical | Personal outreach from account team |

### Proactive Interventions

| Trigger | Intervention |
|---------|-------------|
| Usage drop >50% for 2 weeks | "We noticed your image volume dropped — need help?" |
| No new transforms tried in 60 days | "Have you tried auto=format? It saves 30-50% bandwidth" |
| Annual renewal in 30 days | Value recap: images served, bandwidth saved, performance gains |
| NPS detractor (0-6) | Personal follow-up within 24 hours |
| Support ticket unresolved >48h | Escalation + proactive status update |

---

## Metrics

| Metric | Formula | Imgix Target |
|--------|---------|:----------:|
| Monthly churn rate | Churned / Start-of-month accounts | <2% |
| Revenue churn (net) | (Lost MRR - Expansion MRR) / Start MRR | Negative |
| Cancel flow save rate | Saved / Cancel sessions | 25-35% |
| Dunning recovery rate | Recovered / Failed payments | 55%+ |
| Pause reactivation rate | Reactivated / Paused | 60-80% |

### Cohort Analysis

Segment churn by: plan tier, tenure (30/60/90 day marks), acquisition channel, cancel reason, industry vertical. Use PostHog cohorts and HubSpot lifecycle reporting.

---

## Common Mistakes

- **No cancel flow:** Instant cancel leaves money on the table
- **Same offer for every reason:** A discount won't save someone who isn't using the product
- **Ignoring involuntary churn:** Often 30-50% of total and the easiest to fix
- **Discounts too deep:** 50%+ trains cancel-for-discount behavior
- **Dark patterns:** Hidden cancel buttons breed bad G2 reviews. Developers talk.
- **Not tracking save offer LTV:** A "saved" customer who churns 30 days later wasn't really saved

---

## Related Skills

- **Lifecycle/email-sequence** — Email framework for dunning and win-back sequences
- **Lifecycle/trial-activation** — Re-onboarding for "not using it enough" churners
- **Lifecycle/expansion-upsell** — Expansion and retention are two sides of the same coin
- **Lifecycle/customer-advocacy** — NPS detractors route to retention; promoters route to advocacy
- **Conversion/pricing-strategy** — Plan structure and annual discount strategy
- **Conversion/analytics-tracking** — Setting up churn signal events in PostHog
- **Conversion/ab-test-setup** — Testing cancel flow variations

**For detailed cancel flow patterns**: See [references/cancel-flow-patterns.md](references/cancel-flow-patterns.md)
**For dunning playbook**: See [references/dunning-playbook.md](references/dunning-playbook.md)
