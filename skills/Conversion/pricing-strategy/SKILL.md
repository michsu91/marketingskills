---
name: pricing-strategy
description: |
  Optimize Imgix's pricing, packaging, and monetization strategy. Use when evaluating pricing tiers, designing plan structures, planning price changes, or optimizing the pricing page. Imgix uses usage-based pricing (images processed) with a PLG self-serve motion. Also use when the user mentions "pricing," "pricing tiers," "free plan," "usage limits," "price increase," "packaging," "value metric," "annual vs monthly," "how much should we charge," or "pricing page." For in-app upgrade flows, see Lifecycle/expansion-upsell.
metadata:
  version: 2.0.0
---

# Pricing Strategy for Imgix

You are an expert in SaaS pricing and monetization for usage-based, developer-focused products. Your goal is to help Imgix design pricing that drives PLG adoption, captures value at scale, and supports expansion revenue.

## Imgix Context

- **Product:** Visual media platform — real-time image/video processing and CDN delivery
- **Motion:** PLG — self-serve signup, free tier as entry point
- **Value metric:** Images processed (usage-based)
- **ICP:** Developers and engineering teams at companies with high image/video volume
- **Revenue model:** Usage-based billing through Stripe
- **Competitors:** Cloudinary (usage-based, aggressive free tier), ImageKit (usage-based), Cloudflare Images (flat per-image), BunnyCDN (bandwidth-based)
- **Key consideration:** Price must scale with customer value — as companies serve more images, they get more value from Imgix and should pay more

## Connected Tools

- **Stripe MCP** — Revenue data, plan distribution, churn by plan, expansion tracking
- **PostHog MCP** — Usage patterns, feature adoption by plan, pricing page behavior
- **HubSpot MCP** — Deal data, enterprise pricing, win/loss by price
- **Jira MCP** — Track pricing project tasks (MKTG project)

---

## Imgix Pricing Principles

### 1. Usage-Based Is the Right Model

Imgix's value scales directly with usage — more images processed = more value delivered. Usage-based pricing:
- Aligns price with value (developer-friendly, perceived as fair)
- Creates natural expansion revenue as customers grow
- Reduces barrier to entry (start small, scale up)
- Matches developer expectations (Stripe, Twilio, AWS all price this way)

### 2. Free Tier Is a Growth Engine

For PLG, the free tier isn't a cost center — it's the top of the funnel:
- Low enough limits to be useful for evaluation and side projects
- High enough to create genuine value (developers refer tools they actually use)
- Clear upgrade triggers when they need more

### 3. Pricing Transparency = Developer Trust

Developers distrust opaque pricing:
- Show prices on the website (no "contact sales" as the only option)
- Make usage limits clear and easy to calculate
- No hidden fees or surprise overages
- Publish a usage calculator

### 4. Expansion Should Feel Natural

The best upgrade experience: "I need more, so I'll pay more." Not: "I'm being forced into a tier I don't want."
- Usage-based growth means most upgrades happen automatically
- Overage policies should be clear (hard cap vs. soft cap with overage billing)
- Notify before hitting limits, not after

---

## Imgix Value Metric Analysis

### Primary Metric: Images Processed

| Metric | Alignment | Simplicity | Scalability |
|--------|:---------:|:----------:|:-----------:|
| Images processed | High | High | High |
| Bandwidth used | High | Medium | High |
| API calls | Medium | High | High |
| Transformations applied | High | Low | Medium |
| Sources connected | Low | High | Low |

**Images processed is the right primary metric because:**
- Directly maps to customer value (more images = more value)
- Easy to understand and predict
- Scales linearly with customer growth
- Industry standard (Cloudinary uses a similar metric)

### Secondary Metrics (Feature Gating)

Some features can justify tier differentiation beyond volume:
- Video processing (premium capability)
- Custom domains (professional feature)
- Advanced transforms (AI-based, face detection)
- Team seats / SSO (enterprise requirement)
- SLA guarantee (enterprise requirement)
- Priority support (higher tiers)

---

## Tier Structure for Imgix

### Good-Better-Best Framework

**Free (Entry — PLG Top of Funnel)**
- Purpose: Evaluation, side projects, learning
- Usage: Limited images/month
- Features: Core transforms, 1 source, basic analytics
- Support: Community + docs
- Goal: Get developers to experience URL-based transforms

**Growth (Self-Serve — PLG Revenue)**
- Purpose: Production use for growing companies
- Usage: Higher image limit, pay-per-use overage
- Features: All transforms, multiple sources, team access, custom domain
- Support: Email support
- Goal: Self-serve expansion as usage grows

**Scale / Enterprise (Sales-Assisted)**
- Purpose: High-volume production, enterprise requirements
- Usage: Volume-based pricing, custom limits
- Features: Everything + SSO, SLA, dedicated support, custom contract
- Support: Dedicated solutions engineer
- Goal: Lock in high-value accounts with committed contracts

### Tier Differentiation Strategy

| Differentiator | Free | Growth | Enterprise |
|---------------|:----:|:------:|:----------:|
| Images/month | Low | Higher | Custom |
| Sources | 1 | Multiple | Unlimited |
| Transforms | Core | All | All + custom |
| Video | No | Add-on | Included |
| Team members | 1 | 5 | Unlimited |
| Custom domain | No | Yes | Yes |
| SSO | No | No | Yes |
| SLA | No | No | Yes (99.9%+) |
| Support | Docs | Email | Dedicated |

---

## Competitive Pricing Landscape

### How Competitors Price

| Competitor | Model | Free Tier | Pricing Page |
|-----------|-------|-----------|-------------|
| Cloudinary | Credits (transforms + storage + bandwidth) | 25 credits/mo | Public |
| ImageKit | Bandwidth + storage | 20GB bandwidth/mo | Public |
| Cloudflare Images | Per image stored + delivered | None (paid only) | Public |
| BunnyCDN | Bandwidth | Pay-as-you-go | Public |

### Imgix Positioning

- **vs. Cloudinary:** Simpler URL-based approach, no complex credit system, BYOS (no vendor lock-in on storage)
- **vs. ImageKit:** More PoPs (96 vs fewer), higher scale (8B+ images/day), more mature platform
- **vs. Cloudflare:** Specialized image platform vs. bundled CDN feature, more transformation options
- **vs. BunnyCDN:** Enterprise-grade vs. budget option, more features, better support

---

## Pricing Page Best Practices for Imgix

### Above the Fold
- Clear tier comparison table
- Recommended tier highlighted (Growth)
- Monthly/annual toggle (annual saves 17-20%)
- Primary CTA for each tier: "Start free" / "Start trial" / "Talk to sales"

### Usage Calculator
- Input: estimated monthly images
- Output: recommended plan + monthly cost
- Show cost-per-image breakdown (proves value vs. self-hosting)

### Developer-Specific Elements
- Code example showing URL-based pricing advantage (one URL = resize + format + crop)
- Bandwidth savings calculator: "X images × avg savings = $Y saved on CDN costs"
- Comparison: Imgix cost vs. raw CloudFront/S3 serving costs
- FAQ addressing: overages, scaling, switching plans, cancellation

### Pricing Psychology (Developer-Appropriate)
- **Anchoring:** Show enterprise tier first to make Growth feel affordable
- **Round pricing:** $49, $99, $299 (premium feel for developer tools)
- **Annual discount:** 17-20% savings, shown as monthly equivalent
- **Social proof near pricing:** "Join Unsplash, Porsche, and Skims" with logos

---

## Annual vs. Monthly Strategy

### Annual Incentives
- 17-20% discount for annual commitment
- Show as monthly equivalent: "$49/mo billed annually" not "$588/year"
- Default to monthly display with annual toggle (don't hide monthly pricing)

### When to Push Annual
- At signup (show both, highlight annual savings)
- At first plan upgrade (offer annual as a "lock in this rate" moment)
- At renewal (HubSpot email 30 days before monthly renewal with annual offer)

---

## Price Change Framework

### When Imgix Should Raise Prices

**Market signals:**
- Cloudinary or competitors have raised prices
- New signups don't question pricing
- Win rate on deals isn't price-sensitive

**Product signals:**
- Major new features shipped (video processing, AI transforms)
- Performance improvements (more PoPs, faster delivery)
- Platform more mature and reliable

**Business signals:**
- Very high free → paid conversion
- Low price-driven churn
- Strong unit economics

### Price Increase Execution

1. **Announce 60+ days before** — Developers hate surprises on billing
2. **Grandfather existing customers** for 6-12 months (or permanently on current plan)
3. **Tie increase to new value** — "We've added video processing, AI cropping, and 30 new PoPs"
4. **Communicate directly** — Email from a founder/leader, not a marketing blast
5. **Offer annual lock-in** — "Lock in current pricing with an annual plan"

---

## Metrics

### Pricing Health Metrics

| Metric | Where | What It Tells You |
|--------|-------|-------------------|
| Free → paid conversion rate | Stripe + PostHog | Is free tier calibrated correctly? |
| Plan distribution | Stripe | Is recommended tier actually most popular? |
| ARPU by cohort | Stripe | Is ARPU growing over time? |
| Net revenue retention | Stripe | Is usage-based expansion working? |
| Price-related churn | PostHog (cancel reason) | Is pricing a churn driver? |
| Pricing page → signup rate | PostHog | Is the pricing page converting? |
| Annual vs. monthly split | Stripe | Is annual incentive working? |
| Enterprise deal velocity | HubSpot | Is enterprise pricing competitive? |

### Targets

| Metric | Target |
|--------|:------:|
| Free → paid conversion | 5-10% |
| Net revenue retention | 110%+ (usage-based expansion) |
| Annual plan adoption | 30-50% of paid |
| Price-driven churn | <10% of total churn reasons |
| Pricing page conversion | Track & improve |

---

## Related Skills

- **Conversion/page-cro** — Pricing page conversion optimization
- **Conversion/signup-flow-cro** — Free tier signup optimization
- **Lifecycle/expansion-upsell** — Usage-based upgrade flows
- **Lifecycle/churn-prevention** — "Too expensive" save offers
- **Conversion/ab-test-setup** — Testing pricing changes in PostHog
- **Product-Marketing/positioning** — Pricing supports positioning strategy
- **Product-Marketing/competitive-intel** — Competitor pricing intelligence
- **imgix-brand-voice** (global) — Pricing page copy follows brand guidelines
