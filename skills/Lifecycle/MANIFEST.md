# imgix Lifecycle System

**Owner:** Michelle Su
**Created:** April 17, 2026
**Last Updated:** April 17, 2026

## What This Is

This folder is a coordinated system for the full customer lifecycle — from prospect nurture through trial activation, expansion, retention, and advocacy. Covers every automated touchpoint after someone enters the funnel.

## How It Works

1. **Read this MANIFEST.md** to understand the system and current priorities
2. **Read MEMORY.md** for accumulated context from previous sessions
3. **Always load global skills first:** `imgix-brand-voice` and `product-marketing-context`
4. **Check each subfolder's STATUS.md** for current state
5. **Execute work** using the SKILL.md in the relevant subfolder
6. **Update STATUS.md and MEMORY.md** when work is completed
7. **Report results** via Slack to Michelle

## Connected Tools (MCP)

- **HubSpot** — Email sequences, lifecycle stages, lead scoring, automation
- **PostHog** — Usage-based triggers, activation events, churn signals
- **Jira** — Track lifecycle optimization tasks (MKTG project)
- **Slack** — Alert on churn risk, celebrate advocacy wins

## Global Dependencies

- **imgix-brand-voice** — All email and messaging follows brand tone
- **product-marketing-context** — Value props inform lifecycle messaging

## Subfolders (Ordered by Customer Journey)

### 1. `prospect-nurture/` — TOP OF FUNNEL *(planned)*
MQL→SQL email nurture flows. Lead scoring triggers. Content-based nurture sequences that move prospects toward signup.

### 2. `email-sequence/` — GENERAL EMAIL DESIGN
Framework for designing any multi-email sequence — nurture, onboarding, re-engagement, drip campaigns. The "how to build emails" skill used by other lifecycle skills.

### 3. `trial-activation/` — POST-SIGNUP *(planned)*
PLG activation emails and in-app nudges. Usage-based triggers that guide new users to their "aha moment." Time-to-value optimization.

### 4. `expansion-upsell/` — GROWTH *(planned)*
Usage threshold triggers, plan upgrade flows, and expansion playbooks. Identify when accounts are ready to grow and nudge them at the right moment.

### 5. `churn-prevention/` — RETENTION
Cancellation flows, save offers, dunning/failed payment recovery, exit surveys, and win-back campaigns. Keep existing customers.

### 6. `customer-advocacy/` — ADVOCACY *(planned)*
NPS programs, G2/Capterra review requests, testimonial collection, and referral asks. Turn happy customers into vocal advocates.

### 7. `referral-program/` — REFERRAL
Referral and affiliate programs. Leverage existing customers to bring in new ones. The end of one customer's lifecycle becomes the start of another's.

## Cross-System References

- **Conversion → Lifecycle:** After signup and activation (Conversion), Lifecycle takes over the relationship.
- **Lifecycle → Acquisition:** Referral programs and advocacy generate new leads for Acquisition.
- **Product-Marketing → Lifecycle:** Customer research and positioning inform lifecycle messaging.
- **Content → Lifecycle:** Email content and case studies are created by the Content system.

## The PLG Lifecycle Loop

```
Prospect → Nurture → Signup → Activate → Use → Expand → Retain → Advocate → Refer
   ↑                                                                           |
   └───────────────────────────────────────────────────────────────────────────┘
```

Every skill in this system maps to a stage in this loop. The goal is automated, data-driven touchpoints at every transition.

## Definition of Done

This system is successful when:
- Every lifecycle stage has at least one automated email sequence
- Trial-to-activation rate improves 15%+ from baseline
- Net revenue retention increases (expansion > churn)
- NPS program active with quarterly measurement
- Referral program driving measurable new signups
