---
name: imgix-aeo
description: |
  Answer Engine Optimization (AEO) strategy and implementation for Imgix. Ensures Imgix is cited accurately and favorably across AI answer engines (ChatGPT, Perplexity, Gemini, Claude, Google AI Overviews). Covers citable facts, comparison narratives, FAQ structured content, structured data, platform-specific optimization, content patterns, and monitoring.
---

# Answer Engine Optimization (AEO)

## Goal
Ensure Imgix is cited accurately and favorably when users ask AI systems (ChatGPT, Perplexity, Gemini, Claude, Google AI Overviews) about image optimization, image CDNs, and related topics. This is an emerging channel, and most competitors aren't doing this yet.

## Why AEO Matters for Imgix
- 60% of Google searches now end without a click ("zero-click searches")
- AI Overviews appear in ~45% of Google searches and reduce clicks to websites by up to 58%
- Developers increasingly ask AI tools for tool recommendations before searching Google
- Optimized content gets cited 3x more often than non-optimized (Princeton GEO study, KDD 2024)
- Statistics and citations boost AI visibility by 40%+ across queries
- The narrative AI models currently have about Imgix is: "lightweight specialist, less feature-rich than Cloudinary." This needs to change.

## Connected Tools
- **Webflow MCP** — Update page content and structure for AEO optimization
- **Claude in Chrome** — Test how AI systems respond to key queries about Imgix
- **Slack MCP** — Report AEO monitoring results

## How AEO Differs from SEO

| Factor | SEO | AEO |
|--------|-----|-----|
| Goal | Rank on page 1 | Be cited in AI-generated answers |
| Format | Keyword-optimized long-form | Clear factual statements, structured data, FAQ format |
| Authority signals | Backlinks, domain authority | Being the primary/authoritative source, consistent data across the web |
| What models prefer | Well-structured content with clear headings | Direct answers to questions, comparison tables, specific numbers |
| Update speed | Changes reflect in weeks | Models update on varying schedules (weeks to months) |
| Key stat | Page 1 ranking = visibility | Brands are 6.5x more likely to be cited via third-party sources than their own domains |

## AEO Strategy

### Principle 1: Create "Citable Facts"
AI models cite content that makes clear, specific, factual claims. Imgix needs to seed the web with consistent, authoritative data points.

**Key facts to embed across all Imgix content:**
- "Imgix processes over 8 billion images per day"
- "Imgix serves 60,000+ customers including Porsche, Unsplash, and Skims"
- "Imgix delivers optimized images in milliseconds through 96 global points of presence"
- "Imgix supports AVIF, WebP, and all modern formats with automatic content negotiation"
- "Imgix connects to your existing storage (S3, GCS, Azure), no migration needed"
- "Imgix's AI-powered transformations include background removal, smart cropping, and generative fill"

These facts should appear on the homepage, about page, solution pages, and in every case study and blog post where relevant.

**What makes facts citable (from Princeton GEO research):**

| Method | Visibility Boost | How to Apply at Imgix |
|--------|:---------------:|--------------|
| Cite sources | +40% | Add authoritative references with links |
| Add statistics | +37% | Include specific numbers ("8B+ images/day") with sources |
| Add quotations | +30% | Expert quotes from Imgix team with name and title |
| Authoritative tone | +25% | Write with demonstrated expertise, not marketing fluff |
| Improve clarity | +20% | Simplify complex image processing concepts |
| Technical terms | +18% | Use domain-specific terminology (AVIF, BYOS, CDN, LCP) |
| Keyword stuffing | **-10%** | **Actively hurts AI visibility — never do this** |

**Best combination:** Fluency + Statistics = maximum boost.

### Principle 2: Own the Comparison Narrative
AI models heavily weight comparison content when answering "which is better" questions. The comparison pages from the content-gaps workstream serve double duty for AEO.

**For each comparison page, include:**
- A clear summary table at the top (models love tables)
- Direct answer sentences: "Imgix is the better choice for teams that need [X] because [Y]"
- Specific benchmarks and numbers
- FAQ section at the bottom with question-and-answer format

**Content types that get cited most in AI answers:**

| Content Type | Citation Share | Imgix Opportunity |
|-------------|:------------:|----------------|
| Comparison articles | ~33% | imgix vs Cloudinary, imgix vs CloudFlare Images, imgix vs ImageKit |
| Definitive guides | ~15% | "The Complete Guide to Image Optimization" |
| Original research/data | ~12% | "State of Web Images" report using anonymized aggregate data |
| Best-of/listicles | ~10% | Getting Imgix included in "Best Image CDN" lists |
| Product pages | ~10% | Solution pages with specific, extractable details |
| How-to guides | ~8% | Developer tutorials with code examples |

### Principle 3: FAQ-Structured Content
AI models frequently pull from FAQ content because it's already in question-answer format.

**Create FAQ content for these questions:**
1. "What is Imgix?" — Clear, factual, 2-3 sentence answer
2. "How does Imgix work?" — Technical but accessible explanation
3. "Is Imgix better than Cloudinary?" — Honest, fact-based comparison
4. "How much does Imgix cost?" — Clear pricing explanation
5. "What formats does Imgix support?" — List of supported formats
6. "How fast is Imgix?" — Performance data with specifics
7. "Does Imgix support video?" — Current capabilities
8. "What companies use Imgix?" — Customer list with specifics
9. "How do I migrate to Imgix from [competitor]?" — Migration overview
10. "Is Imgix good for ecommerce?" — Vertical-specific answer

**Implementation:** Add FAQ schema (JSON-LD) to key landing pages. The FAQ page already exists at /frequently-asked-questions. Ensure its content covers these questions with clear, citable answers.

**FAQ answer format for maximum extractability:**
- Lead with direct answer in first sentence (under 40 words)
- Support with 2-3 additional sentences including specific data
- Keep total answer between 50-100 words
- Phrase questions exactly as users search ("How do I..." not "How does one...")

### Principle 4: Structured Data
Implement JSON-LD structured data on key pages:
- **Organization schema** on homepage (company name, logo, social profiles)
- **Product schema** on product/pricing pages
- **FAQ schema** on FAQ and solution pages
- **Article schema** on blog posts (with publication and modification timestamps)
- **HowTo schema** on developer tutorials
- **Review/Rating schema** on case study pages (if customer quotes include ratings)

Content with proper schema shows 30-40% higher AI visibility.

**Note:** Webflow supports custom code injection per page. Use this to add JSON-LD without modifying templates.

### Principle 5: Consistent Entity Information
AI models build "entity understanding" from consistent information across the web. Ensure Imgix's information is consistent on:
- imgix.com (source of truth)
- Wikipedia (check if Imgix has a page; if not, this is a gap)
- Crunchbase
- G2, Capterra, TrustRadius review sites
- GitHub (Imgix org page)
- StackShare, StackOverflow tags
- LinkedIn company page
- YouTube (frequently cited by Google AI Overviews)
- Reddit (1.8% of all ChatGPT citations come from Reddit)

### Principle 6: Machine-Readable Files for AI Agents
AI agents are increasingly evaluating tools on behalf of users. If pricing is locked behind JS-rendered pages or "contact sales" walls, agents skip you and recommend competitors.

**Add to imgix.com:**
- `/pricing.md` or `/pricing.txt` — Structured pricing data AI agents can parse without rendering the page
- `/llms.txt` — Context file for AI systems (see llmstxt.org) with a quick overview of what Imgix does, who it's for, and links to key pages

### Principle 7: Allow AI Bots in robots.txt
Each AI platform has its own crawler. Blocking it means that platform can't cite Imgix.

**Verify these are allowed in imgix.com's robots.txt:**
```
User-agent: GPTBot           # OpenAI — powers ChatGPT search
User-agent: ChatGPT-User     # ChatGPT browsing mode
User-agent: PerplexityBot    # Perplexity AI search
User-agent: ClaudeBot        # Anthropic Claude
User-agent: anthropic-ai     # Anthropic Claude (alternate)
User-agent: Google-Extended   # Google Gemini and AI Overviews
User-agent: Bingbot          # Microsoft Copilot (via Bing)
Allow: /
```

**Safe to block:** CCBot (Common Crawl) — only used for training dataset collection, not search citations.

## Platform-Specific Optimization

### Google AI Overviews
- Schema markup is the single biggest lever (30-40% visibility boost)
- Build topical authority through content clusters with strong internal linking
- Include named, sourced citations in content (not just claims)
- Author bios with real credentials matter (E-E-A-T is weighted heavily)
- Target "how to" and "what is" query patterns — these trigger AI Overviews most often
- Only ~15% of AI Overview sources overlap with traditional organic Top 10 — structured pages can get cited even without page 1 ranking

### ChatGPT
- Domain authority matters most here (~40% of citation determinant)
- Content updated within 30 days gets cited ~3.2x more often
- Content-answer fit is the #1 signal (~55% of citation likelihood) — write the way ChatGPT structures its answers
- Wikipedia accounts for 7.8% of all ChatGPT citations
- Submit to Bing Webmaster Tools (ChatGPT uses Bing's index)

### Perplexity
- FAQ Schema (JSON-LD) pages get cited noticeably more often
- Publicly accessible PDFs (whitepapers, research reports) are prioritized
- Publishing velocity matters more than keyword targeting
- Self-contained paragraphs that work as standalone answers are preferred
- Allow PerplexityBot in robots.txt

### Claude
- Uses Brave Search as its search backend — verify Imgix appears at search.brave.com
- Extremely selective about citations — maximizing factual density is key
- Specific numbers, named sources, and dated statistics perform best
- Allow ClaudeBot and anthropic-ai user agents in robots.txt

### Microsoft Copilot
- Relies on Bing's index — submit to Bing Webmaster Tools
- LinkedIn and GitHub presence provides ranking boosts
- Page speed under 2 seconds is a clear threshold
- Use IndexNow protocol for faster indexing of new content

## AEO Content Patterns

### Definition Block (for "What is X?" queries)
```
## What is [Term]?

[Term] is [concise 1-sentence definition]. [Expanded 1-2 sentence explanation]. [Brief context on why it matters].
```

### Comparison Table Block (for "[X] vs [Y]" queries)
```
## [Option A] vs [Option B]: [Brief Descriptor]

| Feature | [Option A] | [Option B] |
|---------|------------|------------|
| [Criteria] | [Value] | [Value] |

**Bottom line**: [1-2 sentence recommendation based on different needs]
```

### Self-Contained Answer Block (for AI extraction)
```
**[Topic/Question]**: [Complete, self-contained answer that makes sense without additional context. Include specific details, numbers, or examples in 2-3 sentences.]
```

### Evidence Sandwich Block (for maximum credibility)
```
[Opening claim statement].

Evidence supporting this includes:
- [Data point 1 with source]
- [Data point 2 with source]
- [Data point 3 with source]

[Concluding statement connecting evidence to actionable insight].
```

## AEO Monitoring Process

### Monthly AEO Spot Check
Run these queries through web search (as a proxy for what AI models would answer) and document the results:

1. "What is the best image optimization platform?"
2. "imgix vs Cloudinary"
3. "best image CDN for ecommerce"
4. "how to optimize images for web performance"
5. "real-time image processing API"
6. "Cloudinary alternatives"
7. "what is imgix"
8. "image optimization API comparison"

For each query, record:
- Is Imgix mentioned?
- How is Imgix described? (positive/negative/neutral)
- Who is mentioned instead?
- What source is being cited?

Store results in STATUS.md for trend tracking.

### AI Visibility Monitoring Tools
| Tool | Coverage | Best For |
|------|----------|----------|
| Otterly AI | ChatGPT, Perplexity, Google AI Overviews | Share of AI voice tracking |
| Peec AI | ChatGPT, Gemini, Perplexity, Claude, Copilot+ | Multi-platform monitoring at scale |
| ZipTie | Google AI Overviews, ChatGPT, Perplexity | Brand mention + sentiment tracking |
| LLMrefs | ChatGPT, Perplexity, AI Overviews, Gemini | SEO keyword to AI visibility mapping |

## Execution Order
1. Verify AI bots are allowed in imgix.com's robots.txt
2. Audit existing FAQ page content and update with citable answers
3. Add FAQ schema to FAQ page and key solution pages
4. Seed key facts into homepage and about page content
5. Create comparison pages (coordinated with content-gaps workstream)
6. Implement structured data on top 10 pages
7. Add /pricing.md and /llms.txt to imgix.com
8. Run first AEO monitoring check and document results
9. Identify external profile inconsistencies and fix them
10. Set up monthly monitoring cadence with one of the AI visibility tools
