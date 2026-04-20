---
name: win-loss-analysis
description: |
  Systematic analysis of why Imgix wins and loses deals. Use when reviewing closed-won and closed-lost deals, identifying patterns in competitive losses, or feeding insights back into positioning and sales enablement. Analyze Gong calls, HubSpot deal data, and sales feedback. Triggers: "win loss," "why did we lose," "deal analysis," "competitive loss," "closed lost," "why do we win."
---

# Win-Loss Analysis

## Goal
Understand why Imgix wins and loses deals. Feed insights back into positioning, competitive intel, sales enablement, and product roadmap. This is one of the most underused feedback loops in B2B marketing.

## Imgix Win-Loss Context

**Where deal data lives:**
- **HubSpot:** Deal records with close reasons, deal size, competitor mentions, vertical tags
- **Gong:** Sales call recordings with transcribed conversations, objections, competitor mentions
- **Slack (#sales):** Informal deal commentary from Glenn and the sales team
- **BigQuery:** Usage data for accounts that converted (or didn't)

**Common win reasons (validate these through analysis):**
- URL-based simplicity vs. complex APIs
- BYOS model (no vendor lock-in)
- Performance and quality (sub-20ms response times, superior rendering)
- "One platform" consolidation story
- Developer experience and documentation quality

**Common loss reasons (validate these through analysis):**
- Cloudinary's brand recognition ("safe choice" at enterprise level)
- Perception that Imgix is "image-only" (misses video + AI breadth)
- Pricing comparison when Cloudinary bundles aggressively
- Specific feature gaps the prospect needed
- Inertia (already using a competitor, switching cost too high)

## Analysis Framework

### Step 1: Data Collection (Monthly)
1. Pull closed-won and closed-lost deals from HubSpot for the past 30 days
2. Tag each deal: competitor involved, deal size, vertical, close reason
3. For closed-lost deals, check if Gong recordings exist and flag for review
4. For closed-won deals, note what messaging or proof points resonated

### Step 2: Pattern Identification (Monthly)
Look for patterns across the dataset:
- Which competitors appear most in losses?
- Which verticals have the highest win rate?
- What deal size range does Imgix win most?
- Are there common objections that keep appearing?
- Do specific features or capabilities tip deals?

### Step 3: Segmentation
Slice the data by:
- **Deal size:** SMB vs. mid-market vs. enterprise
- **Vertical:** Ecommerce, media, SaaS, marketplace
- **Competitor:** Cloudinary, ImageKit, Cloudflare, self-hosted, none
- **Use case:** Image optimization, video, AI features, full platform
- **Sales motion:** Self-serve vs. sales-assisted

### Step 4: Insight Synthesis
Turn patterns into actionable insights:
- "We lose 60% of enterprise deals where Cloudinary is the incumbent. Primary objection: switching cost." → Action: create a migration guide and ROI calculator
- "We win 80% of deals where the prospect visits docs before talking to sales." → Action: drive more prospects to docs earlier in the funnel
- "Video capabilities are mentioned in 30% of recent wins but aren't in our standard pitch." → Action: update sales deck and enablement materials

### Step 5: Action Distribution
Route insights to the right systems:
- **Positioning** → Refine messaging based on what resonates in won deals
- **Competitor-alternatives** → Update battle cards with real objections from lost deals
- **Sales-enablement** → New objection handling based on actual losses
- **Pricing-strategy** → Pricing-related wins/losses inform packaging changes
- **Product roadmap** → Feature gaps that caused losses go to product triage

## Gong Call Analysis Guide

When reviewing Gong recordings for win-loss:
- Note the moment the prospect's tone shifts (positive or negative)
- Capture verbatim objections in the prospect's own language
- Flag competitor comparisons the prospect makes
- Note which Imgix features or claims generate the most interest
- Track if the "one platform" narrative lands or falls flat
- Listen for pricing reactions (sticker shock, perceived value, comparison to current spend)

## Reporting

**Monthly:** Summary of wins/losses by competitor, vertical, and deal size. Top 3 actionable insights.
**Quarterly:** Full analysis with trend comparison, updated battle cards, and recommendations for positioning changes.

Post summaries to #sales in Slack and create Jira tickets for any actions that need follow-up.

## Related Skills
- **Product-Marketing/customer-research** — Win-loss is a form of customer research
- **Product-Marketing/sales-enablement** — Insights become sales collateral
- **Product-Marketing/competitor-alternatives** — Competitive losses update battle cards
- **Product-Marketing/positioning** — Win patterns validate or challenge positioning
- **Conversion/pricing-strategy** — Pricing-related insights inform packaging
