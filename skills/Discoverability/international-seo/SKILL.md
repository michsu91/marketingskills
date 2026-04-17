# International SEO (Japan Focus)

## Goal
Optimize imgix's presence in Japanese search engines and Japanese-language AI answer engines. imgix already has Japanese localization set up in Webflow — this workstream ensures that localization actually drives discoverability in the Japanese market.

## Connected Tools
- **Webflow MCP** — Read and update Japanese locale content
  - Primary locale: English (ID: 673659649c948b4b79e06c75)
  - Secondary locale: Japanese (ID: 679d0cd07837e01906e3f5f7, CMS locale: 679d0cd07837e01906e3f5fb)
- **Web Search** — Check imgix's visibility in Japanese search queries
- **Jira MCP** — Track international SEO tasks
- **Slack MCP** — Notify Michelle of findings

## Current State
- Japanese locale is enabled in Webflow under /jp/ subdirectory
- Unclear how much Japanese content has been translated vs. left in English
- Japanese info request pages exist (/legal/japanese-info-request)
- Japan eBook content request page exists (/resources/content-request---japan-ebook)
- Key customer in Japan: Ikyu, TV Tokyo, Nikkei, Qiita — strong proof points

## Tasks

### Task 1: Japanese Locale Content Audit
Assess what content currently exists in Japanese and what's missing.

**How to execute:**
1. Use Webflow MCP to list all pages, filtering by Japanese locale
2. For each key page, check if Japanese content has been created or if it falls back to English
3. Document which priority pages have Japanese versions and which don't

**Priority pages for Japanese localization:**
1. Homepage
2. /solutions/ecommerce
3. /solutions/media
4. /how-it-works/ai-transformation
5. /pricing or pricing-related content
6. Case studies: Ikyu, TV Tokyo, Nikkei, Qiita (Japanese customers)
7. /contact
8. Key blog posts about features Japanese customers care about

### Task 2: Japanese SEO Keyword Research
Identify what Japanese users search for when looking for image optimization tools.

**Key query translations to research:**
- 画像最適化 (image optimization)
- 画像CDN (image CDN)
- 画像処理API (image processing API)
- リアルタイム画像変換 (real-time image transformation)
- eコマース画像最適化 (ecommerce image optimization)
- Cloudinary 代替 (Cloudinary alternative)
- imgix 比較 (imgix comparison)

**How to execute:**
1. Search each Japanese query and note who ranks
2. Check if imgix.com/jp/ pages appear in results
3. Note which competitors have Japanese-language content
4. Identify gaps where imgix could rank with localized content

### Task 3: Japanese Meta Tag Optimization
Ensure Japanese locale pages have proper Japanese SEO titles and descriptions — not just translations of English titles, but keyword-optimized Japanese copy.

**Principles for Japanese SEO:**
- Japanese search behavior differs from English — users often search with mixed Japanese/English terms
- Include brand names in katakana where appropriate
- Keep titles under ~32 characters for Japanese (displays differently in Google Japan)
- Meta descriptions can be slightly longer in Japanese due to character density

### Task 4: Hreflang Tag Verification
Ensure proper hreflang tags connect English and Japanese pages so Google serves the right language version to the right users.

**What to check:**
- Each English page should have `hreflang="ja"` pointing to its Japanese counterpart
- Each Japanese page should have `hreflang="en"` pointing to its English counterpart
- Both should have `hreflang="x-default"` pointing to the English version
- Webflow may handle this automatically — verify via source inspection

### Task 5: Japan-Specific Content
Create content specifically targeting the Japanese market.

**Opportunities:**
- Feature Japanese customer case studies prominently in Japanese locale (Ikyu: 16ms response time, 6B+ images; Nikkei: 1-second faster loading, 37% size reduction; TV Tokyo; Qiita: 23MB→3.4 seconds)
- Create Japanese-language comparison content targeting Japanese competitors
- Localize the FAQ page for Japanese-specific questions
- Consider Japanese developer community outreach (Qiita is huge for Japanese developers)

### Task 6: Japanese AEO
Check imgix's presence in Japanese AI answer engines and search AI features.

**Queries to monitor:**
- 「最適な画像CDNは？」(What's the best image CDN?)
- 「imgix vs Cloudinary」in Japanese search
- 「画像最適化ツール おすすめ」(Recommended image optimization tools)

## Execution Cadence
- **One-time:** Japanese locale content audit (Task 1)
- **One-time:** Japanese keyword research (Task 2)
- **One-time:** Hreflang verification (Task 4)
- **Monthly:** Check Japanese search visibility for key terms
- **Quarterly:** Refresh Japanese-localized content

## Related Skills
- **Discoverability/technical-seo** — Hreflang tags and locale configuration
- **Content/copywriting** — Localized content creation
- **imgix-brand-voice** (global) — Brand voice applies to all locales
- **Discoverability/reporting** — Track international search visibility separately
