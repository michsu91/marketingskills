# imgix Acquisition System

**Owner:** Michelle Su
**Created:** April 17, 2026
**Last Updated:** May 27, 2026

## What This Is

This folder is a coordinated system for acquiring new users and leads through paid and organic channels beyond search. Covers paid advertising, cold outreach, lead generation, referrals, free tools, and events.

## How to Use This Folder

**When to invoke this folder:** You're planning or executing a non-search acquisition channel: paid ads, cold outreach, gated content, free tools, or events. If you're not sure which channel to invest in, check `marketing-ideas` first for the prioritized list, then pick the right sub-skill here.

**Context to bring:**
- Target audience and segment (which persona, which vertical)
- Budget and timeline (campaign window, monthly spend ceiling)
- Channel choice (paid ads vs. cold email vs. lead magnet vs. tool)
- What success looks like (signups, qualified leads, downloads)
- Existing campaign performance if iterating

**How the sub-skills fit together:**
- This folder is a **menu, not a pipeline.** Each sub-skill is a discrete channel.
- Pick the sub-skill that matches your channel and execute it.
- Skills don't chain in a fixed sequence. They're independent disciplines.
- Cross-cutting work (a lead magnet that drives paid ad traffic) uses two sub-skills in parallel, not sequentially.

**Typical prompts:**
- "Draft a cold email sequence to engineering leads at e-commerce companies with high image volume."
- "Plan a Google Ads test targeting 'Cloudinary alternative.' Define keywords, budget, ad copy, and landing page."
- "Brainstorm a lead magnet developers will actually download. Should be technical and immediately useful."
- "Evaluate whether to build a free image performance analyzer. Score effort, lead potential, and engineering ask."

**Output to expect:** Campaign briefs with targeting and budget, ad copy and headline sets, cold email sequence drafts, lead magnet outlines, free tool specs. Often produces a Jira ticket in MKTG for the execution work.

**When NOT to use this folder (and where to go instead):**
- Organic search and AEO → Discoverability
- Organic social (LinkedIn, Twitter) → Content/social-content
- Email sequences for existing leads or customers → Lifecycle/email-sequence
- Brand or messaging foundation → product-marketing-context (global)

## How It Works

1. **Read this MANIFEST.md** to understand the system and current priorities
2. **Read MEMORY.md** for accumulated context from previous sessions
3. **Always load global skills first:** `imgix-brand-voice` and `product-marketing-context`
4. **Check each subfolder's STATUS.md** for current state
5. **Execute work** using the SKILL.md in the relevant subfolder
6. **Update STATUS.md and MEMORY.md** when work is completed
7. **Report results** via Slack to Michelle

## Connected Tools (MCP)

- **HubSpot** — Track leads, attribution, and campaign performance
- **Jira** — Track campaign tasks (MKTG project)
- **Slack** — Coordinate campaigns and report results
- **Gmail** — Cold outreach and partnership emails
- **Google Calendar** — Event scheduling

## Global Dependencies

- **imgix-brand-voice** — All outreach and ad copy follows brand guidelines
- **product-marketing-context** — ICP and positioning inform targeting and messaging

## Subfolders

### 1. `paid-ads/` — PAID CHANNELS
Google Ads, LinkedIn Ads, and other paid advertising. Campaign strategy, targeting, bidding, and optimization.

### 2. `cold-email/` — OUTBOUND
B2B cold email outreach and follow-up sequences for developer and enterprise leads.

### 3. `lead-magnets/` — GATED CONTENT
Downloadable content for email capture — image optimization guides, benchmark reports, checklists, templates.

### 4. `free-tool-strategy/` — ENGINEERING AS MARKETING
Plan and build free tools that attract developers — image analyzers, performance graders, format converters. High leverage for a developer tools company.

### 5. `webinars-events/` — EVENTS *(planned)*
Webinar strategy, conference talks, and workshop planning. Not running currently but placeholder for when the channel is activated.

## Cross-System References

- **Acquisition → Conversion:** Acquisition drives traffic; Conversion optimizes it into signups.
- **Content → Acquisition:** Lead magnets and free tools need content from the Content system.
- **Discoverability → Acquisition:** Organic search is handled by Discoverability; this system handles non-search channels.
- **Product-Marketing → Acquisition:** Customer research and positioning inform targeting.

## Definition of Done

This system is successful when:
- At least 2 acquisition channels are active and measured
- Lead magnet library has 3+ high-quality downloadable assets
- Free tool strategy evaluated (build vs. skip decision made)
- Every acquisition channel has clear CAC and attribution
