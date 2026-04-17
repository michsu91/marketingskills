# Content Refresh Strategy

## Goal
Keep existing content fresh and accurate. Google rewards content freshness — pages that haven't been updated in 12+ months gradually lose rankings. This workstream audits existing content, identifies what needs updating, and refreshes it to maintain and improve rankings.

## Connected Tools
- **Webflow MCP** — Read and update blog posts and page content via CMS
- **Web Search** — Check current SERPs to see if refreshed content needs to target new keywords
- **HubSpot MCP** — Identify which content still drives traffic/leads vs. which has decayed
- **Jira MCP** — Track content refresh tasks
- **Slack MCP** — Notify Michelle when refresh recommendations are ready

## Why Content Decays

- Competitors publish newer, better content on the same topics
- Statistics and data become outdated (e.g., "in 2024" in a 2026 search)
- Product features change but content still describes old capabilities
- New keywords emerge that the original content doesn't target
- Google's algorithm updates may change what content format ranks best

## Tasks

### Task 1: Content Age Audit
Review all published content and flag anything older than 6 months that hasn't been updated.

**How to execute:**
1. Pull all blog posts and static pages from Webflow with their last-updated dates
2. Sort by age (oldest first)
3. Cross-reference with traffic data from HubSpot (if available)
4. Create a priority matrix:

| Priority | Criteria |
|----------|---------|
| **HIGH** | Older than 12 months + still gets traffic → refresh to protect rankings |
| **HIGH** | Older than 6 months + targets a competitive keyword → refresh before competitors outrank |
| **MEDIUM** | Older than 12 months + low traffic → refresh if topic is still relevant, otherwise archive |
| **LOW** | Older than 6 months + evergreen topic that hasn't changed → light touch update |

### Task 2: Refresh Checklist
For each piece of content being refreshed:

1. **Check for outdated information:** stats, dates, product features, pricing, customer references
2. **Check current SERPs:** search the target keyword and see what's ranking now — does the content need to match a new format or angle?
3. **Update the year reference:** if the title or content mentions a year, update it
4. **Add new information:** new features, new case studies, new data points since original publish
5. **Improve internal links:** add links to newer content that didn't exist when originally published
6. **Check keyword targeting:** has search intent changed? Are there new related keywords to include?
7. **Update meta title and description:** refresh for current best practices
8. **Add FAQ section if missing:** FAQ content helps both SEO and AEO
9. **Update the published date** in the CMS after refresh

### Task 3: Case Study Freshness
Case studies are high-value pages. Check each one for:
- Are the customer metrics still current or have they improved?
- Is the customer still using imgix? (Don't promote a churned customer)
- Can we add updated results or expanded scope?
- Are the screenshots and visuals still accurate?

### Task 4: Product Content Sync
When imgix ships new features or changes pricing, existing content mentioning the old features/pricing needs updating.

**Process:**
1. After any product update, search all site content for mentions of the changed feature
2. Update all references
3. This should eventually be triggered by product release notes (manual for now)

### Task 5: Competitor Reference Updates
Content that references competitors needs periodic updates as competitors change their products and pricing.

**Check quarterly:**
- Are competitor pricing references still accurate?
- Have competitors launched features that change the comparison?
- Have competitors been acquired or rebranded?

## Content Refresh Templates

### Blog Post Refresh
When refreshing a blog post, add an "Updated [Month Year]" note at the top:
> *This post was originally published in [Month Year] and has been updated with the latest information as of [Month Year].*

### Case Study Refresh
Reach out to the customer contact to ask:
- "Can we update the case study with your latest metrics?"
- "Are there new use cases we should highlight?"

## Execution Cadence
- **Monthly:** Run content age audit, identify top 5 pages needing refresh
- **Monthly:** Refresh 3-5 pieces of content
- **After product updates:** Sync all affected content within 1 week
- **Quarterly:** Full case study freshness check

## Related Skills
- **Content/copy-editing** — Copy-editing improves refreshed content quality
- **Discoverability/technical-seo** — Refreshes may require meta tag updates
- **Discoverability/imgix-aeo** — Refresh content to include AEO-optimized elements
- **Discoverability/reporting** — Track ranking impact of content refreshes
- **Content/content-strategy** — Content calendar includes refresh cadence
