# Discoverability Reporting

## Goal
Track progress against the baseline, identify what's working, and surface what needs attention. Reports should be concise and actionable.

## Connected Tools
- **Web Search** — Run keyword visibility checks
- **Webflow MCP** — Pull current page metadata to verify changes
- **HubSpot MCP** — Pull lead attribution data to see which content drives signups
- **Slack MCP** — Post report summaries
- **Jira MCP** — Update tickets with reporting data

## Report Types

### Weekly SEO Pulse (Every Monday)
Quick check on key metrics. Should take ~15 minutes to run.

**What to check:**
1. Run spot-check searches for top 5 target keywords — note any ranking changes
2. Check if any new pages have been published or modified in Webflow this week
3. Review STATUS.md in each subfolder for progress updates
4. Summarize in 5-10 bullet points

**Output:** Post to Slack + update this folder's STATUS.md

### Monthly Discoverability Report (First week of each month)
Comprehensive review of all discoverability metrics.

**What to include:**
1. **SEO section:**
   - Keyword visibility changes for all tracked terms (vs. baseline)
   - New content published this month
   - Technical SEO fixes applied
   - Pages with improved/declined visibility

2. **AEO section:**
   - Run full AEO monitoring query set (8 queries from aeo/SKILL.md)
   - Compare to previous month's AEO spot check
   - Note any changes in how AI models describe imgix

3. **Competitive section:**
   - Notable competitor moves this month
   - New competitor content targeting imgix's keywords
   - Changes to competitor positioning or pricing

4. **Content section:**
   - Content published this month
   - Content in pipeline
   - Content performance (clicks from HubSpot if available)

5. **Action items:**
   - Top 3 priorities for next month
   - Any blockers that need Michelle's attention

**Output:** Markdown report saved to this folder + posted to Slack + Jira ticket created

### Quarterly Baseline Re-measurement (Every 3 months)
Full re-run of the original baseline methodology.

**What to do:**
1. Re-run all keyword visibility searches from BASELINE.md
2. Re-run all AEO spot checks
3. Re-audit Webflow page metadata for any new issues
4. Update BASELINE.md with new data and comparison to original
5. Adjust priorities in MANIFEST.md based on what's changed

**Output:** Updated BASELINE.md + quarterly summary document + Slack post

## Tracked Keywords

### Primary (Check Weekly)
1. "image CDN"
2. "best image CDN"
3. "image optimization API"
4. "real-time image processing"
5. "imgix vs Cloudinary"

### Secondary (Check Monthly)
6. "Cloudinary alternatives"
7. "image optimization for ecommerce"
8. "best image CDN 2026"
9. "imgix vs Cloudflare"
10. "imgix vs ImageKit"
11. "automatic image optimization"
12. "image processing API"
13. "AVIF image optimization"
14. "responsive image delivery"
15. "image CDN for developers"

### AEO Queries (Check Monthly)
See aeo/SKILL.md for the full list of 8 monitoring queries.

## Reporting Format
Keep reports scannable. Use this structure:

```
# [Report Type] — [Date]

## TL;DR
[3 bullet points: biggest win, biggest concern, top priority]

## Details
[Organized by section]

## Action Items
[Numbered list, assigned to person or workstream]
```

## Related Skills
- **Discoverability/imgix-aeo** — AEO monitoring results feed into reports
- **Conversion/analytics-tracking** — Tracking data flows into discoverability reports
- **Discoverability/competitive-intel** — Competitive position changes tracked in reports
- **Discoverability/content-gaps** — Gap closure progress reported
- **Discoverability/technical-seo** — Technical health metrics in reports
