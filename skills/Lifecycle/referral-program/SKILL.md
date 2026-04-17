---
name: referral-program
description: |
  Design and optimize a referral or affiliate program for Imgix. Use when building a customer referral program, planning affiliate partnerships, or creating word-of-mouth growth loops. Imgix's developer audience refers through code communities, Stack Overflow, GitHub, and direct team recommendations — not traditional "share a link" mechanics.
---

# Referral & Affiliate Programs for Imgix

You are an expert in viral growth and referral marketing for developer tools. Your goal is to design referral programs that leverage how developers actually recommend tools to each other.

## Imgix Context

- **Product:** Visual media platform — real-time image/video processing and CDN delivery
- **ICP:** Developers and engineering teams. They recommend tools through code reviews, architecture discussions, and Stack Overflow answers.
- **Pricing:** Usage-based. Referral economics must account for variable revenue per account.
- **Current state:** No referral or affiliate program (greenfield opportunity)
- **How developers actually refer tools:** GitHub repos, blog posts, conference talks, Stack Overflow answers, Slack/Discord communities, direct recommendations to colleagues

## Connected Tools

- **HubSpot MCP** — Track referral attribution, manage affiliate contacts
- **Stripe MCP** — Commission tracking, referral credit application
- **Slack MCP** — Notify on referral conversions, coordinate program launch
- **Jira MCP** — Track program build tasks (MKTG project)

---

## How Developer Referrals Actually Work

Traditional referral programs ("share this link, get $20") underperform with developers. Developers recommend tools when:

1. **They solve a real problem** — "We switched to Imgix and our LCP dropped from 3.2s to 0.8s"
2. **The code is clean** — Good SDKs, simple API, URL-based transforms they can show in a code review
3. **They trust the recommender** — Tech leads, senior engineers, open source maintainers
4. **The recommendation is contextual** — Stack Overflow answer about image optimization, not a cold referral link

### Imgix Referral Channels (Ranked by Trust)

| Channel | Trust Level | Volume | Imgix Opportunity |
|---------|:----------:|:------:|-------------------|
| Direct colleague recommendation | Highest | Low | Hard to track, but highest conversion |
| Stack Overflow answers | High | Medium | Answer image optimization questions with Imgix examples |
| GitHub repos / READMEs | High | Medium | Imgix SDKs referenced in project dependencies |
| Blog posts / tutorials | Medium-High | Medium | "How I optimized images with Imgix" posts |
| Conference talks | High | Low | Web performance talks featuring Imgix |
| Twitter/LinkedIn | Medium | High | Developer influencer mentions |
| Affiliate links | Low | Variable | Content creators, comparison sites |

---

## Referral Program Design for Imgix

### Option 1: Usage Credit Referral (Recommended for PLG)

**How it works:**
- Existing customer gets a referral link from their Imgix dashboard
- New signup uses the link → gets $50 in usage credits
- When the referred account makes first payment → referrer gets $100 in usage credits
- Double-sided reward, both parties benefit

**Why usage credits work for Imgix:**
- Aligns with usage-based pricing (credits feel natural)
- Low marginal cost to Imgix (credit costs less than cash)
- Encourages the referrer to use more Imgix features
- No cash payout complexity

### Option 2: Affiliate Program (For Content Creators)

**How it works:**
- Content creators, bloggers, and tutorial writers apply to the program
- Approved affiliates get tracking links and a dashboard
- 20% recurring commission for 12 months on referred accounts
- Minimum payout threshold ($50)

**Why for Imgix:**
- Developer content creators write image optimization tutorials
- Comparison bloggers write "Cloudinary vs alternatives" content
- YouTube tutorial creators show image processing workflows
- These are the third-party sources AI models cite (6.5x more likely than your own domain)

### Option 3: Partner Program (For Agencies/Consultancies)

**How it works:**
- Web development agencies and performance consultancies get partner status
- Dedicated referral dashboard with client management
- Higher commission (25%) or volume-based discounts for their clients
- Co-marketing opportunities (joint case studies, webinar mentions)

**Best for:** Agencies building ecommerce sites, media platforms, or real estate portals that need image optimization.

---

## The Referral Loop for Imgix

```
Activation → Delight Moment → Share Prompt → Convert Referred → Reward → Loop
```

### Trigger Moments (When to Ask)

| Moment | Why It Works | Implementation |
|--------|-------------|----------------|
| First 10K images served | They've seen the product work | In-app banner + email |
| Performance milestone | "Your images are 60% smaller" | Dashboard notification |
| After positive support interaction | Goodwill is high | Follow-up email |
| 90 days active | Committed, unlikely to churn | Email + in-app |
| Plan upgrade | They're investing more | Confirmation email with referral CTA |

### Share Mechanisms for Developers

**In-product (highest conversion):**
- Referral link in Imgix dashboard settings
- "Share with your team" button that generates a team invite link
- Code snippet they can drop in a README: `<!-- Images optimized by Imgix -->`

**Content-based (highest reach):**
- Pre-written code examples they can use in blog posts
- Imgix badge for READMEs (like "powered by Vercel" badges)
- Shareable performance report: "See how Imgix optimized our images"

---

## Measuring Success

### Key Metrics

| Metric | Target | How to Track |
|--------|:------:|-------------|
| Active referrers (last 30 days) | Growing month-over-month | HubSpot referral attribution |
| Referral conversion rate | 15-25% | Link click → signup |
| Referred account activation rate | Higher than organic | PostHog cohort comparison |
| % of new accounts from referral | 10%+ at maturity | HubSpot source attribution |
| Referred customer LTV | 20%+ higher than average | Stripe cohort analysis |
| CAC via referral | 50%+ lower than paid | Credits issued / revenue generated |

### What to Watch For
- **Fraud:** Same person creating multiple accounts for credits → verify with email domain + usage pattern
- **Low-quality referrals:** Signups that never activate → only pay reward after first payment
- **Referral cannibalization:** People who would have signed up anyway → compare to organic baseline

---

## Launch Plan

### Phase 1: Soft Launch (Month 1)
- Build referral link generation in Imgix dashboard
- Create referral landing page on imgix.com
- Email top 100 most active customers with early access
- Track manually in HubSpot

### Phase 2: Public Launch (Month 2)
- Announce to full customer base
- Add in-app referral prompts at trigger moments
- Launch affiliate application page
- Set up automated tracking and reward distribution

### Phase 3: Optimize (Month 3+)
- A/B test incentive amounts
- Identify and nurture top referrers
- Launch agency partner tier
- Create referral-specific content (shareable performance reports, badges)

---

## Email Sequences for Referral Program

### Launch Announcement
```
Subject: Invite your team — get $100 in Imgix credits

You've been using Imgix to optimize your images.
Know someone else who should be?

Share your referral link → they get $50 in credits,
you get $100 when they subscribe.

[Get your referral link →]
```

### Post-Milestone Nudge
```
Subject: You just served your 100,000th optimized image

That's 100K images delivered faster, smaller, and in the
right format for every browser.

Know another team dealing with slow image loads?

[Share Imgix with your network →]
```

---

## Related Skills

- **Lifecycle/customer-advocacy** — Advocacy pipeline feeds referral program participants
- **Lifecycle/email-sequence** — Email framework for referral campaigns
- **Lifecycle/expansion-upsell** — Referral credits encourage more usage (expansion)
- **Discoverability/imgix-aeo** — Third-party mentions from affiliates boost AI citations
- **Product-Marketing/launch-strategy** — Referral program launch plan
- **Conversion/analytics-tracking** — Referral attribution tracking
- **imgix-brand-voice** (global) — All referral content follows brand guidelines
