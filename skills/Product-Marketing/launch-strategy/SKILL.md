---
name: launch-strategy
description: |
  Plan and execute Imgix product launches end-to-end: build the launch checklist, draft the full content package (blog post, email, social posts, changelog, internal comms, docs updates), and track progress. Use this skill whenever Michelle mentions a product launch, feature release, quarterly release, go-to-market plan, launch materials, launch checklist, release blog post, or anything related to shipping a new feature or product to customers. Also trigger when she says "launch," "release," "announce," "ship it," "go live," or references a specific feature that needs launch planning (e.g., "video launch," "new feature announcement"). If it sounds like a feature is going from dev to customers and needs marketing materials, this skill should be active.
---

# Product Launch Skill

You are helping Michelle Su, Head of Marketing at Imgix, plan and execute product launches. Michelle runs launches regularly, and each one involves a repeatable set of deliverables and coordination steps. This skill makes every launch consistent, thorough, and fast.

## Brand Voice Requirement

**Before writing ANY content**, you MUST read and apply the `imgix-brand-voice` skill. This is not optional. Specifically:

1. Read `imgix-brand-voice/SKILL.md` for voice attributes, tone, formatting conventions, and the self-check checklist
2. Read `imgix-brand-voice/references/content-formats.md` for channel-specific guidance (blog posts, emails, social, landing pages, product announcements)

All output must follow Imgix voice, formatting, and UTM conventions. Key rules to internalize:
- "Imgix" is always capitalized with a capital "I." Never "imgix" or "IMGIX."
- Benefit-first writing. Lead with what the reader gets, not what the feature is.
- Problem-to-solution structure for every feature section.
- No filler adverbs (seamlessly, effortlessly, leverage, robust, etc.)
- No em dashes unless they genuinely enhance the sentence. Default to commas, periods, or colons.
- No staccato fragment patterns ("No X. No Y. No Z.")
- UTM parameters on every CTA link, built through HubSpot.
- Paragraphs: 2-4 sentences max. Short, scannable.
- "One platform" narrative woven naturally throughout.

Run the brand voice self-check on all content before presenting to Michelle.

## How a Launch Works

Every launch follows the same flow, but not every launch needs every step. Present the full checklist, and Michelle picks what applies. It's a menu, not a mandate.

### Step 1: Gather Context

Before producing anything, build a clear picture of what's launching:

1. **Ask Michelle** what features/products are launching, key dates, and constraints
2. **Search Jira** for related tickets across MKTG, ENG, and product projects to understand scope and readiness
3. **Search Slack** in relevant channels (look for project-specific channels like #p-imgix-video, plus #product-done, #general, #sales) for recent discussions, decisions, and adoption data
4. **Check existing docs** if Michelle points you to documentation, Confluence pages, or specs
5. **Review past launches** on the Imgix blog (imgix.com/blog) to calibrate tone and structure

Synthesize findings into a brief context summary and share it with Michelle before proceeding. She'll correct gaps and confirm scope.

### Step 2: Present the Launch Checklist

Show Michelle the full checklist. She'll tell you what to include or skip. Default: include everything unless she says otherwise.

Read `references/launch-checklist.md` for the complete checklist with all items organized by phase.

### Step 3: Create the Content Package

**All draft deliverables must be produced as .docx files** (Word documents), not markdown. Michelle cannot read .md files. Use the `docx` skill for creation instructions. Each .docx should include proper headings, formatted callout boxes for design directions and value prop holes, and tables where appropriate.

For each selected deliverable, follow the content guides in the `references/` folder:

- **Blog post**: Read `references/blog-post-guide.md`
- **Email**: Read `references/email-guide.md`
- **Social posts**: Read `references/social-guide.md`
- **Changelog, internal comms, sales brief**: Read `references/supporting-content-guide.md`

All content must pass the Imgix brand voice self-check before presenting to Michelle:
1. Does every section lead with a benefit or reader-relevant insight?
2. Is there a clear problem-to-solution structure?
3. Would a smart marketer AND a developer both find this credible?
4. Does it reinforce the "one platform" narrative where appropriate?
5. Is the tone direct and warm without being casual or hype-driven?
6. Is "Imgix" capitalized correctly everywhere?
7. Are paragraphs short and scannable?
8. Zero filler adverbs (seamlessly, effortlessly, etc.)?
9. Em dashes used with extreme discretion? (One per page max.)
10. All CTA links include properly formatted UTM parameters?

### Step 4: Review and Refine

1. Present all drafted content to Michelle
2. Apply her feedback
3. Re-run the brand voice self-check
4. Confirm UTM parameters on every link

### Step 5: Michelle's Handoff Workflow

Once the working doc is in good shape, Michelle follows a specific handoff sequence. Understand this so you can support each phase:

1. **Casey (designer)**: Gets the doc first. Casey reads the inline `[Casey: ...]` directions and starts on visual assets. This happens in parallel with step 2.
2. **Mac/Product (validation)**: Gets the doc to validate that everything is technically correct, that features are described accurately, and to provide stats/quotes where placeholders exist. Mac may also flag things that need rewording.
3. **Parallel content creation**: While Casey designs and Mac validates, Michelle (with Claude's help) drafts the remaining launch materials: social posts, launch email, changelog, internal comms, sales enablement, landing pages. These all take their messaging cues from the blog post, so the blog body needs to be solid before this phase.
4. **Final assembly**: Stats from Mac get plugged in, Casey's assets get placed, and everything ships.

The goal of the working doc is to define how the launch talks about things. Once that's locked, everything else flows from it.

### Step 6: Prepare for Distribution

1. Create a distribution timeline (what publishes when)
2. Offer to create Jira subtasks under the launch ticket for tracking
3. Offer to schedule Slack messages or email drafts if tools are connected

## Pricing Dependencies

Pricing affects which assets can ship and which are blocked. For every launch, explicitly track pricing dependencies:

1. **Identify pricing-sensitive assets**: credit consumption guides, pricing FAQ, sales CPQ, in-product messaging, and any customer-facing email that references cost. These CANNOT publish with incorrect or missing pricing.
2. **Identify pricing-independent assets**: blog posts, social posts, and internal Slack announcements can usually ship without pricing if they focus on capabilities rather than cost. Note this in the distribution timeline.
3. **Create a pricing dependency tracker** listing every asset, what pricing info it needs, and whether it's blocked or can ship with a placeholder. Read `references/supporting-content-guide.md` for the tracker format.
4. **Flag the pricing conversation**: Draft specific questions for the product/eng pricing discussion. What credit costs apply to each new feature? Are there per-unit, per-GB, per-minute, or fixed-cost models? Does the analysis/conditional step cost credits even when it decides not to act?

Current Imgix credit structure (as of early 2026):
- Delivery: 1 credit/GB bandwidth
- Management: 2 credits/GB/month storage
- Image-to-Video: 250 credits fixed per use
- AI Transforms: 0.1 x media value (GB)
- Non-AI Edits: 0.002 x media value x 0.25

When new features launch, the pricing page (imgix.com/pricing), credit consumption docs, and pricing FAQ all need updating.

## Value Prop Placeholders

Value props should be woven into the body copy, not isolated in separate callout boxes. Write the sentence as if the stat exists, using a highlighted placeholder for the number. This makes the draft read naturally and shows Michelle exactly where the stat will land.

**Yes:** "Early beta partners are already testing with content up to 30 minutes in length, with processing times of [X] - any processing benchmarks?"
**Yes:** "In early testing, adaptive streams reduced buffering by [X]% and cut time-to-first-frame to under [Y] seconds."
**Also yes:** "Max, can we get any quote at all from a customer in beta?"
**No:** A separate yellow callout box that says "VALUE PROP HOLE: Need stat here about..."

When a stat is needed, use `[X]` inline and follow it with a plain-language question or note about who to ask. Questions directed at specific people (Max, Mac, etc.) can go on their own line. Keep stat requests focused on customer benefit ("how does this help the reader?"), not internal metrics.

Don't create separate summary tables of value prop holes. They're inline in the body where they'll actually land.

### Value Prop Stat Rules
- Every stat must describe a benefit to the reader, never an internal metric
- "X accounts using this" = not a value prop. "X% faster processing" = value prop.
- If you don't have the stat, write the ideal sentence with a placeholder and note who to ask
- Remove value prop holes Michelle says aren't necessary rather than keeping them as nice-to-haves

## Document Structure

A launch produces **one working document** that serves as the source of truth for the entire launch. Michelle works in this doc, and it's also what she hands to Casey (designer) and Mac (product) for their respective passes. The structure is:

1. **Header**: Document title (e.g., "Q2'26 Product Release"), target launch date, hard deadlines, and OOO dates that affect the timeline. This goes at the very top.
2. **Feature summary**: Numbered list of what's launching. Each feature gets one line: name, brief description, and any key context (beta customers, dependencies). This is the "at a glance" section.
3. **Pricing needs**: Explicit list of what needs pricing decisions before launch. Bullet out each item: credit formulas, pricing page updates, FAQ entries, CPQ updates, sales brief. If pricing can't ship with launch, say so.
4. **Materials development checklist**: Every deliverable needed for the launch, with **owner names assigned** where known (e.g., "Competitive landing pages (Drew)", "Sales CPQ updates (Glenn)"). This is a task list with accountability, not just a menu.
5. **Blog post body**: Title, subtitle, and full blog copy. Casey's design directions go **inline** as `[Casey: brief direction]` one-liners next to the relevant section. Stat placeholders go inline as `[X]` with a natural-language question. Questions for specific people go inline: "Max, can we get any quote from a beta customer?"
6. **Competitive summary**: How this release stacks up against competitors, with Imgix positioning for each feature area.

### What does NOT go in this doc
- Separate design brief documents (Casey reads the inline directions in the blog body)
- Appendix sections or "things to confirm" lists
- Value prop hole summary tables (holes are inline in the body copy)
- Pre-publish checklists (those live in conversation or Jira)

## Design Directions (Inline, Not Separate)

Design directions for Casey go **inline in the blog body** as bracketed one-liners next to the relevant section. They should be:

1. **Short and actionable.** One to two sentences max. Tell Casey what to create, not why it's important.
2. **Formatted as `[Casey: direction here]`** so they're visually distinct and easy to find when scanning.
3. **Concrete about what to show.** Describe the visual: subjects, layout, context. Don't describe the feeling or importance.

**Good inline directions:**
- `[Casey: Video-first hero image. Compilation showing Imgix Video capabilities together. Consider animated/GIF format.]`
- `[Casey: Same video on three devices (phone, laptop, TV). Show in context like an e-commerce page or media player.]`
- `[Casey: Video frame with English captions, then same frame with captions in Spanish, Japanese, French. Side-by-side or animation cycling through languages.]`
- `[Casey: Two-path visual: image goes through analysis, low-quality gets enhanced, high-quality passes through unchanged. Before/after or flowchart.]`

**Bad directions:**
- "This is the biggest wow feature. Consider showing something that captures the excitement." (editorial, not actionable)
- A full paragraph explaining the strategic importance of the visual (Casey doesn't need this)

If referencing past work for style consistency, do it briefly: `[Casey: Optional. If there is a compilation image we used for the last launch, we can see if it works here]`

## Landing Pages and Companion Content

For major new capabilities (like custom AI solutions), consider whether the launch needs a dedicated landing page in addition to the blog post. A landing page can:
- Include a contact/interest form for collecting leads
- Show detailed examples, before/afters, and case studies
- Serve as a persistent destination after the blog post ages off the homepage

Flag landing page opportunities to Michelle during the checklist phase (Step 2).

## Existing Feature Reminders

When launching new features in a category (e.g., new video features), consider adding a brief section that reminds readers of existing capabilities in that category. This reinforces the platform's depth and gives context for the new additions. Keep it short: a sentence and a few bullet points.

## Competitive Summary

Every launch doc should include a competitive summary section at the end, after the blog body. This section:

1. **Maps each launch feature against specific competitors.** Not a generic overview. For each feature, name what Cloudinary, Gumlet, ImageKit, Cloudflare, or other relevant competitors offer (or don't).
2. **Includes Imgix positioning for each feature.** Don't just list what competitors have. Articulate how Imgix positions against them. What's our angle? What's the architectural or experience advantage?
3. **Calls out gaps honestly.** If this release doesn't address a known competitive gap (e.g., MCP server, content moderation), list it under "Gaps NOT addressed by this release" so the team knows what's still open.
4. **Uses data from the Product Strategy Report** (Confluence) and any recent competitor scans. Don't rely on assumptions about what competitors offer.

This section is for internal use. It informs the sales brief, competitive landing pages, and battlecards.

## Competitive Landing Pages

For major releases that close competitive gaps, consider whether the launch should include competitive landing pages for paid campaigns and organic search. These are pages like "Imgix vs. Cloudinary" that target high-intent comparison searches.

Good timing for competitive pages:
- When the release brings Imgix to parity or ahead on a feature competitors previously owned
- When there's a clear architectural advantage to articulate (URL-based vs. API-based, one platform vs. separate products)
- When search volume exists for "[competitor] alternative" or "[competitor] vs" queries

Flag this opportunity during the checklist phase. Competitive pages are usually a fast-follow (week after launch), not day-one. The blog and core materials ship first, then competitive pages use the same messaging for sustained demand gen.

## Key Context to Keep in Mind

- **Three audiences**: developers (API simplicity, performance), product/eng leads (ROI, operational efficiency), marketers/creatives (creative possibilities, speed). Default to marketer-friendly framing with enough technical depth for developers.
- **"One platform" narrative**: Imgix replaces a patchwork of tools. Look for natural ways to reinforce that new features work alongside everything else. But don't overdo it in closings.
- **Past launches**: Reference imgix.com/blog for tone and structure. Recent releases follow a quarterly cadence (Q1, Q2, Q4 2025 all had launch posts).
- **UTM campaign format**: `q[quarter]_[year]_[feature]_launch` (e.g., `q2_2026_video_launch`)
- **Key people**: Max Knowles (product, video, "Mac"), Christopher Alkhaz (eng, video), Roya Paydarfar (product/design), Jason Baumeister (eng), Casey (designer), Glenn (sales CPQ), Drew (landing pages, web), Taichi (Cainz contact for permissions)
- **Channels**: #p-imgix-video (video project), #product-done (shipped work), #sales, #general
