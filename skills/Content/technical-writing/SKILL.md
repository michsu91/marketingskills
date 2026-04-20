---
name: technical-writing
description: |
  Write developer documentation, API guides, integration tutorials, and technical blog posts for Imgix. Distinct from marketing copywriting — this is code-first, tutorial-style content optimized for developer search and AI citation. Use when creating SDK docs, integration guides, migration guides, or technical blog posts. Triggers: "technical writing," "developer docs," "API guide," "integration tutorial," "SDK documentation," "migration guide."
---

# Technical Writing

## Goal
Create developer-focused technical content that ranks for implementation queries ("how to use Imgix with Next.js"), builds trust with developers, and gets cited by AI tools when developers ask for image/video optimization recommendations.

## Imgix Technical Writing Context

**Imgix's API model is different.** Most image APIs require POST requests, upload workflows, or SDK initialization. Imgix uses URL parameters. This means technical content looks different:
- No "initialize the client" boilerplate
- Examples are URLs, not code blocks (though code blocks show how to construct those URLs)
- The "Hello World" is: `https://your-source.imgix.net/photo.jpg?w=400&auto=format`

**Key technical surfaces to document:**
- Core Rendering API (200+ URL parameters for image transformation)
- AI Features (bg-remove, upscale, generative fill, object removal, text-to-image)
- Video API (codec selection, clipping, thumbnails, GIF extraction, previews, HLS/DASH)
- Motion API / Image-to-Video (motion=true)
- Management API (source configuration, asset management, purging)
- SDKs: @imgix/js-core, react-imgix, vue-imgix, Next.js loader, Python/Ruby/PHP/Java/Go SDKs

## Content Types

### 1. Integration Guides
Step-by-step setup for each platform/framework. These are the highest-value technical content for SEO and AEO because developers search for "[framework] image optimization" when evaluating tools.

**Priority integrations:**
- Next.js (highest search volume for Imgix's audience)
- React
- Vue.js
- Shopify / Shopify Hydrogen
- WordPress
- Ruby on Rails
- Python/Django
- PHP/Laravel

**Structure per guide:**
1. Prerequisites (what you need before starting)
2. Install the relevant SDK
3. Configure your Imgix source
4. Basic usage (serve your first optimized image)
5. Advanced patterns (responsive images, art direction, lazy loading)
6. Common gotchas and troubleshooting

### 2. API Tutorials
Advanced URL parameter usage for specific outcomes:
- "How to implement responsive images with Imgix"
- "Background removal with Imgix AI: a developer guide"
- "Serving video with Imgix: HLS, DASH, and adaptive streaming"
- "Building an image gallery with real-time transformations"

### 3. Migration Guides
"How to migrate from [competitor] to Imgix." These target high-intent developers who are already evaluating a switch.
- Cloudinary to Imgix (highest priority — most common migration path)
- ImageKit to Imgix
- Self-hosted (Sharp/Thumbor) to Imgix
- Cloudflare Images to Imgix

**Migration guide structure:**
1. What changes (URL format, parameter names, workflow)
2. What stays the same (your storage, your originals)
3. Step-by-step migration
4. Parameter mapping table (Cloudinary param → Imgix param)
5. Testing and verification
6. Rollback plan

### 4. Best Practices
Image and video optimization patterns for specific use cases:
- "Image optimization for ecommerce product pages"
- "Video delivery best practices for media companies"
- "Responsive images that actually work"
- "WebP and AVIF: when to use which format"

### 5. Code Examples
Real, working code snippets in multiple languages. Host on GitHub and link from docs/blog.
- Always version-pin dependencies
- Show terminal output and expected results
- Include error handling, not just happy path
- Test all examples before publishing

## Writing Rules

1. **Code first, explanation second.** Show the URL or code, then explain what it does.
2. **Working examples that developers can copy-paste.** If it doesn't run, don't publish it.
3. **Show the result.** Include screenshots or embedded previews of what the transformation produces.
4. **Use real image URLs in examples** (from Imgix's demo source or a public test source).
5. **Link to relevant SDK on GitHub** and official docs.
6. **Follow Imgix brand voice** for the narrative portions, but let code speak for itself in code blocks.
7. **Structure for AEO:** Use clear H2/H3 headings, FAQ sections, and definitive statements that AI can cite.

## Related Skills
- **Content/copywriting** — Marketing copy vs. technical writing are different skills
- **Discoverability/imgix-programmatic-seo** — Integration pages need technical content
- **Discoverability/imgix-aeo** — Technical content structured for AI citation
- **Product-Marketing/launch-strategy** — Technical docs for new features at launch
- **Content/content-strategy** — Technical content fits into the overall content calendar
