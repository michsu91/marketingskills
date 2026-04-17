---
name: onboarding-cro
description: |
  Optimize Imgix's post-signup onboarding and activation flow. Use when improving time-to-value, reducing activation drop-off, designing the first-run experience, or increasing the percentage of signups who serve their first transformed image. Imgix activation path: connect storage source → configure subdomain → serve first image → apply first transformation. Also use when the user mentions "activation rate," "onboarding," "users aren't activating," "nobody completes setup," "time to value," or "users sign up but don't use the product." For signup form optimization, see signup-flow-cro. For email onboarding sequences, see Lifecycle/trial-activation.
metadata:
  version: 2.0.0
---

# Onboarding CRO for Imgix

You are an expert in user onboarding and activation for developer-focused PLG products. Your goal is to help Imgix users reach their activation moment — serving their first transformed image — as quickly as possible.

## Imgix Context

- **Product:** Visual media platform — real-time image/video processing and CDN delivery
- **Motion:** PLG — self-serve signup, usage-based pricing
- **ICP:** Developers and engineering teams
- **Activation event:** First image served through Imgix CDN with a URL transformation applied
- **Product analytics:** PostHog (funnels, cohorts, session replay)
- **Email platform:** HubSpot (onboarding email sequences)
- **Dashboard:** Imgix dashboard (where onboarding happens)

## Connected Tools

- **PostHog MCP** — Track onboarding funnel, identify drop-offs, session replays of stuck users
- **HubSpot MCP** — Trigger onboarding emails based on activation status
- **Slack MCP** — Alert on onboarding issues, share activation metrics
- **Jira MCP** — Track onboarding improvement tasks (MKTG project)

## Global Dependencies

Always load before optimizing onboarding:
- **imgix-brand-voice** — Developer-friendly, direct tone
- **product-marketing-context** — ICP, value propositions, competitive positioning

---

## Imgix Activation Path

### The Critical Steps

```
Signup → Connect Storage → Configure Source → Serve First Image → Apply First Transform
  100%       ?%                 ?%                  ?%                    ?%
```

Each step has specific friction points for developers:

### Step 1: Signup → Connect Storage Source

**What happens:** User needs to connect their existing image storage (S3, Google Cloud Storage, Azure Blob, or web folder).

**Common friction:**
- Don't know which source type to choose
- AWS IAM permissions confusion for S3
- GCS service account setup complexity
- Fear of giving third-party access to their storage

**Optimization opportunities:**
- Pre-detect likely source type from signup data (email domain, stated use case)
- Inline IAM policy template (copy-paste ready)
- "Test connection" button with clear success/failure states
- Video walkthrough for each source type (under 2 minutes)
- Web folder option as lowest-friction starter path

### Step 2: Configure Source → Subdomain

**What happens:** User sets up their Imgix subdomain (e.g., `images.example.imgix.net`).

**Common friction:**
- Decision paralysis on naming
- DNS configuration for custom domains
- Not understanding the URL structure

**Optimization opportunities:**
- Auto-suggest subdomain based on company name
- Show example URL immediately: `https://[your-name].imgix.net/photo.jpg`
- Defer custom domain setup to later (don't block activation)

### Step 3: Serve First Image

**What happens:** User makes their first request to Imgix CDN to serve an image from their connected source.

**Common friction:**
- Not sure which image URL to try
- Typo in image path
- Source not synced yet
- Unclear if it's "working"

**Optimization opportunities:**
- Auto-browse their source and show available images
- One-click "try this image" with a real URL from their source
- Clear loading/success states
- Show before/after: original vs. Imgix-served (with size comparison)

### Step 4: Apply First Transformation

**What happens:** User adds URL parameters to transform an image (resize, crop, format conversion).

**Common friction:**
- Don't know what parameters are available
- Syntax uncertainty
- Can't see the result immediately

**Optimization opportunities:**
- Interactive sandbox: drag sliders, see URL update live
- Pre-built "recipes" — "Responsive thumbnail: `?w=400&h=300&fit=crop&auto=format`"
- Show URL + visual result side by side
- Copy-paste ready code snippet for their framework (React, Next.js, etc.)

---

## Onboarding Checklist Design

### Recommended Items (4-5 Steps)

1. **Connect your first source** — Link S3, GCS, or web folder
2. **Serve your first image** — See it delivered through Imgix CDN
3. **Try a transformation** — Resize, crop, or auto-format an image
4. **Install the SDK** — Add Imgix to your codebase (optional but recommended)
5. **Invite a teammate** — Share access with your team (optional)

### Checklist Principles

- Start with quick wins (web folder source = fastest)
- Show progress percentage
- Celebrate completion of each step (brief, not cheesy — developers don't want confetti)
- Link each item to relevant docs
- Allow dismissal (don't trap users who know what they're doing)
- Persist across sessions (pick up where they left off)

---

## Empty States

### Dashboard with No Sources

**Bad:** "You have no sources. Add a source to get started."

**Good:**
```
Your images, optimized and delivered fast.

Connect your image storage and Imgix handles the rest —
resizing, cropping, format conversion, and global CDN delivery.

[Connect S3 bucket]  [Connect GCS]  [Use a web folder]

Not sure which? Web folder is the fastest way to try Imgix.
```

### Source Connected but No Images Served

```
Your source is connected. Try your first image:

https://[source].imgix.net/[path-to-image]?w=800&auto=format

[Browse your images]  [Try the sandbox]
```

---

## Multi-Channel Onboarding

### Email + In-App Coordination (HubSpot + Dashboard)

| Trigger | Email | In-App |
|---------|-------|--------|
| Signup (immediate) | Welcome + quickstart link | Onboarding checklist |
| No source after 24h | "Connect your images in 2 minutes" + guide | Persistent banner |
| Source connected, no image served | "Try your first transformation" + URL example | Sandbox prompt |
| First transform applied | Celebration + "What's next" (auto=format, fit=crop) | Feature discovery tooltips |
| No activity for 7 days | Re-engagement: "Your source is waiting" | Welcome back + resume |
| Activated (all steps) | SDK installation guide for their language | Checklist complete state |

### Email Principles (from imgix-brand-voice)

- Lead with code examples, not marketing copy
- Show the URL transformation inline in the email
- Link to docs, not landing pages
- Keep under 100 words for onboarding emails
- Send from a real person at Imgix, not "noreply"

---

## Handling Stalled Users

### Detection (PostHog Cohorts)

| Stalled State | Definition | Intervention |
|--------------|-----------|-------------|
| No source (48h+) | Signup but no `source_connected` event | Email + in-app guide |
| Source but no image (72h+) | `source_connected` but no `first_image_served` | Email with try-it URL |
| Image but no transform (7d+) | `first_image_served` but no `first_transform_applied` | Email with transformation recipes |
| Dashboard abandoned (14d+) | No `dashboard_login` in 14 days | Re-engagement sequence |

### Re-engagement by Stall Reason

**Stuck on source connection (most common):**
- Email with step-by-step for their likely source type
- Offer a 15-minute setup call
- Suggest web folder as a quick-start alternative

**Stuck on first image:**
- Send a working URL example using their actual source
- Link to troubleshooting docs
- Offer to check their source configuration

**Didn't try transforms:**
- Send 3 transformation recipes (resize, smart crop, auto-format)
- Link to interactive sandbox
- Show bandwidth savings they're missing

---

## Measurement

### Key Metrics (PostHog)

| Metric | Description | Target |
|--------|-------------|:------:|
| Signup → Source connected | % who connect within 7 days | Track & improve |
| Source → First image | % who serve first image within 48h | Track & improve |
| First image → First transform | % who apply transform within 7 days | Track & improve |
| Overall activation rate | Signup → first transform within 14 days | Track & improve |
| Time to activation | Median time from signup to first transform | Reduce |
| Day 1 / Day 7 / Day 30 retention | Return rate by timeframe | Track & improve |

### Funnel Analysis in PostHog

Build these funnels:
1. **Full activation funnel** — signup → source → image → transform
2. **Source connection funnel** — by source type (S3 vs GCS vs web folder)
3. **Time-to-activation** — distribution of hours/days to each step
4. **Activation by cohort** — by signup source, company size, use case

### Session Replay

Use PostHog session replays filtered to:
- Users who started but didn't complete source setup
- Users who visited billing page during onboarding (potential pricing confusion)
- Users who visited docs multiple times during a single onboarding session (potential UX issues)

---

## Experiment Ideas for Imgix Onboarding

| Experiment | Primary Metric |
|-----------|---------------|
| Guided setup wizard vs. self-service dashboard | Activation rate |
| Web folder first (easiest) vs. S3 first (most common) | Source connection rate |
| Interactive sandbox in onboarding vs. docs link | First transform rate |
| Video walkthrough vs. text guide for source setup | Source connection rate |
| Simplified IAM policy template vs. full instructions | S3 connection rate |
| Checklist with 4 items vs. 6 items | Completion rate |
| Personal welcome email from founder vs. automated | Day 7 retention |

---

## Related Skills

- **Conversion/signup-flow-cro** — Optimizing the signup that precedes onboarding
- **Conversion/ab-test-setup** — Testing onboarding changes in PostHog
- **Conversion/analytics-tracking** — Setting up activation events
- **Lifecycle/trial-activation** — Email sequences for activation
- **Lifecycle/email-sequence** — Email framework for onboarding drips
- **Lifecycle/churn-prevention** — "Not using it enough" churners get re-routed here
- **imgix-brand-voice** (global) — Onboarding copy follows brand guidelines
