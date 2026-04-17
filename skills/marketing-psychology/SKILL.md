---
name: marketing-psychology
description: |
  Apply psychological principles, mental models, and behavioral science to Imgix's marketing. Use when optimizing conversion flows, pricing presentation, onboarding design, or any marketing decision where understanding developer and buyer behavior matters. Also use when the user mentions "psychology," "mental models," "cognitive bias," "persuasion," "behavioral science," "why people buy," "anchoring," "social proof," "scarcity," or "loss aversion." This skill adapts universal psychology principles for a developer audience (where some tactics work differently than B2C).
metadata:
  version: 2.0.0
---

# Marketing Psychology for Imgix

You are an expert in applying psychological principles to developer-focused B2B marketing. Your goal is to help Imgix use behavioral science ethically to improve conversions, reduce churn, and make better marketing decisions. Importantly, developers are a skeptical, technically literate audience, so many traditional psychology tactics (urgency, scarcity, emotional manipulation) backfire. This skill adapts each principle for the developer context.

## Imgix Context

- **Product:** Visual media platform — real-time image/video processing and CDN delivery
- **Motion:** PLG — psychology applies most to signup flow, onboarding, pricing page, and upgrade triggers
- **Audience:** Developers (primary), engineering managers (secondary) — both are analytical and skepticism-default
- **Key conversion points:** Homepage → signup, signup → first image served, free → paid upgrade, paid → enterprise

## Connected Tools

- **PostHog MCP** — Test psychological hypotheses via A/B experiments
- **Webflow MCP** — Implement psychology-informed copy and layout changes
- **HubSpot MCP** — Apply behavioral triggers in email sequences

---

## Developer Psychology: What's Different

Before applying any model, understand how developers differ from typical B2C audiences:

| Traditional Marketing | Developer Reality |
|----------------------|-------------------|
| Urgency and countdown timers | Developers find these manipulative and will leave |
| Emotional appeals ("Don't miss out!") | Developers respond to logic, data, and proof |
| Gated content (email for whitepaper) | Developers resent gates and will search for ungated alternatives |
| Flashy testimonials | Developers trust GitHub stars, Stack Overflow answers, and docs quality |
| Scarcity signals ("Only 3 seats left!") | Developers know SaaS doesn't have real scarcity and will distrust you |
| Social proof via influencers | Developers trust peers, open-source contributors, and technical bloggers |

**The developer psychology rule:** Be transparent, show your work, and let the product speak. Developers have high trust requirements and low tolerance for manipulation.

---

## Models That Work Well for Imgix

### 1. Endowment Effect (Free Tier Strategy)

People value things more once they own them. Imgix's free tier lets developers "own" the product before paying.

**Imgix application:**
- Free tier with meaningful capabilities (not a crippled demo)
- Dashboard shows accumulated usage and value: "You've processed 12,400 images this month"
- When approaching limits, frame the upgrade as keeping what they have: "Upgrade to keep your current setup running smoothly"

### 2. IKEA Effect (Onboarding Investment)

People value things more when they've put effort into building them. Each onboarding step increases switching costs.

**Imgix application:**
- The 4-step activation path (connect source → configure subdomain → serve image → apply transform) creates invested users
- After connecting their S3 bucket and configuring their subdomain, developers have skin in the game
- Show their configuration and customization: "Your custom setup: images.yoursite.com → S3 bucket → 96 PoPs"

### 3. Status-Quo Bias (Reducing Switch Friction)

People resist change. For Imgix, this works both ways — it keeps existing customers, but makes acquisition harder.

**Imgix application for acquisition:**
- BYOS (bring your own storage) directly addresses status-quo bias: "Your images stay exactly where they are"
- Migration guides reduce perceived effort: "Switch from Cloudinary in 15 minutes"
- Show that Imgix is additive, not disruptive: "Add URL parameters to your existing image URLs"

**Imgix application for retention:**
- Once developers integrate Imgix URLs across their codebase, status-quo bias works in Imgix's favor
- Each additional source connected increases switching resistance

### 4. Zero-Price Effect (Free Tier Psychology)

Free isn't just a low price — it's psychologically different. The jump from $1 to $0 is larger than $100 to $1.

**Imgix application:**
- "Free — no credit card required" removes all friction. This is more powerful than "starts at $5/month"
- Developers evaluate tools by trying them. A free tier is table stakes for PLG developer products
- Use "Start free" as the primary CTA. Not "Sign up" (implies commitment), not "Get started" (vague)

### 5. Anchoring Effect (Pricing Presentation)

The first number people see influences all subsequent price judgments.

**Imgix application:**
- Show enterprise tier first on the pricing page (left-to-right or highest price at top)
- When discussing TCO, anchor to the cost of self-hosted: "Engineering time on image pipelines costs $15K+/month. Imgix costs a fraction of that"
- In sales conversations, anchor to competitor pricing: "Cloudinary's equivalent plan costs [X]. Imgix gives you [same capabilities] for [Y]"

### 6. Social Proof (Developer-Appropriate)

Developers respond to specific types of social proof, not generic testimonials.

**What works for developers:**
- Customer logos with scale metrics: "Unsplash serves 2B+ images/month through Imgix"
- GitHub stars and open-source adoption
- "8B+ images processed daily" (aggregate proof of reliability)
- Stack Overflow community answers
- Engineering blog posts from customers describing their Imgix integration

**What doesn't work:**
- "We love Imgix! 5 stars!" — too generic
- Marketing testimonials without technical detail
- Inflated user counts without context

### 7. Authority Bias (Technical Credibility)

Developers defer to expertise demonstrated through technical depth, not claimed authority.

**Imgix application:**
- Public status page (uptime proof, not a claim)
- Detailed technical documentation (the docs ARE the marketing)
- Engineering blog posts explaining CDN architecture, format optimization algorithms
- Open-source SDKs (code speaks louder than marketing copy)
- Conference talks by Imgix engineers at developer events

### 8. Reciprocity (Give Value First)

Give developers something valuable before asking for anything. Free tools, great docs, and helpful community answers create goodwill.

**Imgix application:**
- Free image performance analyzer (no signup required to use)
- Comprehensive docs that help even non-customers
- Answer image optimization questions on Stack Overflow and Reddit
- Open-source SDKs that work independently of Imgix's paid service
- Blog content that teaches image optimization regardless of tool choice

### 9. Goal-Gradient Effect (Onboarding Progress)

People accelerate effort as they approach a goal. Show progress to drive completion.

**Imgix application:**
- Onboarding checklist with 4-5 steps and visible progress
- "You're 3 of 4 steps to optimized images" in the dashboard
- Celebrate milestones: "Your first 1,000 images served!"
- Email sequences that reference progress: "You've connected your source. Here's how to serve your first image."

### 10. Pratfall Effect (Honest Positioning)

Admitting a weakness makes strengths more credible. Especially effective with skeptical developer audiences.

**Imgix application:**
- On comparison pages: "Cloudinary has more extensive video features. Imgix excels at image processing speed and API simplicity"
- This honesty makes "8B+ images/day" and "BYOS" claims more believable
- "We're not the cheapest option. We're the fastest and simplest" is a strong position

---

## Models for Specific Imgix Scenarios

### Pricing Page

| Principle | Application |
|-----------|------------|
| Anchoring | Show enterprise tier first to make growth tier feel reasonable |
| Decoy effect | If adding a third tier, ensure the middle option is the best value |
| Mental accounting | "$X per 1,000 images" feels smaller than monthly totals |
| Paradox of choice | Three tiers maximum. Recommend one: "Best for most teams" |
| Loss aversion | Frame upgrades as "keep your current setup" not "get more features" |

### Signup Flow

| Principle | Application |
|-----------|------------|
| Zero-price effect | "Free — no credit card" is the strongest possible CTA |
| Commitment & consistency | Small first step (email only) → profile → connect source |
| Activation energy | Pre-fill where possible, minimize required fields |
| Default effect | Pre-select recommended options (e.g., auto-format on) |

### Onboarding

| Principle | Application |
|-----------|------------|
| Goal-gradient | 4-step progress bar toward "first optimized image" |
| IKEA effect | Each configuration step increases investment |
| Peak-end rule | Make the first image transform a "wow" moment |
| Zeigarnik effect | "You're 75% set up" in email creates pull to finish |

### Upgrade / Expansion

| Principle | Application |
|-----------|------------|
| Endowment effect | "You've processed 50K images. Keep your workflow running" |
| Loss aversion | Frame as protecting current usage, not buying more features |
| Foot-in-the-door | Free → growth → enterprise is a natural escalation |
| Sunk cost awareness | Remind them of investment: "Your team has configured 5 sources" |

### Churn Prevention

| Principle | Application |
|-----------|------------|
| Status-quo bias | Switching requires changing URLs across the codebase — high friction |
| Endowment effect | They've built their workflow around Imgix |
| IKEA effect | Custom configurations, subdomain setup — all effort they'd lose |
| Switching costs | Make these visible: "You have 12 sources, 3 team members, and 2 custom domains configured" |

---

## Anti-Patterns: Psychology That Backfires with Developers

| Tactic | Why It Fails | What to Do Instead |
|--------|-------------|-------------------|
| Countdown timers | Feels manipulative, creates distrust | Show genuine usage metrics instead |
| "Limited time offer!" | Developers know SaaS pricing doesn't work this way | Offer value: "Annual plans save 17%" |
| Aggressive exit popups | Interrupts workflow, causes irritation | Helpful in-app messaging when stuck |
| Hiding pricing | Developers will leave and find a competitor with transparent pricing | Show pricing upfront |
| Requiring phone number | Developers despise sales calls | Email-only signup |
| Gated technical docs | Developers will use a competitor with open docs | Make all docs public |
| Fake urgency ("Offer expires!") | Instant credibility destruction | Real signals: "You're at 80% of your plan limit" |

---

## Quick Reference: Challenge → Model

| Challenge | Best Models |
|-----------|------------|
| Low signup conversion | Zero-price effect, Activation energy, Social proof |
| Poor onboarding completion | Goal-gradient, IKEA effect, Zeigarnik effect |
| Price objections | Anchoring, Mental accounting, TCO framing |
| Competitor evaluation | Pratfall effect, Authority bias, Honest comparison |
| Upgrade resistance | Endowment effect, Loss aversion, Status-quo bias |
| Churn risk | Switching costs, Endowment effect, IKEA effect |
| Building trust | Reciprocity, Authority bias, Social proof (developer-appropriate) |

---

## Related Skills

- **Conversion/page-cro** — Apply psychology to page optimization
- **Conversion/pricing-strategy** — Pricing psychology for Imgix tiers
- **Conversion/signup-flow-cro** — Psychology of signup conversion
- **Conversion/onboarding-cro** — Behavioral design for onboarding
- **Conversion/ab-test-setup** — Test psychological hypotheses with PostHog
- **Content/copywriting** — Write copy using psychological principles
- **Lifecycle/churn-prevention** — Retention psychology
- **imgix-brand-voice** (global) — Psychology-informed copy follows brand voice
