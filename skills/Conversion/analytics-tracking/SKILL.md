---
name: analytics-tracking
description: |
  Set up, improve, or audit analytics tracking for Imgix across PostHog (product analytics), GA4 (marketing site), HubSpot (lifecycle), and Stripe (revenue). Use when implementing event tracking, building dashboards, setting up conversion funnels, configuring UTM parameters, or debugging tracking issues. Also use when the user mentions "tracking," "PostHog," "GA4," "events," "conversion tracking," "UTM," "attribution," "analytics implementation," "tracking plan," or "are my events firing."
metadata:
  version: 2.0.0
---

# Analytics Tracking for Imgix

You are an expert in analytics implementation for developer-focused PLG products. Your goal is to set up tracking that provides actionable insights across Imgix's full funnel, from first website visit through activation, expansion, and retention.

## Imgix Context

- **Product:** Visual media platform — real-time image/video processing and CDN delivery
- **Motion:** PLG — self-serve signup, usage-based pricing
- **Marketing site:** Webflow (GA4 + PostHog tracking)
- **Product analytics:** PostHog (primary — events, funnels, cohorts, session replay, feature flags)
- **Web analytics:** GA4 (marketing site traffic, SEO performance, campaign attribution)
- **CRM/Lifecycle:** HubSpot (lifecycle stages, email engagement, lead scoring)
- **Revenue:** Stripe (usage, MRR, churn, expansion)
- **Key activation metric:** First image served through Imgix CDN with a transformation applied

## Connected Tools

- **PostHog MCP** — Query events, create insights, build funnels, analyze cohorts
- **HubSpot MCP** — Lifecycle stage tracking, email metrics, contact properties
- **Jira MCP** — Track analytics implementation tasks (MKTG project)
- **Slack MCP** — Alert on tracking issues or metric anomalies

---

## Imgix Analytics Stack

### Tool Responsibilities

| Tool | What It Tracks | Key Events |
|------|---------------|------------|
| **PostHog** | Product behavior, experiments, funnels | Signup, source connected, first transform, feature usage |
| **GA4** | Marketing site traffic, campaigns, SEO | Page views, CTA clicks, form submissions, traffic sources |
| **HubSpot** | Lifecycle stages, email engagement | MQL, SQL, lifecycle transitions, email opens/clicks |
| **Stripe** | Revenue, usage, billing | Payment, plan change, usage milestones, churn |

### Data Flow

```
GA4 (marketing site) → PostHog (product) → HubSpot (lifecycle) → Stripe (revenue)
         |                    |                    |                    |
    Traffic source      Activation          Lead stage           Revenue
    Campaign attr.      Feature usage       Email engage.        Expansion
    SEO performance     Experiments         Contact props        Churn
```

---

## Imgix Tracking Plan

### Marketing Site Events (GA4 + PostHog)

| Event | Properties | Trigger |
|-------|-----------|---------|
| `page_view` | page_title, page_path, referrer | Automatic (GA4 enhanced) |
| `cta_clicked` | button_text, location, page_path | Any CTA click |
| `pricing_page_viewed` | referrer, utm_source | Pricing page load |
| `plan_compared` | plans_viewed | Pricing toggle/tab interaction |
| `signup_started` | source_page, utm_source, utm_medium | Signup form focus |
| `signup_completed` | method (email/google/github), utm_source | Account created |
| `demo_requested` | company_size, use_case | Demo form submitted |
| `docs_clicked` | doc_section, source_page | Link to docs |
| `content_downloaded` | asset_name, asset_type | Gated content download |

### Product Events (PostHog)

| Event | Properties | Trigger |
|-------|-----------|---------|
| `source_connected` | source_type (S3/GCS/Azure), time_since_signup | Storage source added |
| `source_configured` | source_name, subdomain | Source settings saved |
| `first_image_served` | source_type, time_since_signup | First CDN request |
| `first_transform_applied` | transform_type (resize/crop/format/etc), time_since_signup | First URL parameter used |
| `transform_used` | transform_type, count | Any transformation |
| `api_call_made` | endpoint, sdk_language | API request |
| `dashboard_login` | login_method | Dashboard access |
| `billing_page_viewed` | current_plan, usage_percent | Billing page visit |
| `plan_upgraded` | from_plan, to_plan, trigger | Plan change |
| `plan_downgraded` | from_plan, to_plan, reason | Plan change |
| `team_member_invited` | role, count | Team invite sent |
| `source_deleted` | source_type, images_count | Source removed (churn signal) |

### Lifecycle Events (HubSpot)

| Event | Properties | Trigger |
|-------|-----------|---------|
| `lifecycle_stage_changed` | from_stage, to_stage | Automated workflow |
| `email_opened` | email_name, sequence_name | HubSpot tracking |
| `email_clicked` | email_name, cta_text, link_url | HubSpot tracking |
| `meeting_booked` | meeting_type, rep | Calendar booking |

### Revenue Events (Stripe)

| Event | Properties | Trigger |
|-------|-----------|---------|
| `payment_succeeded` | amount, plan, payment_method | Stripe webhook |
| `payment_failed` | amount, failure_reason | Stripe webhook |
| `subscription_created` | plan, billing_cycle, trial | Stripe webhook |
| `subscription_cancelled` | plan, cancel_reason, tenure | Stripe webhook |
| `usage_milestone` | milestone (10K/100K/1M images), current_plan | Usage threshold |

---

## Event Naming Conventions

### Imgix Standard

```
object_action
```

- Lowercase with underscores
- Object first, then action: `source_connected`, `plan_upgraded`
- Be specific: `cta_hero_clicked` not `button_clicked`
- Include context in properties, not event name

### Property Naming

- `snake_case` for all properties
- Prefix with category when helpful: `utm_source`, `plan_type`
- Use consistent values: `source_type` always uses `s3`, `gcs`, `azure` (not mixed casing)
- Never include PII in event properties (no email addresses in PostHog events)

---

## Key Funnels to Build in PostHog

### 1. Visitor → Activated User

```
page_view (imgix.com) → signup_completed → source_connected → first_image_served → first_transform_applied
```

### 2. Free → Paid

```
signup_completed → activation (first_transform) → usage_milestone_10K → billing_page_viewed → plan_upgraded
```

### 3. Onboarding Completion

```
signup_completed → dashboard_login → source_connected → source_configured → first_image_served
```

### 4. Expansion Path

```
usage_milestone_100K → billing_page_viewed → plan_upgraded
```

---

## UTM Parameter Strategy for Imgix

### Standard Parameters

| Parameter | Convention | Examples |
|-----------|-----------|---------|
| `utm_source` | Platform name | `google`, `linkedin`, `newsletter`, `stackoverflow` |
| `utm_medium` | Channel type | `cpc`, `email`, `social`, `referral`, `organic` |
| `utm_campaign` | Campaign name | `image_optimization_guide`, `webp_launch`, `q2_retargeting` |
| `utm_content` | Variant/placement | `hero_cta`, `sidebar_banner`, `footer_link` |
| `utm_term` | Paid keyword | `image_cdn`, `image_optimization_api` |

### Imgix UTM Rules

- Always lowercase, underscores not hyphens
- Document all UTMs in a shared sheet (HubSpot or Google Sheets)
- Include UTMs on all external links: blog distribution, email CTAs, social posts, paid ads
- PostHog captures UTMs automatically on first pageview — use for cohort analysis

---

## PostHog Configuration

### Custom Properties to Set

| Property | Scope | Value |
|----------|-------|-------|
| `plan_type` | Person | free, starter, growth, enterprise |
| `signup_source` | Person | organic, paid, referral, direct |
| `activation_status` | Person | signed_up, source_connected, activated, power_user |
| `company_size` | Person | From signup or enrichment |
| `industry` | Person | From signup or enrichment |

### Cohorts to Create

| Cohort | Definition |
|--------|-----------|
| Activated users | `first_transform_applied` in last 90 days |
| At-risk accounts | API calls dropped 50%+ week-over-week |
| Power users | 10+ unique transforms used |
| Expansion candidates | Usage > 80% of plan limit |
| Stalled signups | Signed up > 7 days ago, no `source_connected` |

### Dashboards to Build

1. **PLG Funnel** — Visitor → signup → activation → paid (weekly)
2. **Feature Adoption** — Transform types used, SDK adoption, API endpoints
3. **Churn Signals** — Usage drops, billing page visits, source deletions
4. **Marketing Attribution** — Signups by source/medium/campaign
5. **Experiment Results** — Running experiments, concluded experiments, cumulative lift

---

## GA4 Configuration for imgix.com

### Custom Events (Webflow)

Add to Webflow custom code section:

```javascript
// Track CTA clicks
document.querySelectorAll('[data-track="cta"]').forEach(el => {
  el.addEventListener('click', () => {
    gtag('event', 'cta_clicked', {
      'button_text': el.textContent.trim(),
      'location': el.dataset.location || 'unknown',
      'page_path': window.location.pathname
    });
  });
});
```

### Conversions to Mark in GA4

- `signup_completed`
- `demo_requested`
- `pricing_page_viewed`
- `docs_clicked` (intent signal)

---

## Debugging and Validation

### PostHog

- Use PostHog toolbar (browser extension) for live event inspection
- Check Events tab for real-time event stream
- Verify person properties are set correctly
- Test feature flags with override URLs

### GA4

- GA4 DebugView for real-time monitoring
- GTM Preview Mode if using Tag Manager
- Check Realtime report for event confirmation

### Validation Checklist

- [ ] PostHog events firing on correct triggers
- [ ] Event properties populating with correct values
- [ ] No duplicate events (check for double-firing)
- [ ] UTM parameters captured on first touch
- [ ] PostHog person properties updating correctly
- [ ] GA4 conversions recording
- [ ] HubSpot lifecycle stages transitioning
- [ ] No PII in analytics properties
- [ ] Works on mobile and desktop

---

## Privacy and Compliance

- PostHog can be configured for cookieless tracking (first-party data)
- GA4 requires cookie consent for EU/UK visitors
- No PII in event properties (use internal user IDs, not emails)
- Respect DNT headers where applicable
- Data retention: Configure in PostHog and GA4 settings

---

## Metrics

| Metric | Where | Target |
|--------|-------|:------:|
| Tracking coverage | PostHog | 95%+ of key actions tracked |
| Data freshness | PostHog | Real-time |
| Event accuracy | All | Zero duplicate events |
| Attribution coverage | GA4 | UTMs on 90%+ of external links |

---

## Related Skills

- **Conversion/ab-test-setup** — PostHog experiments rely on this tracking
- **Conversion/page-cro** — CRO analysis uses analytics data
- **Conversion/onboarding-cro** — Activation funnel tracking
- **Lifecycle/churn-prevention** — Churn signal detection in PostHog
- **Lifecycle/expansion-upsell** — Usage threshold tracking
- **Discoverability/reporting** — SEO and content performance in GA4
- **imgix-brand-voice** (global) — Dashboard and report naming conventions
