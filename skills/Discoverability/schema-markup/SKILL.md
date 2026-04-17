---
name: schema-markup
description: |
  Implement and optimize structured data on imgix.com for rich results and AEO visibility. Covers Organization, SoftwareApplication, Article, HowTo, FAQPage, and BreadcrumbList schema on Webflow. Also use when the user mentions "schema markup," "structured data," "JSON-LD," "rich snippets," "schema.org," "FAQ schema," "breadcrumb schema," "Google rich results," or "add structured data." For broader SEO issues, see technical-seo. For AI search optimization, see imgix-aeo.
metadata:
  version: 2.0.0
---

# Schema Markup for Imgix

You are an expert in structured data and schema markup. Your goal is to implement schema.org markup on imgix.com that helps search engines and AI answer engines understand Imgix's content and enables rich results in search.

## Imgix Context

- **Product:** Visual media platform — real-time image/video processing and CDN delivery
- **Website:** Webflow (Site ID: 6705f4b15aee7ca914fff083)
- **Key pages:** Homepage, solutions (ecommerce, media, real estate, automotive), pricing, blog, docs, case studies, comparison pages
- **Rich result goals:** SoftwareApplication (pricing), Article (blog), FAQPage (FAQ sections on comparison/feature pages), HowTo (tutorials), Organization (homepage/about), BreadcrumbList (all pages)

## Connected Tools

- **Webflow MCP** — Inject JSON-LD via custom code head sections on pages
- **Claude in Chrome** — Validate schema via Rich Results Test, inspect existing markup
- **Jira MCP** — Track schema implementation tasks (MKTG project)

## Global Dependencies

Always load before implementing schema:
- **imgix-brand-voice** — Ensure schema descriptions match brand voice
- **product-marketing-context** — Company info for Organization schema

---

## Schema Types for Imgix

### Priority 1: Organization (Homepage)

Establishes Imgix's identity in Google's Knowledge Graph.

```json
{
  "@context": "https://schema.org",
  "@type": "Organization",
  "name": "Imgix",
  "url": "https://imgix.com",
  "logo": "https://imgix.com/logo.png",
  "description": "Visual media platform for real-time image and video processing and CDN delivery.",
  "sameAs": [
    "https://twitter.com/imgabortech",
    "https://www.linkedin.com/company/imgix/",
    "https://github.com/imgix"
  ],
  "contactPoint": {
    "@type": "ContactPoint",
    "contactType": "sales",
    "url": "https://imgix.com/contact"
  }
}
```

### Priority 2: SoftwareApplication (Pricing & Product Pages)

Enables rich product information in search results.

```json
{
  "@context": "https://schema.org",
  "@type": "SoftwareApplication",
  "name": "Imgix",
  "applicationCategory": "DeveloperApplication",
  "operatingSystem": "Web",
  "description": "Real-time image and video processing via URL-based transforms with CDN delivery from 96 global PoPs.",
  "offers": {
    "@type": "Offer",
    "price": "0",
    "priceCurrency": "USD",
    "description": "Free tier available. Usage-based pricing for Growth and Enterprise plans."
  },
  "aggregateRating": {
    "@type": "AggregateRating",
    "ratingValue": "4.5",
    "ratingCount": "50",
    "bestRating": "5"
  }
}
```

*Note: Only include aggregateRating if Imgix has verified G2/Capterra ratings to reference. Update ratingValue and ratingCount with actual numbers.*

### Priority 3: Article (Blog Posts)

Every blog post should have Article schema. In Webflow, this can be templated via the CMS collection.

```json
{
  "@context": "https://schema.org",
  "@type": "Article",
  "headline": "[Post Title]",
  "description": "[Meta description]",
  "image": "[Hero image URL via Imgix]",
  "datePublished": "[ISO 8601 date]",
  "dateModified": "[ISO 8601 date]",
  "author": {
    "@type": "Organization",
    "name": "Imgix"
  },
  "publisher": {
    "@type": "Organization",
    "name": "Imgix",
    "logo": {
      "@type": "ImageObject",
      "url": "https://imgix.com/logo.png"
    }
  }
}
```

### Priority 4: FAQPage (Comparison & Feature Pages)

FAQ schema is critical for both rich results and AEO. Add to comparison pages (vs Cloudinary, vs ImageKit) and feature pages.

```json
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    {
      "@type": "Question",
      "name": "How does Imgix compare to Cloudinary?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Imgix offers a simpler URL-based API with BYOS (bring your own storage) so your images stay in your S3 or GCS bucket. Cloudinary uses a credit-based pricing model and requires uploading assets to their storage."
      }
    },
    {
      "@type": "Question",
      "name": "Does Imgix work with my existing image storage?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Yes. Imgix connects to your existing S3, Google Cloud Storage, or Azure Blob storage. Your images stay where they are, and Imgix processes and delivers them in real time."
      }
    }
  ]
}
```

### Priority 5: HowTo (Tutorials & Getting Started)

For developer tutorial content and getting-started guides.

```json
{
  "@context": "https://schema.org",
  "@type": "HowTo",
  "name": "How to Optimize Images with Imgix",
  "description": "Connect your image storage and serve optimized images in minutes using URL-based transforms.",
  "step": [
    {
      "@type": "HowToStep",
      "name": "Connect your storage source",
      "text": "Add your S3, GCS, or Azure Blob storage as a source in the Imgix dashboard."
    },
    {
      "@type": "HowToStep",
      "name": "Configure your subdomain",
      "text": "Set up a custom subdomain (e.g., images.yoursite.com) to serve images through Imgix."
    },
    {
      "@type": "HowToStep",
      "name": "Add URL parameters",
      "text": "Append parameters like ?w=800&auto=format to your image URLs for real-time transforms."
    }
  ]
}
```

### Priority 6: BreadcrumbList (All Pages)

Breadcrumbs should be on every page. Webflow may generate some of this, but verify.

```json
{
  "@context": "https://schema.org",
  "@type": "BreadcrumbList",
  "itemListElement": [
    { "@type": "ListItem", "position": 1, "name": "Home", "item": "https://imgix.com" },
    { "@type": "ListItem", "position": 2, "name": "Solutions", "item": "https://imgix.com/solutions" },
    { "@type": "ListItem", "position": 3, "name": "Ecommerce", "item": "https://imgix.com/solutions/ecommerce" }
  ]
}
```

---

## Implementation on Webflow

### Static Pages

Add JSON-LD to each page's custom head code in Webflow:
1. Open page settings in Webflow
2. Scroll to "Custom Code" section
3. Paste the JSON-LD `<script type="application/ld+json">` block in the head
4. Publish changes

### CMS Collection Pages (Blog)

For blog posts, use Webflow's CMS dynamic fields within the JSON-LD:
1. Create a code embed in the blog post template
2. Use dynamic field references for headline, date, image, description
3. The template renders unique schema for each blog post

### Combining Multiple Types

Use `@graph` on pages that need multiple schema types (e.g., homepage gets Organization + WebSite + BreadcrumbList):

```json
{
  "@context": "https://schema.org",
  "@graph": [
    { "@type": "Organization", "name": "Imgix", "url": "https://imgix.com" },
    { "@type": "WebSite", "name": "Imgix", "url": "https://imgix.com" },
    { "@type": "BreadcrumbList", "itemListElement": [...] }
  ]
}
```

---

## Page-by-Page Schema Plan

| Page | Schema Types | Priority |
|------|-------------|----------|
| Homepage | Organization, WebSite, BreadcrumbList | HIGH |
| /pricing | SoftwareApplication, BreadcrumbList | HIGH |
| /solutions/* | FAQPage (add FAQ sections), BreadcrumbList | HIGH |
| /blog/* | Article, BreadcrumbList | HIGH |
| Comparison pages (vs Cloudinary, etc.) | FAQPage, BreadcrumbList | HIGH |
| /customers/* (case studies) | Article, BreadcrumbList | MEDIUM |
| Getting started / tutorials | HowTo, BreadcrumbList | MEDIUM |
| /about | Organization, BreadcrumbList | LOW |
| /contact | ContactPoint, BreadcrumbList | LOW |

---

## Validation and Testing

### Tools

- **Google Rich Results Test**: https://search.google.com/test/rich-results
- **Schema.org Validator**: https://validator.schema.org/
- **Search Console**: Enhancements reports for monitoring

### Testing Checklist

- [ ] Validates in Google Rich Results Test with no errors
- [ ] No warnings for missing recommended fields
- [ ] Schema matches visible page content
- [ ] All URLs are fully qualified (https://imgix.com/...)
- [ ] Dates are ISO 8601 format
- [ ] Images served through Imgix CDN (dogfooding)

### Common Errors to Watch For

- **Mismatched content**: Schema description doesn't match visible page text
- **Missing images**: Article and Product schema require image fields
- **Stale dates**: Blog posts with dateModified older than actual last update
- **Duplicate schema**: Multiple conflicting Organization schemas across pages

---

## AEO Impact

Schema markup directly improves AEO performance:
- FAQPage schema gives AI models structured Q&A pairs to cite
- Organization schema establishes entity recognition
- Article schema helps AI models identify authoritative content
- HowTo schema provides step-by-step instructions AI models prefer

Prioritize FAQ schema on comparison pages, as these are the most likely to be cited when users ask AI "How does Imgix compare to Cloudinary?"

---

## Metrics

| Metric | Target |
|--------|:------:|
| Rich results appearing in search | Track via Search Console |
| FAQ rich results on comparison pages | Visible within 4 weeks |
| Schema validation errors | Zero |
| Pages with schema implemented | 100% of priority pages |

---

## Related Skills

- **Discoverability/technical-seo** — Schema is a technical SEO element
- **Discoverability/imgix-aeo** — FAQ schema improves AEO citations
- **Discoverability/site-architecture** — Breadcrumb schema mirrors site hierarchy
- **Content/content-strategy** — Blog schema applies to all content
- **Product-Marketing/competitor-alternatives** — FAQ schema on comparison pages
- **imgix-brand-voice** (global) — Schema descriptions follow brand voice
