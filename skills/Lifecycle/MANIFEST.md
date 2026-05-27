# Imgix Lifecycle System

**Owner:** Michelle Su
**Created:** April 17, 2026
**Last Updated:** May 27, 2026

## What This Is

This folder is a coordinated system for the full customer lifecycle — from prospect nurture through trial activation, expansion, retention, and advocacy. Covers every automated touchpoint after someone enters the funnel.

## How to Use This Folder

**When to invoke this folder:** You're building or optimizing an automated touchpoint for someone already in the funnel: prospect nurture, trial activation, expansion, churn prevention, referrals, or advocacy. Anything that's an automated email or in-product nudge for a known user belongs here.

**Context to bring:**
- The lifecycle stage (prospect, trial, active, expansion-ready, at-risk, advocate)
- The trigger event (signup, usage threshold, days since last login, failed payment)
- The audience size and segment
- The success metric (activation rate, MQL conversion, save rate, NRR)
- HubSpot access confirmed; PostHog access if the trigger is usage-based

**How the sub-skills fit together:**
- This folder has an **underlying framework + stage-specific applications.**
- email-sequence is the foundational framework. It defines how to build any multi-email automated flow in HubSpot. Other sub-skills lean on it.
- Always start with the stage-specific sub-skill (churn-prevention, referral-program, prospect-nurture, etc.). It will pull email-sequence as needed for the email mechanics.
- *Note: 4 of 7 sub-skills in this folder are planned but not built (prospect-nurture, trial-activation, expansion-upsell, customer-advocacy). For those stages today, use email-sequence directly and apply the framework manually.*

**Typical prompts:**
- "Design a churn prevention sequence for accounts that hit 50% credit usage and then went idle for 14 days."
- "Build a referral program for developer customers. Focus on code-community sharing mechanics, not 'share a link' buttons."
- "Draft a welcome sequence for new free trial users. Map emails to the activation milestones."
- "Use email-sequence to build an NPS request flow that goes to all paid accounts at 60 days."

**Output to expect:** Sequence briefs with subject lines, timing, trigger logic, audience segments, copy drafts for each email, and a HubSpot workflow spec ready for implementation.

**When NOT to use this folder (and where to go instead):**
- Cold outbound to people who haven't signed up → Acquisition/cold-email
- In-product onboarding UI (not email) → Conversion/onboarding-cro
- Marketing campaign emails (newsletters, launches) → Content + Acquisition
- Brand voice and tone questions → imgix-brand-voice (global)

## How Claude Runs this Folder

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
