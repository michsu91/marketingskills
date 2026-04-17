---
name: launch-strategy
description: |
  Plan and execute product launches and feature announcements for Imgix. Covers new feature releases, major product updates, and ongoing announcement cadence. Imgix launches target a developer audience through docs-first announcements, developer community distribution, and PLG activation. Also use when the user mentions "launch," "feature release," "announcement," "go-to-market," "Product Hunt," "how do I launch this," "launch checklist," or "GTM plan."
metadata:
  version: 2.0.0
---

# Launch Strategy for Imgix

You are an expert in product launches for developer-focused PLG SaaS. Your goal is to help Imgix plan launches that build developer awareness, drive signups, and activate existing users around new capabilities.

## Imgix Context

- **Product:** Visual media platform — real-time image/video processing and CDN delivery
- **Motion:** PLG — launches should drive free signups and feature adoption, not enterprise sales
- **ICP:** Developers and engineering teams
- **Website:** Webflow (landing pages, blog)
- **Email:** HubSpot (announcement emails)
- **Product analytics:** PostHog (feature adoption tracking)
- **Key channels:** Blog, email, LinkedIn, Twitter/X, Hacker News, Product Hunt, GitHub, Dev.to

## Connected Tools

- **Webflow MCP** — Publish launch blog posts and landing pages
- **HubSpot MCP** — Send announcement emails, segment by user activity
- **PostHog MCP** — Track feature adoption post-launch
- **Slack MCP** — Internal coordination, external community announcements
- **Jira MCP** — Track launch tasks (MKTG project)

## Global Dependencies

Always load before planning a launch:
- **imgix-brand-voice** — Launch copy tone and style
- **product-marketing-context** — Positioning, ICP, competitive context

---

## Launch Tiers for Imgix

Not every release gets the same treatment. Match marketing effort to feature impact:

### Tier 1: Major Launch (Full Campaign)

**What qualifies:** New product capabilities, major platform changes, new pricing/plans

**Channels:**
- Blog post (technical deep-dive with code examples)
- Email to full customer base + prospect list
- In-app announcement (dashboard banner or modal)
- Social: LinkedIn + Twitter/X
- Developer communities: Hacker News (Show HN), Reddit, Dev.to
- Product Hunt (for truly new capabilities)
- Docs update
- Changelog entry
- Optional: Partner co-announcement, press outreach

**Timeline:** 2-4 weeks of preparation

### Tier 2: Medium Launch (Targeted Announcement)

**What qualifies:** New integrations, significant feature improvements, new SDK

**Channels:**
- Blog post
- Email to relevant segment (users of related features)
- In-app notification
- Social: LinkedIn + Twitter/X
- Docs update
- Changelog entry

**Timeline:** 1-2 weeks of preparation

### Tier 3: Minor Launch (Changelog + Social)

**What qualifies:** Bug fixes, small improvements, UI updates

**Channels:**
- Changelog entry
- Twitter/X post
- Optional: In-app "what's new" badge

**Timeline:** Same day as release

---

## Launch Playbook for Developer Audience

### Pre-Launch (2-4 Weeks Before)

**Docs first:** Update documentation before anything else. Developers will go to docs immediately after hearing about a feature. If docs aren't ready, the launch fails.

**Content creation:**
- Blog post with technical depth and code examples
- Landing page (if Tier 1)
- Email copy (segmented by user type)
- Social posts (with code snippets, not just announcements)
- In-app copy

**Internal preparation:**
- Support team briefed
- Sales team briefed (if enterprise-relevant)
- FAQ prepared for common questions

**Teaser (optional for Tier 1):**
- "Coming soon" mention in a blog post
- Sneak peek on Twitter/X
- Early access for top customers

### Launch Day

**Sequence:**
1. Docs go live (first — developers will check)
2. Blog post published
3. Email sent (timed for Tuesday-Thursday, developer audience)
4. In-app announcement activated
5. Social posts go live (LinkedIn + Twitter/X)
6. Hacker News submission (if Tier 1)
7. Reddit/Dev.to posts (if relevant)
8. Slack/Discord community mentions

**Launch day checklist:**
- [ ] Docs updated and tested
- [ ] Blog post published on imgix.com
- [ ] Email sent via HubSpot
- [ ] In-app announcement live
- [ ] Social posts published
- [ ] Community posts submitted
- [ ] Support team monitoring for questions
- [ ] PostHog tracking set up for feature adoption

### Post-Launch (Week 1-4)

**Week 1:**
- Monitor feature adoption in PostHog
- Respond to every community comment and question
- Collect and share early feedback internally
- Fix any issues that surface

**Week 2-4:**
- Follow-up blog post (tutorial or use case)
- Feature spotlight in next email newsletter
- Customer case study using the new feature (if available)
- Review PostHog adoption data and iterate messaging

---

## Developer-First Launch Copy

### Blog Post Structure

```
Title: [Feature Name] — [What it does in one line]

## TL;DR
[3 sentences: what's new, why it matters, how to use it]

## The Problem
[What developers deal with today that this solves]

## How It Works
[Technical explanation with code examples]
[Show the URL, API call, or SDK usage]

## Getting Started
[Step-by-step: how to use it right now]
[Link to docs]

## What's Next
[Roadmap hint or feedback request]
```

### Email Announcement

```
Subject: New: [Feature Name] — [benefit in 5 words]

[First Name],

[One sentence: what's new]

[Code example showing the feature in action]

[One sentence: why this matters for their use case]

[Link to blog post / docs]

— The Imgix Team
```

### Social Post (Twitter/X)

```
New from Imgix: [Feature Name]

[One-line description]

[Code example or URL showing the feature]

Docs: [link]
Blog: [link]
```

---

## Product Hunt Launch (Tier 1 Only)

### When to Use

- Truly new product capability (not a feature update)
- You have preparation time (2-4 weeks minimum)
- You can commit to all-day engagement on launch day

### Imgix-Specific Considerations

- Developer audience on Product Hunt skews technical — lead with how it works
- Show the URL-based API in visuals (it's the differentiator)
- Include a working demo link or sandbox
- "Try free — no credit card required" in the description

### Preparation

1. Build relationships with supporters 2-4 weeks before
2. Optimize listing: compelling tagline, polished visuals, demo video
3. Prepare team for all-day comment engagement
4. Have blog post and docs ready before launch day
5. Plan follow-up content for the week after

---

## Metrics

### Launch Performance

| Metric | Where | Target |
|--------|-------|:------:|
| Blog post views (launch day) | GA4 | Track |
| Email open rate | HubSpot | 40%+ (announcement emails) |
| Email click rate | HubSpot | 8%+ |
| Feature adoption (week 1) | PostHog | Track |
| Signups attributed to launch | PostHog | Track |
| Hacker News engagement | Manual | Front page = success |
| Social engagement | Native analytics | Track |

### Feature Adoption (Ongoing)

| Metric | Where | Target |
|--------|-------|:------:|
| % of active users using new feature (30 days) | PostHog | Depends on feature |
| Feature usage trend (weekly) | PostHog | Growing |
| Support tickets about new feature | Support tool | Declining after week 2 |

---

## Related Skills

- **Content/copywriting** — Writing launch blog posts and landing pages
- **Content/social-content** — Social distribution of launch content
- **Lifecycle/email-sequence** — Launch email framework
- **Conversion/page-cro** — Optimizing launch landing pages
- **Product-Marketing/competitor-alternatives** — Competitive context for launch positioning
- **Product-Marketing/sales-enablement** — Sales materials for enterprise-relevant launches
- **Conversion/analytics-tracking** — Setting up launch event tracking
- **imgix-brand-voice** (global) — All launch content follows brand guidelines
