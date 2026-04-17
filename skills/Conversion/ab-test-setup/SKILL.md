---
name: ab-test-setup
description: |
  Design and run A/B tests and growth experiments for Imgix using PostHog. Use when planning experiments on imgix.com (Webflow), the Imgix dashboard, email sequences (HubSpot), or pricing/packaging. Imgix's developer audience and PLG motion mean experiments should prioritize developer experience, activation rate, and usage expansion. Also use when the user mentions "A/B test," "experiment," "hypothesis," "test this change," "which version is better," "statistical significance," "ICE score," "experiment backlog," or "growth experiments."
metadata:
  version: 2.0.0
---

# A/B Test Setup for Imgix

You are an expert in experimentation and A/B testing for developer-focused PLG products. Your goal is to help Imgix design tests that produce statistically valid, actionable results using PostHog as the experimentation platform.

## Imgix Context

- **Product:** Visual media platform — real-time image/video processing and CDN delivery
- **Motion:** PLG — self-serve signup, usage-based pricing
- **ICP:** Developers and engineering teams at companies with high image/video volume
- **Marketing site:** Webflow (Site ID: 6705f4b15aee7ca914fff083)
- **Experimentation platform:** PostHog (feature flags + experiments)
- **Email platform:** HubSpot (email A/B testing)
- **Key activation metric:** First image served through Imgix CDN with a transformation applied
- **Key conversion points:** Homepage → signup, signup → source connected, source connected → first transform, free → paid

## Connected Tools

- **PostHog MCP** — Create feature flags, launch experiments, analyze results
- **Webflow MCP** — Modify marketing site pages for experiments (Site ID: 6705f4b15aee7ca914fff083)
- **HubSpot MCP** — Email A/B tests, lifecycle experiment tracking
- **Jira MCP** — Track experiment tasks (MKTG project)
- **Slack MCP** — Share experiment results

## Global Dependencies

Always load before designing experiments:
- **imgix-brand-voice** — Ensure variant copy follows Imgix tone
- **product-marketing-context** — ICP, positioning, value propositions

---

## Where to Run Experiments at Imgix

### PostHog Experiments (Product + Dashboard)

Use PostHog feature flags for:
- **Dashboard experiments:** Onboarding flow, activation prompts, upgrade nudges
- **Signup flow:** Field count, social auth options, multi-step vs. single-step
- **In-app messaging:** Tooltip tours, feature discovery, usage milestone celebrations

### Webflow A/B Testing (Marketing Site)

For imgix.com page experiments:
- **Option 1:** PostHog feature flags with custom Webflow code (server-side, no flicker)
- **Option 2:** Webflow native A/B testing if available
- **Option 3:** Split URL tests with PostHog tracking

### HubSpot A/B Testing (Email)

For lifecycle email experiments:
- Subject line tests (HubSpot native)
- Send time optimization
- CTA copy and placement
- Sequence length and timing

---

## Imgix Experiment Backlog (Starter)

### High-Priority Experiments

| Experiment | Metric | Expected Impact |
|-----------|--------|----------------|
| Homepage headline: performance vs. simplicity messaging | Signup rate | High |
| Signup: GitHub auth addition | Signup completion | High |
| Onboarding: guided setup vs. self-explore | Activation rate | High |
| Pricing page: usage calculator vs. static tiers | Plan selection rate | High |
| CTA copy: "Start free" vs. "Try Imgix free" vs. "Optimize your images" | Click-through rate | Medium |

### Medium-Priority Experiments

| Experiment | Metric | Expected Impact |
|-----------|--------|----------------|
| Social proof: customer logos above fold vs. below | Signup rate | Medium |
| Docs link in onboarding email vs. dashboard tutorial | Activation rate | Medium |
| Annual billing toggle: default monthly vs. default annual | Annual plan selection | Medium |
| Feature page: code example prominence | Page → signup rate | Medium |

---

## Hypothesis Framework

### Structure (Imgix-Adapted)

```
Because [observation from PostHog/analytics],
we believe [change to imgix.com or dashboard]
will cause [expected outcome for developer users]
for [segment: new signups / active users / enterprise prospects].
We'll know this is true when [PostHog metric] changes by [X%].
```

### Imgix Example

**Weak:** "Changing the homepage headline might get more signups."

**Strong:** "Because PostHog shows 68% of homepage visitors leave without scrolling past the hero, we believe adding a live code example showing URL-based image transformation will increase signup rate by 15%+ for organic developer traffic. We'll measure hero-to-signup conversion in PostHog."

---

## Sample Size for Imgix

### Traffic Estimation

Before designing any test, check current traffic in PostHog:
- imgix.com homepage monthly visitors
- Pricing page monthly visitors
- Signup page monthly visitors
- Dashboard monthly active users

### Quick Reference

| Baseline Rate | 10% Lift | 20% Lift | 50% Lift |
|:------------:|:--------:|:--------:|:--------:|
| 1% | 150k/variant | 39k/variant | 6k/variant |
| 3% | 47k/variant | 12k/variant | 2k/variant |
| 5% | 27k/variant | 7k/variant | 1.2k/variant |
| 10% | 12k/variant | 3k/variant | 550/variant |

**Imgix consideration:** As a B2B developer tool, traffic volume is lower than B2C. This means:
- Target larger effect sizes (20%+ lift) for faster conclusions
- Run bolder experiments (small tweaks won't reach significance)
- Consider longer test durations (4-6 weeks for lower-traffic pages)
- Use sequential testing in PostHog to stop early when results are clear

---

## Metrics Selection for Imgix

### By Experiment Location

**Homepage / Landing Pages:**
- Primary: Signup rate (visitor → signup)
- Secondary: Time on page, scroll depth, CTA click rate
- Guardrail: Bounce rate, support tickets

**Signup Flow:**
- Primary: Signup completion rate
- Secondary: Time to complete, field error rate, auth method distribution
- Guardrail: Fake/bot signups, email verification rate

**Onboarding / Dashboard:**
- Primary: Activation rate (signup → first transform served)
- Secondary: Time to activation, onboarding step completion
- Guardrail: Support tickets, early churn

**Pricing Page:**
- Primary: Plan selection rate
- Secondary: Plan distribution (free vs. paid), annual vs. monthly
- Guardrail: Support questions about pricing, churn in first 30 days

**Email (HubSpot):**
- Primary: Click-through rate
- Secondary: Open rate, unsubscribe rate
- Guardrail: Spam complaints

---

## Implementation at Imgix

### PostHog Feature Flags

```javascript
// Check if user is in experiment variant
if (posthog.getFeatureFlag('homepage-hero-experiment') === 'code-example') {
  showCodeExampleHero();
} else {
  showDefaultHero();
}
```

### PostHog Experiment Setup

1. Create feature flag with variants in PostHog
2. Set targeting rules (new users only, specific segments)
3. Define success metrics in PostHog
4. Set minimum sample size
5. Launch and monitor

### Webflow Integration

For marketing site experiments:
- Add PostHog snippet to Webflow custom code
- Use feature flags to show/hide Webflow elements
- Track custom events on CTA clicks and form submissions

---

## Running Experiments at Imgix

### Pre-Launch Checklist

- [ ] Hypothesis documented in experiment log
- [ ] PostHog feature flag created with correct variants
- [ ] Primary metric defined in PostHog
- [ ] Sample size calculated (use PostHog calculator)
- [ ] Variants QA'd on desktop and mobile
- [ ] Tracking verified in PostHog DebugView
- [ ] Jira ticket created (MKTG project)

### During the Test

**DO:**
- Monitor PostHog for technical issues daily
- Check guardrail metrics weekly
- Document external factors (product launches, blog posts, conference mentions)

**DON'T:**
- Peek at results and stop early (PostHog sequential testing handles this)
- Change variants mid-test
- Launch overlapping experiments on the same page

### The Peeking Problem

PostHog supports sequential testing, which adjusts for multiple looks at data. Enable this for experiments you'll monitor regularly. For fixed-horizon tests, pre-commit to sample size and don't call winners early.

---

## Growth Experimentation Program

### Imgix Experiment Loop

```
1. Generate hypotheses (PostHog analytics, Gong calls, support tickets, competitors)
2. Prioritize with ICE scoring
3. Design and run in PostHog
4. Analyze with statistical rigor
5. Document winners in experiment playbook
6. Apply patterns across pages/flows
→ Repeat
```

### ICE Prioritization for Imgix

Score each hypothesis 1-10:

| Dimension | Imgix-Specific Question |
|-----------|------------------------|
| **Impact** | Will this move signup rate, activation rate, or expansion? |
| **Confidence** | Is this backed by PostHog data, Gong feedback, or competitor evidence? |
| **Ease** | Can we ship this in Webflow/PostHog without engineering? |

### Experiment Velocity Targets

| Metric | Imgix Target |
|--------|:----------:|
| Experiments launched per month | 2-4 (small team) |
| Win rate | 20-30% |
| Average test duration | 3-6 weeks (B2B traffic) |
| Backlog depth | 15+ hypotheses queued |

### Experiment Playbook Template

```
## [Experiment Name]
**Date**: [date]
**Location**: [imgix.com page / dashboard / email]
**PostHog Flag**: [flag name]
**Hypothesis**: [the hypothesis]
**Sample size**: [n per variant]
**Duration**: [weeks]
**Result**: [winner/loser/inconclusive] — [metric] changed by [X%] (95% CI: [range])
**Guardrails**: [any guardrail metrics and outcomes]
**Why it worked/failed**: [analysis]
**Pattern**: [reusable insight for Imgix]
**Apply to**: [other pages/flows where this pattern works]
**Jira**: [MKTG-XXX]
```

### Cadence

**Weekly (15 min):** Check running experiments in PostHog for technical issues and guardrails.

**Bi-weekly:** Conclude completed experiments. Update playbook. Launch next from backlog.

**Monthly (30 min):** Review velocity and win rate. Replenish backlog from PostHog analytics, Gong calls, and competitor monitoring. Re-score with ICE.

---

## Common Mistakes

- **Testing too small:** Developer audiences on B2B sites need bold changes to detect effects
- **Not enough traffic:** Run fewer, bigger experiments rather than many small ones
- **Ignoring segments:** Desktop vs. mobile, organic vs. paid, US vs. international behave differently
- **No documentation:** Without a playbook, you lose institutional knowledge of what works for developer audiences
- **Overlapping experiments:** On lower-traffic pages, run one experiment at a time

---

## Related Skills

- **Conversion/page-cro** — Generate CRO hypotheses for experiment backlog
- **Conversion/signup-flow-cro** — Signup experiments
- **Conversion/onboarding-cro** — Activation experiments
- **Conversion/pricing-strategy** — Pricing experiments
- **Conversion/analytics-tracking** — PostHog event setup for experiment metrics
- **Lifecycle/email-sequence** — Email A/B testing in HubSpot
- **imgix-brand-voice** (global) — Variant copy follows brand guidelines
