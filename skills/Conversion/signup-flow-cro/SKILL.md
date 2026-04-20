---
name: signup-flow-cro
description: |
  Optimize Imgix's self-serve signup and registration flow. Use when reducing signup abandonment, testing signup variations, adding auth methods, or improving the visitor-to-signup conversion. Imgix is PLG with a developer audience — signup should be fast, minimal, and developer-friendly (GitHub auth, no credit card, minimal fields). Also use when the user mentions "signup conversions," "registration friction," "signup form," "people aren't signing up," "signup abandonment," "too many steps to sign up," or "simplify our signup." For post-signup onboarding, see onboarding-cro. For marketing page optimization, see page-cro.
metadata:
  version: 2.0.0
---

# Signup Flow CRO for Imgix

You are an expert in optimizing signup flows for developer-focused PLG products. Your goal is to reduce friction, increase completion rates, and set developers up for successful activation after they create an Imgix account.

## Imgix Context

- **Product:** Visual media platform — real-time image/video processing and CDN delivery
- **Motion:** PLG — self-serve signup, free trial, no credit card required
- **ICP:** Developers and engineering teams
- **Website:** Webflow (signup page)
- **Product analytics:** PostHog (signup funnel, field-level tracking, session replay)
- **Auth:** Email + password, Google auth, GitHub auth (developer audience expects GitHub)
- **Post-signup:** Dashboard → connect storage source → configure → serve first image
- **No credit card required:** Critical for PLG — must be prominently stated

## Connected Tools

- **PostHog MCP** — Signup funnel analytics, field drop-off, session replays, experiments
- **Webflow MCP** — Modify signup page on imgix.com
- **HubSpot MCP** — Lead capture, lifecycle tracking post-signup
- **Jira MCP** — Track signup optimization tasks (MKTG project)

## Global Dependencies

Always load before signup optimization:
- **imgix-brand-voice** — Direct, developer-friendly tone
- **product-marketing-context** — ICP, positioning, value propositions

---

## Imgix Signup Flow Principles

### 1. Developers Value Speed

Developers evaluate dozens of tools. If signup takes more than 30 seconds, they'll try a competitor instead. Every field, every step, every second counts.

### 2. GitHub Auth Is Expected

Developer tools that don't offer GitHub authentication signal "this isn't built for developers." GitHub auth should be prominently available, alongside Google.

### 3. No Credit Card = No Friction

"No credit card required" must be visible near the signup CTA. This is non-negotiable for PLG developer tools. Developers will not enter payment info to evaluate.

### 4. Show What's Next

After signup, developers want to know: "What do I do now?" The signup flow should set expectations for the onboarding path (connect source → serve first image).

---

## Recommended Signup Flow for Imgix

### Ideal Flow (Minimal Friction)

```
Landing Page → Signup Page → Dashboard (onboarding begins)
```

### Signup Page Layout

**Above the fold:**
1. Headline: Brief value reinforcement ("Start optimizing your images")
2. Social auth buttons (prominent):
   - [Sign up with GitHub]
   - [Sign up with Google]
3. Divider: "or"
4. Email + password form (2 fields)
5. Submit: "Create free account"
6. Below button: "No credit card required. Free up to X images/month."
7. Login link: "Already have an account? Log in"

**Supporting elements (below fold or sidebar):**
- Customer logos (Porsche, Unsplash, Skims)
- Quick stat: "8B+ images optimized daily"
- "Takes less than 30 seconds"

### Field Priority

| Field | Required at Signup? | Rationale |
|-------|:------------------:|-----------|
| Email | Yes | Account identifier |
| Password | Yes (unless social auth) | Account security |
| Full name | No — defer | Collect during onboarding or first source setup |
| Company name | No — defer | Infer from email domain, ask later |
| Role | No — defer | Progressive profiling after activation |
| Team size | No — defer | Enterprise qualification can happen post-signup |
| Use case | No — defer | Ask during onboarding to personalize experience |
| Phone | No — never at signup | Developers will abandon |

### Social Auth Configuration

**GitHub (primary for developers):**
- Request minimal permissions (email, profile)
- Auto-create account with GitHub email
- Display GitHub avatar in dashboard

**Google (secondary):**
- Standard Google OAuth
- Common for developers using Google Workspace

**Why not others:**
- Microsoft: Only add if enterprise signups justify it
- Apple: Low priority for B2B developer audience
- SSO/SAML: Enterprise tier feature, not signup flow

---

## Signup Page Optimization

### Trust Signals

Place near the signup form:
- "No credit card required" (most important)
- "Free forever up to X images/month"
- Customer logos (recognizable tech brands)
- "Set up in under 2 minutes"
- SOC 2 or security badge if applicable

### Error Handling

- Inline validation as user types (email format, password strength)
- "Email already registered" → show login link + password reset
- Password requirements visible before first keystroke
- Don't clear form on error
- Specific, helpful error messages in developer-friendly language

### Mobile Optimization

- Social auth buttons full-width (easy touch targets)
- Single column layout
- Appropriate keyboard types (email keyboard for email field)
- Autofill support enabled
- No CAPTCHA unless absolutely necessary (friction killer)

### Post-Submit Experience

**On successful signup:**
1. Redirect immediately to dashboard (no email verification gate)
2. Send welcome email in background (HubSpot)
3. Start onboarding checklist in dashboard
4. Show first step: "Connect your image storage"

**Email verification:**
- Delay verification until it matters (before first production deployment or paid upgrade)
- Don't gate the product behind email verification
- Developers will verify when they see value, not before

---

## Signup Funnel Measurement (PostHog)

### Key Metrics

| Metric | Description | Target |
|--------|-------------|:------:|
| Page → signup started | Visitors who interact with signup form | Track & improve |
| Signup started → completed | Form completion rate | 70%+ |
| Social auth vs. email ratio | Which method developers prefer | Track (expect 40-60% social) |
| Field-level drop-off | Which fields lose people | Zero tolerance for unnecessary fields |
| Time to complete | Signup duration | < 30 seconds |
| Mobile vs. desktop completion | Platform parity | Within 10% of each other |
| Signup → activation (next day) | Post-signup quality | Track & improve |

### Events to Track (PostHog)

| Event | Properties | Trigger |
|-------|-----------|---------|
| `signup_page_viewed` | referrer, utm_source, device | Page load |
| `signup_form_focused` | first_field_focused | First field interaction |
| `signup_method_selected` | method (github/google/email) | Auth button click or email focus |
| `signup_field_error` | field_name, error_type | Validation error shown |
| `signup_completed` | method, time_to_complete, utm_source | Account created |
| `signup_abandoned` | last_field_focused, time_spent, method | Page exit without completion |

### Funnel to Build

```
signup_page_viewed → signup_form_focused → signup_method_selected → signup_completed → source_connected
```

---

## Experiment Ideas for Imgix Signup

### High Priority

| Experiment | Primary Metric | Hypothesis |
|-----------|---------------|-----------|
| GitHub auth prominence (top vs. equal with Google) | Signup completion | Developers prefer GitHub, making it primary will increase completion |
| Add "Sign up with GitHub" to homepage hero | Homepage → signup rate | Reducing steps increases conversion |
| Remove name field entirely | Signup completion | One less field = less friction |
| Show "What happens next" preview below form | Signup completion | Setting expectations reduces uncertainty |

### Medium Priority

| Experiment | Primary Metric | Hypothesis |
|-----------|---------------|-----------|
| Single-step (current) vs. two-step (email → details) | Signup completion | Progressive commitment may increase starts |
| Customer logos near form vs. not | Signup completion | Social proof increases trust at decision moment |
| "Free forever" vs. "No credit card" messaging | Signup completion | Different trust signals resonate differently |
| Auto-detect company from email domain | Post-signup activation | Pre-filling reduces friction in onboarding |

---

## Common Signup Mistakes for Developer Tools

- **Requiring company name at signup:** Infer from email domain, ask later
- **No GitHub auth:** Signals "not built for developers"
- **Credit card required for trial:** Kills PLG conversion
- **Email verification gate:** Blocks value, increases abandonment
- **CAPTCHA by default:** Add friction only if bot signups are a proven problem
- **"Tell us about your use case" at signup:** Defer to onboarding
- **Login and signup on same page:** Creates confusion, separate them
- **No indication of what's free:** Developers assume everything costs money

---

## Related Skills

- **Conversion/onboarding-cro** — Optimizing what happens after signup
- **Conversion/page-cro** — Optimizing the page that leads to signup
- **Conversion/ab-test-setup** — Testing signup flow changes in PostHog
- **Conversion/analytics-tracking** — Setting up signup event tracking
- **Lifecycle/trial-activation** — Email sequences for new signups
- **Lifecycle/email-sequence** — Welcome email framework
- **imgix-brand-voice** (global) — Signup copy follows brand guidelines
