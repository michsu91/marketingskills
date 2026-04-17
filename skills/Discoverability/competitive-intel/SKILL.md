# Competitive Intelligence

## Goal
Monitor competitor positioning, content strategy, and search visibility. Keep battlecards current and identify opportunities competitors are missing.

## Connected Tools
- **Claude in Chrome** — Browse competitor websites, check their latest content and positioning
- **Web Search** — Monitor competitor mentions, new content, and ranking changes
- **Jira MCP** — Create tickets when competitive intelligence reveals action items
- **Slack MCP** — Alert Michelle to significant competitor moves

## Competitors to Monitor

### Tier 1 (Direct Competitors)
1. **Cloudinary** — cloudinary.com — The primary competitor. Most feature-rich, dominant in search.
2. **ImageKit** — imagekit.io — Growing fast, developer-focused, competitive pricing.
3. **Cloudflare Images** — cloudflare.com/products/cloudflare-images — Leverages massive parent brand.

### Tier 2 (Adjacent Competitors)
4. **BunnyCDN** — bunny.net — Winning "best value" positioning in 2026.
5. **Uploadcare** — uploadcare.com — Strong in upload + processing workflow.
6. **Gumlet** — gumlet.com — Budget alternative, actively targeting imgix customers.

### Tier 3 (Emerging/Niche)
7. **Fastly Image Optimizer** — fastly.com — Strong JPEG XL and format support.
8. **tiny.pictures** — tiny.pictures — Niche, cloud-based processing.

## Monitoring Cadence

### Weekly (Automated via scheduled task)
- Search "[competitor name] + image CDN" and note any new content
- Check competitor blog RSS/recent posts for new comparison or feature content
- Search "imgix" in competitor content to see if they're targeting imgix users

### Monthly
- Full competitive content audit: what new pages have they published?
- Check competitor pricing pages for changes
- Update the battlecard document
- Run AEO comparison queries (who gets cited for what?)

### Quarterly
- Deep competitive positioning analysis
- Update the comparison pages in content-gaps workstream
- Review and refresh competitive messaging in imgix's own content

## Battlecard Template

For each competitor, maintain a battlecard with:

### Quick Facts
- Company size, funding, pricing model
- Key differentiators they claim
- Their ideal customer profile

### Their Strengths (Be Honest)
- What they do better than imgix
- Where they have more content/SEO presence
- Features they have that imgix doesn't

### Their Weaknesses
- Where imgix genuinely outperforms
- Gaps in their offering
- Customer complaints (from G2, Reddit, etc.)

### "When They Say X, We Say Y"
- Counter-messaging for their top 5 sales claims
- Fact-based responses, never disparaging

### Content Strategy Observations
- What topics are they publishing about?
- What keywords are they targeting?
- What content formats do they use? (guides, vs pages, tutorials, etc.)
- What's missing from their content that imgix could fill?

## Current Intelligence (From Baseline)

### Cloudinary
- **Content strategy:** Massive library of /guides/vs/ pages targeting every competitor. Extensive tutorial content.
- **Positioning:** "Comprehensive media experience platform" — positions as the enterprise all-in-one solution
- **Key weakness:** Pricing gets expensive at scale. Complexity is a real barrier for smaller teams.
- **Opportunity:** They own the comparison narrative because imgix has no counter-content. Fix this immediately.

### ImageKit
- **Content strategy:** Developer-focused blog, competitive pricing messaging
- **Positioning:** "The affordable Cloudinary alternative" with strong developer experience
- **Key weakness:** Not proven at imgix's scale (8B+ images/day). Limited enterprise customer base.
- **Opportunity:** imgix can outposition on scale, reliability, and enterprise credibility.

### Cloudflare Images
- **Content strategy:** Benefits from parent brand's massive content ecosystem
- **Positioning:** "Simple image hosting bundled with your existing Cloudflare setup"
- **Key weakness:** Very limited transformation capabilities compared to imgix. No AI features.
- **Opportunity:** Create content showing what imgix can do that Cloudflare Images simply can't (AI transforms, advanced processing).

### BunnyCDN
- **Content strategy:** Community-driven, value-focused, strong in listicle recommendations
- **Positioning:** "Best value image CDN" — $10-12/month for most sites
- **Key weakness:** Trailing on format support (limited AVIF), fewer advanced features
- **Opportunity:** Different market segment, but imgix could lose developer mindshare if BunnyCDN keeps winning "best of" lists.

## Output
All competitive intelligence updates should be:
1. Written to this folder's STATUS.md
2. Summarized in Slack for Michelle
3. Actioned via Jira tickets when they reveal work to do

## Related Skills
- **Product-Marketing/competitor-alternatives** — Competitive intel feeds into comparison pages and battle cards
- **Discoverability/imgix-aeo** — AEO monitoring reveals how AI models describe competitors
- **Discoverability/content-gaps** — Competitor content analysis reveals keyword gaps
- **Product-Marketing/win-loss-analysis** — Deal outcomes validate competitive positioning
- **Product-Marketing/sales-enablement** — Competitive intel becomes sales collateral
