# Imgix Product Marketing System

**Owner:** Michelle Su
**Created:** April 17, 2026
**Last Updated:** May 27, 2026

## What This Is

This folder is a coordinated system for product marketing — understanding the market, positioning Imgix, enabling sales, and launching features. These skills inform every other system's messaging and targeting.

## How to Use This Folder

**When to invoke this folder:** A feature is going to launch, sales asks for new collateral, positioning needs a refresh, you want to mine customer research for insights, or a competitor moved. This folder informs how Imgix shows up to the market.

**Context to bring:**
- The product or feature in question (one-pager, spec, dates)
- The audience (which persona, internal vs. external)
- Current positioning and where it might need to shift
- Sales context if relevant (deal stage, objection, competitor in deal)
- Access to Gong (for customer research) and Drive (for collateral storage) confirmed

**How the sub-skills fit together:**
- This folder has an **orchestrator + specialists.**
- launch-strategy is the orchestrator. It pulls from sales-enablement (collateral), Content/copywriting (blog and email), customer-research (proof points), competitor-alternatives (comparison angle), and Discoverability/imgix-aeo (search and AEO setup).
- The other sub-skills work standalone too. Use customer-research for ongoing voice-of-customer work. Use competitor-alternatives whenever a vs. page or battle card is needed. Use revops when lead routing or scoring needs attention.
- *Note: positioning and win-loss-analysis are planned but not built. For positioning work today, use product-marketing-context (global) directly. For win-loss, pull Gong calls into customer-research manually.*

**Typical prompts:**
- "Plan the launch for [feature]. Use launch-strategy. Target date is [date]."
- "Build a battle card against Cloudinary. Focus on the URL-based API simplicity angle and BYOS."
- "Analyze the last 10 Gong calls for objection patterns. What are we hearing most often?"
- "Update sales-enablement collateral with the new pricing and the AI features added in Q1."

**Output to expect:** Launch plans with checklists and full content packages, public-facing comparison pages, sales decks and one-pagers, objection handling docs, customer research syntheses, lead scoring proposals.

**When NOT to use this folder (and where to go instead):**
- Writing the actual launch blog or email copy → Content/copywriting (launch-strategy will direct you there)
- Paid promotion for the launch → Acquisition/paid-ads
- Post-launch lifecycle emails to customers → Lifecycle/email-sequence
- Brand voice and tone → imgix-brand-voice (global)
- ICP, positioning fundamentals, proof points → product-marketing-context (global)

## How Claude Runs this Folder

1. **Read this MANIFEST.md** to understand the system and current priorities
2. **Read MEMORY.md** for accumulated context from previous sessions
3. **Always load global skills first:** `imgix-brand-voice` and `product-marketing-context`
4. **Check each subfolder's STATUS.md** for current state
5. **Execute work** using the SKILL.md in the relevant subfolder
6. **Update STATUS.md and MEMORY.md** when work is completed
7. **Report results** via Slack to Michelle

## Connected Tools (MCP)

- **HubSpot** — CRM data, deal analysis, customer segmentation
- **Jira** — Track product marketing tasks (MKTG project)
- **Slack** — Coordinate launches and share competitive intel
- **Gmail** — Sales enablement distribution, customer outreach
- **Google Drive** — Sales collateral, research docs, battlecards

## Global Dependencies

- **imgix-brand-voice** — All positioning and messaging follows brand guidelines
- **product-marketing-context** — This system owns and updates the foundational context doc

## Subfolders

### 1. `customer-research/` — UNDERSTANDING
ICP research, voice of customer, review mining, persona development. Feeds insights into every other system.

### 2. `competitor-alternatives/` — COMPETITIVE
Comparison pages, vs pages, battle cards, and competitive teardowns. Coordinate with Discoverability for SEO optimization of comparison content.

### 3. `sales-enablement/` — SALES SUPPORT
Pitch decks, one-pagers, objection handling docs, demo scripts, and talk tracks for the sales team.

### 4. `launch-strategy/` — LAUNCHES
Product launches, feature announcements, and go-to-market planning. Coordinates with Content (assets), Acquisition (promotion), and Lifecycle (existing customer comms).

### 5. `revops/` — SYSTEMS
Revenue operations — lead scoring, lead routing, marketing-to-sales handoff, CRM automation, and pipeline management.

### 6. `win-loss-analysis/` — FEEDBACK LOOP *(planned)*
Systematic analysis of why deals close or don't. Feeds back into positioning, competitive intel, and sales enablement.

### 7. `positioning/` — NARRATIVE *(planned)*
Category design, messaging framework, and core narrative. The strategic foundation that product-marketing-context is derived from.

## Cross-System References

- **Product-Marketing → Content:** Positioning and research inform what content to create and how to frame it.
- **Product-Marketing → Conversion:** Pricing strategy and value props inform page optimization.
- **Product-Marketing → Acquisition:** ICP and positioning inform ad targeting and outreach.
- **Product-Marketing → Discoverability:** Competitor intel informs comparison content and AEO narratives.
- **Product-Marketing → Lifecycle:** Launch comms and customer research inform lifecycle messaging.

## Definition of Done

This system is successful when:
- Customer research is conducted quarterly and shared across teams
- Battle cards exist for top 4 competitors and are updated quarterly
- Sales has current collateral for every major deal scenario
- Feature launches follow a repeatable GTM process
- Win-loss analysis feeds back into positioning quarterly
