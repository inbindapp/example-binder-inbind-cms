---
status: partial
---
# Features

> Answer the questions below to document what your product can do.

## What are the main features?

1. **Collection table view** — All collection items in one sortable table. Spot missing fields, check readiness, stop clicking into items one by one.
2. **SEO-focused editor** — Rich text editor with metadata, structure, and discoverability treated as core features, not afterthoughts.
3. **Generated fields** — Automatically populate field values using Liquid-style templates based on other fields. Used for programmatic SEO and repetitive field composition (SEO titles, descriptions, reading time, word count, JSON-LD, UTM links, etc.).
4. **Content health checks** — Flag missing or incomplete fields before publishing. Configurable SEO health score (0–100) based on title, headings, word count, images, links, freshness.
5. **Internal fields** — Add status, owner, and notes fields visible only in Inbind. Track workflow without cluttering published content.
6. **Blocks** — Insert the content of another item's rich text field by reference. Updates automatically everywhere when the source changes. Used for reusable CTAs, disclaimers, author bios, boilerplate.
7. **Tables in rich text** — Add tables to long-form content. Rendered as standard HTML, styled by existing site CSS.
8. **Direct publishing** — Push content live without opening Webflow Designer, touching code, or waiting on a developer.
9. **Bidirectional Webflow sync** — Edits in Inbind push to Webflow; edits in Webflow sync back to Inbind automatically.
10. **Multi-platform connections** — Webflow (CMS API), Webstudio, Astro, Next.js, Nuxt, SvelteKit (via JSON files on S3-compatible storage).
11. **Unlimited collections** — No collection limits based on plan tier.

## Which features are most important to your users? Why?

- **Table view** — gives marketers visibility across all items at once; they can spot gaps without opening each item
- **SEO-focused editor** — SEO fields are front and center, not buried; users actually fill them in
- **Generated fields / programmatic SEO** — huge time saver for teams managing many collection items or building pSEO pages
- **Publish without a developer** — removes the most common bottleneck for content teams

## Which features are unique to you (not found in competitors)?

- Generated fields with Liquid-style templates for programmatic SEO (source → destination collection population)
- Content health score as a generated field (configurable SEO rubric)
- Blocks (reusable rich text content by reference, auto-updating)
- Internal-only fields that don't sync to Webflow
- Unlimited collections regardless of pricing tier

## What features are on the roadmap?

Not publicly documented at time of fetch. Website mentions "More of what's to come you'll find on our website."
Pricing page lists upcoming features: roles, approvals, clear ownership, and AEO-ready content workflows.

## What features have you intentionally left out, and why?

Inbind does not replace Webflow Designer — it's a content layer, not a site builder. Users still design in Webflow; Inbind handles the content editing and publishing side only.
