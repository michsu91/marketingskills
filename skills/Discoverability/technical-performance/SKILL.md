# Technical Performance (Core Web Vitals & Page Speed)

## Goal
Ensure imgix.com itself is a showcase of visual media performance. An image optimization company with a slow website undermines the entire brand promise. Monitor and optimize Core Web Vitals, page speed, and mobile experience as ranking signals.

## Connected Tools
- **Webflow MCP** — Inspect page structure, scripts, and assets
- **Claude in Chrome** — Run Lighthouse audits, visually inspect pages, check mobile rendering
- **Jira MCP** — Create tickets for performance issues that need engineering attention
- **Slack MCP** — Alert Michelle to performance regressions

## Key Metrics to Track

### Core Web Vitals (Google ranking signals)
- **LCP (Largest Contentful Paint):** Target < 2.5 seconds. Measures how fast the main content loads.
- **INP (Interaction to Next Paint):** Target < 200ms. Measures responsiveness to user interaction.
- **CLS (Cumulative Layout Shift):** Target < 0.1. Measures visual stability (things jumping around as the page loads).

### Additional Performance Metrics
- **TTFB (Time to First Byte):** Target < 800ms. How fast the server responds.
- **FCP (First Contentful Paint):** Target < 1.8 seconds. First visual content on screen.
- **Total page weight:** Target < 2MB per page for content pages, < 3MB for media-heavy showcases.
- **Image optimization:** Every image on imgix.com should be served through imgix itself (dogfooding).

## Tasks

### Task 1: Baseline Performance Audit
Run Lighthouse audits on key pages to establish current performance scores.

**Pages to audit (priority order):**
1. Homepage (imgix.com)
2. /solutions/ecommerce
3. /solutions/media
4. /how-it-works/ai-transformation
5. /pricing
6. /customers (case studies listing)
7. A sample blog post
8. /contact

**How to execute:**
1. Use Claude in Chrome to navigate to each page
2. Run Lighthouse via Chrome DevTools (Performance, Accessibility, Best Practices, SEO categories)
3. Record scores and specific issues
4. Create a baseline table in STATUS.md

### Task 2: Verify imgix Dogfooding
Every image on imgix.com should be served via imgix's own CDN. Check for any images being served from Webflow's default CDN, uploaded directly, or served from third-party sources.

**How to check:**
1. Use Claude in Chrome to inspect network requests on key pages
2. Filter for image requests
3. Flag any images NOT served through an imgix domain
4. Create Jira ticket for any non-imgix images found

### Task 3: Script and Third-Party Audit
Third-party scripts (analytics, chat widgets, tracking pixels) are often the biggest performance killers.

**What to check:**
- Total number of third-party scripts loaded
- Which scripts block rendering
- Unused or redundant scripts
- Script loading strategy (async, defer, lazy)

### Task 4: Mobile Performance Check
Over 60% of web traffic is mobile. imgix.com must perform well on mobile devices.

**What to check:**
- Mobile Lighthouse scores
- Touch target sizes
- Responsive image serving (are srcset and sizes attributes used?)
- Mobile-specific layout shift issues
- Font loading and text rendering on mobile

### Task 5: Ongoing Monitoring
Set up a regular check to catch performance regressions after site updates.

**Monitoring cadence:**
- **After every Webflow publish:** Spot-check homepage Lighthouse score
- **Weekly:** Run Lighthouse on homepage + one rotating page
- **Monthly:** Full audit of all 8 priority pages
- **Quarterly:** Deep performance review with comparison to baseline

## Performance Fix Playbook

When an issue is found, categorize and route it:

| Issue Type | Who Fixes It | How |
|-----------|-------------|-----|
| Images not through imgix | Michelle / Dev | Update image sources in Webflow |
| Large unoptimized assets | Claude via Webflow MCP | Optimize and replace |
| Third-party script bloat | Dev team | Audit and remove/defer scripts |
| CLS from layout shifts | Dev team | Fix CSS, add dimensions to images/embeds |
| Slow TTFB | Dev / Infrastructure | CDN config, Webflow hosting settings |
| Missing lazy loading | Claude via Webflow MCP | Add loading="lazy" to below-fold images |
| Font loading issues | Dev team | Preload critical fonts, use font-display: swap |
