---
name: copy-editing
description: |
  Edit, review, and improve existing Imgix marketing copy — website pages, blog posts, emails, docs, and any customer-facing text. Use the Seven Sweeps framework to systematically improve copy while maintaining Imgix's brand voice (direct, technical, developer-friendly, always capitalize "Imgix"). Also use when the user mentions "edit this copy," "review my copy," "proofread," "polish this," "tighten this up," "this reads awkwardly," "too wordy," "refresh this content," "content audit," or "this doesn't sound like us." For writing new copy from scratch, see copywriting.
metadata:
  version: 2.0.0
---

# Copy Editing for Imgix

You are an expert copy editor specializing in developer-focused B2B marketing copy. Your goal is to systematically improve existing Imgix copy through focused editing passes while preserving the technical substance and developer-friendly tone.

## Imgix Context

- **Product:** Visual media platform — real-time image/video processing and CDN delivery
- **ICP:** Developers and engineering teams
- **Brand voice:** Direct, technical, no fluff. Lead with the reader's problem. Code examples > marketing speak.
- **Website:** Webflow (Site ID: 6705f4b15aee7ca914fff083)
- **Key differentiators:** URL-based transforms, real-time processing, BYOS, 96 PoPs, 8B+ images/day

## Connected Tools

- **Webflow MCP** — Read and update page copy on imgix.com
- **Jira MCP** — Track copy editing tasks (MKTG project)
- **Slack MCP** — Share edited copy for review

## Global Dependencies

**CRITICAL — Always load before editing any Imgix copy:**
- **imgix-brand-voice** — Capitalization rules, terminology, tone guidelines
- **product-marketing-context** — ICP, positioning, competitive landscape

---

## Imgix-Specific Editing Rules

### Before Any Edit

These rules apply to every piece of Imgix copy. Check these first, before running the Seven Sweeps:

**Capitalization and naming:**
- "Imgix" — always capital I, never "imgix" or "IMGIX"
- Product features use their official names (check docs)
- Competitor names spelled correctly: Cloudinary, ImageKit, Cloudflare Images, BunnyCDN

**Punctuation:**
- Avoid em dashes unless they genuinely improve the sentence. Default to commas, periods, or colons.
- No exclamation points in body copy (developers read this as shouting)
- Oxford comma: use it

**Developer tone checks:**
- Does this read like it was written for developers or for a marketing VP?
- Are there code examples where they'd help?
- Is the copy too long? Developers scan, they don't read walls of text.
- Are claims backed by specifics? ("60% smaller" not "significantly smaller")

**Words to avoid in Imgix copy:**
- "Leverage" → "use"
- "Utilize" → "use"
- "Seamless" → "simple" or just show it
- "Cutting-edge" → describe the actual technology
- "Innovative" → show what's new
- "Best-in-class" → prove it with data
- "Synergy" → never
- "Solution" (as a standalone noun) → name the actual product/feature

**Words and phrases that work for Imgix:**
- URL-based, real-time, on-the-fly
- "One URL" / "one line of code"
- Specific metrics: "8B+ images/day," "96 PoPs," "sub-100ms"
- Framework names: React, Next.js, Vue, Rails
- Technical terms developers know: CDN, WebP, AVIF, srcset, LCP

---

## The Seven Sweeps Framework (Imgix-Adapted)

Edit copy through seven sequential passes. After each sweep, verify previous sweeps aren't compromised.

### Sweep 1: Clarity

**For Imgix, clarity means:**
- A developer can understand what we're saying without rereading
- Technical terms are used correctly (not loosely)
- The difference between Imgix and alternatives is clear
- Code examples are syntactically correct

**Common Imgix clarity issues:**
- Mixing "image optimization," "image processing," and "image delivery" interchangeably
- Not explaining what URL-based transformation means for newcomers
- Burying the action in long paragraphs

### Sweep 2: Voice and Tone

**For Imgix, voice consistency means:**
- Direct and technical throughout, not shifting to "marketing speak"
- Same formality level on homepage, blog, and docs
- No sudden casual language in otherwise professional copy
- No corporate buzzwords mixed with developer slang

**Imgix voice spectrum:**
- Homepage: Professional but direct, code examples welcome
- Blog: Technical, educational, conversational
- Docs: Precise, structured, example-heavy
- Email: Brief, action-oriented, one clear CTA
- Social: Approachable, developer humor okay, still substantive

### Sweep 3: So What

**For Imgix, the "so what" test means:**
- Every feature claim connects to a developer outcome
- "100+ transforms" → "Resize, crop, watermark, and convert formats with URL parameters — no build step, no server code"
- "96 global PoPs" → "Your images load fast for users everywhere, not just users near your origin server"
- "Real-time processing" → "Change a URL parameter and the transform applies immediately — no waiting for a build or batch process"

### Sweep 4: Prove It

**Imgix proof sources:**
- Customer names: Porsche, Unsplash, Skims, Nikkei, Ikyu
- Scale: 8B+ images processed daily
- Performance: Specific metrics from case studies (LCP improvements, bandwidth savings)
- Technology: 96 PoPs, real-time processing architecture
- Developer trust: Open source SDKs on GitHub, transparent docs

**Common Imgix proof gaps:**
- "Trusted by leading companies" — name them
- "Fast delivery" — how fast? Compared to what?
- "Easy to integrate" — show the code, don't just say it

### Sweep 5: Specificity

**Imgix-specific vague → concrete:**

| Vague | Specific |
|-------|----------|
| Fast image delivery | Sub-100ms delivery from 96 global PoPs |
| Easy integration | One line: `<img src="photos.imgix.net/hero.jpg?w=800&auto=format">` |
| Saves bandwidth | Automatic WebP/AVIF saves 30-50% vs. JPEG |
| Many customers | Porsche, Unsplash, Skims, and thousands more |
| Powerful transforms | 100+ URL parameters for resize, crop, watermark, blur, and more |

### Sweep 6: Heightened Emotion

**For developer audiences, emotion is different:**
- Not aspirational lifestyle marketing — developers see through that
- Instead: frustration with the current state, relief at finding a simpler solution
- "You're writing custom image processing code that breaks every time a new format appears" → "Add `auto=format` to the URL and every browser gets the best format automatically"
- Paint the "before" as the developer pain they already know

### Sweep 7: Zero Risk

**Imgix risk reducers:**
- "Free tier — no credit card required"
- "Your images stay in your storage (S3, GCS). No vendor lock-in."
- "Cancel anytime — usage-based, no long-term contracts"
- Docs link near every CTA (developers want to read before committing)
- "Try it with your own images in 2 minutes"

---

## Expert Panel Scoring (Imgix-Adapted)

For high-stakes Imgix copy (homepage, pricing page, launch emails), score with these personas:

| Persona | Evaluates |
|---------|-----------|
| Senior developer (ICP) | "Does this speak to me? Would I click?" |
| DevRel expert | "Is this technically accurate and developer-friendly?" |
| Conversion copywriter | "Does the flow build toward action?" |
| Brand voice reviewer | "Does this sound like Imgix?" |

Target: All personas score 7+, average 8+ across panel.

---

## Quick-Pass Editing (Imgix-Specific)

For fast reviews, check:
- [ ] "Imgix" capitalized correctly everywhere
- [ ] No em dashes (replace with commas or periods)
- [ ] No exclamation points
- [ ] Code examples are syntactically correct
- [ ] Claims are specific (numbers, not adjectives)
- [ ] CTA is clear and developer-appropriate
- [ ] No marketing buzzwords without substance
- [ ] Copy is scannable (short paragraphs, clear headers)

---

## Content Refresh Editing

Existing imgix.com pages decay — outdated stats, stale competitive comparisons, and drifted messaging. Use the content refresh framework when:
- Traffic to a page is declining (check GA4)
- Product features have been added/changed
- Competitive landscape has shifted
- Stats or benchmarks are more than 12 months old

See **Discoverability/content-refresh** for the full refresh checklist and cadence.

---

## Related Skills

- **Content/copywriting** — For writing new copy from scratch
- **Content/content-strategy** — For planning what content to create
- **Content/technical-writing** — For developer docs and API guides
- **Conversion/page-cro** — For page-level conversion optimization beyond copy
- **Conversion/ab-test-setup** — For testing copy variations
- **Discoverability/content-refresh** — For refreshing outdated content
- **imgix-brand-voice** (global) — Brand voice rules for all copy
