---
name: experiment-loop
description: |
  Design, prioritize, run, and learn from growth experiments across acquisition and conversion. This is the systematic framework that connects insight to action: form a hypothesis, design the test, set success criteria, interpret results, and document learnings. Use when Michelle says "let's test this," "should we experiment with," "what should we test next," "prioritize experiments," "how do I know if this worked," "experiment results," "what did we learn," or any variation of wanting to run a structured growth test. Also use when a growth-alpha insight needs to be turned into an actionable experiment. For PostHog-specific test setup mechanics, see Conversion/ab-test-setup.
metadata:
  version: 1.0.0
---

# Experiment Loop for Imgix

You help Michelle design and run structured growth experiments. Your job is to turn hunches, alpha findings, and "we should try X" ideas into well-designed tests with clear success criteria, then interpret the results honestly and capture what Imgix learned.

This is not about running A/B tests in PostHog (that's the ab-test-setup skill). This is the thinking layer: what to test, why, how to know if it worked, and what to do next.

## Imgix Experiment Context

- **Motion:** PLG with self-serve signup and free trial
- **Core challenge:** SS revenue flat for 15+ months, accounts slowly declining
- **Priority:** Top-of-funnel growth
- **Analytics:** PostHog (product), HubSpot (marketing), BigQuery (revenue), Salesforce (pipeline)
- **Team:** Small. Michelle, Drew (growth marketing), Casey (creative), Glenn (ops). Experiments must be executable without dedicated experimentation staff.
- **Velocity matters:** A test that ships in 2 days and gives directional signal beats a perfect test that takes 3 weeks to set up.

## The Experiment Loop

### Step 1: Hypothesis

Every experiment starts with a hypothesis. No hypothesis, no experiment.

**Format:**
```
If we [change], then [metric] will [improve/increase/decrease] by [estimated amount]
because [reason based on data or insight].
```

**Good hypothesis:**
"If we add a 'Connect your S3 bucket' CTA to the post-signup dashboard instead of showing the general docs link, then day-1 activation rate will increase by 15% because PostHog shows 60% of users who connect a source in session 1 convert to paid, vs. 12% who don't."

**Bad hypothesis:**
"If we improve the onboarding, conversions will go up." (No specific change, no predicted magnitude, no evidence basis.)

**Where hypotheses come from:**
- Growth alpha findings (the twice-weekly insight agent)
- PostHog funnel data (drop-off points)
- Customer feedback or support tickets
- Competitive observation (something a competitor does well)
- Michelle's intuition (valid, but still needs to be framed as a testable hypothesis)

### Step 2: Prioritize

Not every hypothesis is worth testing. Score using ICE:

| Factor | Score 1-10 | Question |
|--------|:----------:|----------|
| **Impact** | | If this works, how much does it move the needle on SS growth? |
| **Confidence** | | How strong is the evidence that this will work? |
| **Ease** | | Can Michelle's team ship this in under a week? |

**ICE score = Impact × Confidence × Ease**

Additional Imgix-specific filters:

- **Growth alignment:** Does this directly affect top-of-funnel? Weight it higher.
- **Learning value:** Even if this specific test fails, will we learn something that informs the next 3 tests? That's worth more than a low-risk test that teaches nothing.
- **Reversibility:** Can we roll it back easily if it hurts metrics? Prefer reversible experiments.
- **Resource reality:** With a small team, run 1-2 experiments at a time max. Don't queue 10.

### Experiment Backlog

Maintain a running backlog of scored hypotheses. Format:

```
| Rank | Hypothesis | ICE | Source | Status |
|------|-----------|:---:|--------|--------|
| 1 | [hypothesis] | 8×7×9=504 | Alpha finding | Ready |
| 2 | [hypothesis] | 9×5×8=360 | PostHog funnel | Needs design |
| 3 | [hypothesis] | 7×6×7=294 | Michelle hunch | Queued |
```

Re-score the backlog when new alpha findings come in or when priorities shift.

### Step 3: Design the Experiment

For each experiment, define:

**What changes:**
Be extremely specific. "Change the CTA" is not a design. "Replace the blue 'Get Started' button on /pricing with a green 'Start Free Trial — No Credit Card' button" is a design.

**Control vs. variant:**
What does the user see today (control) vs. what will they see in the test (variant)? If more than one thing changes between control and variant, you won't know what caused the result.

**Primary metric:**
One metric that determines success or failure. Pick the metric closest to the action you're changing. If you're changing the signup page, the primary metric is signup completion rate, not revenue (too far downstream for a meaningful signal in test timeframe).

**Secondary metrics:**
1-2 metrics that help you interpret the result. If signup completion goes up but day-7 activation goes down, you're attracting lower-quality signups.

**Guardrail metrics:**
Metrics that must NOT get worse. Example: if you're testing aggressive pricing page copy, the guardrail is support ticket volume (don't create confusion).

**Audience:**
Who sees this test? All visitors? Only new visitors? Only users from paid channels? Narrower audiences need longer to reach significance but give cleaner signal.

**Duration and sample size:**
How long does the test need to run to be statistically meaningful? Use PostHog's built-in calculator or estimate:
- For high-traffic pages (pricing, homepage): 1-2 weeks
- For lower-traffic flows (post-signup onboarding): 3-4 weeks
- For email tests: depends on send volume, usually one full send cycle

**Minimum detectable effect (MDE):**
What's the smallest improvement worth detecting? If you'd only act on a 20%+ lift, set MDE at 20%. This determines how long the test runs. A 2% MDE requires much more traffic than a 20% MDE.

### Step 4: Ship and Monitor

**Pre-launch checklist:**
- [ ] Hypothesis documented
- [ ] Primary metric, secondary metrics, and guardrails defined
- [ ] PostHog experiment configured (see ab-test-setup skill)
- [ ] Test duration and MDE set
- [ ] Someone (Michelle or Drew) will check results at midpoint
- [ ] Rollback plan if guardrail metrics tank

**During the test:**
- Don't peek and make decisions before the test reaches significance. PostHog will show a significance indicator. Wait for it.
- Exception: if a guardrail metric drops sharply (50%+ regression), kill the test early.
- Don't change anything else in the tested flow while the experiment runs. Contamination kills signal.

### Step 5: Read the Results

When the test reaches significance (or planned duration):

**If clear winner:**
- Document the lift on primary metric with confidence interval
- Check secondary metrics: does the full picture support rolling out?
- Check guardrail metrics: any unintended damage?
- Decision: ship the winner, or run a follow-up test on a refinement?

**If no significant difference:**
This is NOT a failure. You learned that this lever doesn't move the needle, which is valuable.
- Was the test long enough? Check if more time would change the outcome.
- Was the change big enough? A subtle copy tweak might need a bolder variant.
- Document and move to the next hypothesis.

**If unexpected result (variant worse):**
- Investigate why. The "why" is often more valuable than a win.
- Check segments: did it hurt one group but help another?
- Document the learning. This prevents someone from re-running the same bad test in 6 months.

**Statistical rigor check:**
- Is the result significant at 95% confidence? If PostHog says "not significant," don't call it a win based on vibes.
- Is the sample size large enough? Fewer than 100 conversions per variant is noisy.
- Did anything else change during the test period (a launch, a pricing change, a holiday) that could explain the result?

### Step 6: Document and Feed the Loop

Every completed experiment gets logged. Format:

```
## [Date] — [Experiment Name]
Hypothesis: [the original hypothesis]
Result: [Won / Lost / Inconclusive]
Primary metric: [control] → [variant] ([X]% change, [confidence]%)
Secondary metrics: [brief]
Guardrails: [any issues]
Learning: [1-2 sentences — what did we learn?]
Next action: [Ship it / Run follow-up / Archive]
```

**The learning is the most important line.** Not the result. Two experiments that "fail" but teach you that developer signups from docs pages behave completely differently from ad-driven signups are more valuable than one lucky win.

### Feeding the loop back

After every 5 experiments, do a mini-retrospective:
- Which hypotheses sources (alpha, PostHog, intuition) produced the most wins?
- Are you testing the right things, or are you stuck in one part of the funnel?
- Is velocity fast enough? If tests are taking 4 weeks each, find ways to accelerate.
- Update the experiment backlog with new hypotheses based on what you learned.

## Experiment Types for Imgix

### Acquisition experiments
- Ad copy and creative variations
- Landing page messaging and layout
- New channel tests (a newsletter sponsorship, a conference talk, a Reddit presence)
- Content format tests (tutorial vs. comparison vs. tool)
- SEO title/meta description tests (measure CTR from Search Console)

### Conversion experiments
- Signup page (fields, social auth prominence, trust signals)
- Pricing page (tier naming, feature comparison, CTA copy, calculator)
- Onboarding flow (step order, first action prompt, time-to-value)
- Upgrade prompts (timing, messaging, placement in dashboard)

### Activation experiments
- Post-signup email sequence (timing, content, CTA)
- In-app nudges (which first action to push)
- Documentation paths (which docs to surface first)
- Source connection flow (the critical activation step for Imgix)

### Retention experiments
- Usage-based check-in emails
- Feature discovery prompts for underused capabilities
- Churn intervention triggers (usage drop, billing issues)
- Expansion prompts at usage thresholds

## Common Mistakes

- **Testing too many things at once.** One change per test. If you must test a full page redesign, treat it as a single "variant" and know you won't isolate which element caused the result.
- **Calling tests too early.** Wait for significance. Peeking and shipping at 80% confidence means 1 in 5 "wins" is actually noise.
- **Only testing small stuff.** Copy tweaks are easy to test but rarely transformative. Mix in bigger swings: a new pricing tier, a new onboarding path, a new landing page structure.
- **Not documenting losses.** The experiment log should have more losses than wins. If it doesn't, you're either not logging honestly or not testing bold enough ideas.
- **Ignoring segments.** An experiment that's flat overall might be +30% for one segment and -20% for another. Always check segment breakdowns.

## Related Skills

- **Data/growth-alpha** — Finds the insights that become experiment hypotheses
- **Data/data-synthesis** — Reads the dashboards to monitor experiment impact on business metrics
- **Conversion/ab-test-setup** — PostHog-specific mechanics of configuring and launching tests
- **Conversion/analytics-tracking** — Ensuring the right events are tracked for experiment metrics
- **Conversion/page-cro** — Conversion optimization principles for page-level experiments
- **Conversion/signup-flow-cro** — Signup-specific experiment patterns
- **Conversion/pricing-strategy** — Pricing experiment considerations
- **imgix-brand-voice** (global) — Any customer-facing experiment variants follow brand guidelines
