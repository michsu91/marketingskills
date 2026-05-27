# Start Here

If you're new to this repo or picking it up from Michelle, read this first.

## What this is

A coordinated system of marketing skills that Claude sessions can run autonomously for Imgix. Six system folders (Acquisition, Content, Conversion, Discoverability, Lifecycle, Product-Marketing), one Data folder, two global skills loaded into every system run (imgix-brand-voice, product-marketing-context), and two reference skills invoked on demand (marketing-ideas, marketing-psychology).

It's a strong skeleton with a few well-developed muscles, not a turnkey system. This onramp hardens the parts that matter most.

## Who runs what

- **Glenn (owner / decision-maker):** Decides what to run, when, at what priority. Approves changes. Calls when something should be retired.
- **Drew (executor):** Runs the skills, manages outputs, updates MEMORY.md after each session, iterates on instructions.

## Before you invoke any skill

Each system folder has a `How to Use This Folder` section at the top of its MANIFEST.md. It tells you when to invoke, what context to bring, how the sub-skills fit, typical prompts, and what to expect. Read it before running anything.

## 30-day onramp

### Week 1: Orient and run your first session

- **Days 1-3:** Read this file, then the main README.md. Read `imgix-brand-voice/SKILL.md` and `product-marketing-context/SKILL.md`. Skim the "How to Use This Folder" section in each of the six system MANIFEST.md files.
- **Days 4-7:** Pick Discoverability as your first system (weekly cadence, well-developed sub-skills). Read its MANIFEST.md, BASELINE.md, and MEMORY.md. Do one real run: invoke `technical-seo` on imgix.com. Update Discoverability/MEMORY.md with what you ran and what you decided.

### Week 2: Establish a weekly rhythm

- Run the Discoverability weekly pulse: technical-seo audit, content-gaps scan, reporting summary.
- Run one Content production cycle: chain content-strategy, copywriting, social-content for one piece.
- After each session, update the relevant MEMORY.md.
- Identify any "Michelle" references in skill trigger conditions that misfire. Edit them out.

### Week 3: Expand to the other systems

- Add Acquisition: run a bi-weekly sprint on one channel (paid-ads, cold-email, lead-magnets, or free-tool-strategy).
- Add Conversion: set up one experiment with ab-test-setup plus page-cro or signup-flow-cro.
- Decide what to do with Lifecycle: 4 of 7 sub-skills are planned but not built. Either build them out this quarter or use email-sequence directly for now.
- Schedule growth-alpha to run 2x/week as a scheduled agent.

### Week 4: Settle into the full cadence

- Run the full suggested cadence: weekly (Discoverability, Content), bi-weekly (Acquisition), monthly (Conversion, Lifecycle).
- Do a quarterly Product-Marketing audit: positioning, sales enablement collateral, competitor battlecards.
- Compare current state against each system's BASELINE.md. Refresh BASELINE.md if it's materially stale.
- Retire what you haven't used: Tier 4 Discoverability sub-skills, unbuilt Lifecycle skills.

## What to refresh quarterly

These have hardcoded values that drift over time:

- `product-marketing-context/SKILL.md` (proof points, stats, competitor landscape)
- `Data/data-synthesis/SKILL.md` (dashboard URLs)
- `Data/growth-alpha/SKILL.md` and `Data/experiment-loop/SKILL.md` (revenue stats baked into context)
- `Product-Marketing/` sub-skills (customer names, proof points)
- MEMORY.md files in every system (continuously, not quarterly)

## When you're stuck

- Stuck on what to try next? Invoke `marketing-ideas`.
- Stuck on a conversion, pricing, or onboarding design call? Invoke `marketing-psychology`.
- Writing anything? Always pull `imgix-brand-voice` as the global anchor.
- Targeting question, value prop confusion, competitor positioning? Invoke `product-marketing-context`.

## Two principles to keep in mind

1. **Update MEMORY.md after every meaningful run.** This system improves over time only if Claude has a record of what worked and what didn't. Without MEMORY updates, every session starts cold.
2. **Fix the skill, not the output.** If a skill recommends an outdated tactic or misses context, edit the SKILL.md. The point of this system is compounding improvement, not one-off corrections.
