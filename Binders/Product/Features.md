---
last_synced: 2026-07-14
source: Notes/Onboarding/Product/Features.md
---
# Features

> ⚠️ This page was generated from incomplete source material. Review and expand the sections that are missing or thin.

## Features

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

## Most important features

- **Table view** — gives marketers visibility across all items at once; they can spot gaps without opening each item
- **SEO-focused editor** — SEO fields are front and center, not buried; users actually fill them in
- **Generated fields / programmatic SEO** — huge time saver for teams managing many collection items or building pSEO pages
- **Publish without a developer** — removes the most common bottleneck for content teams

## Unique features

- Generated fields with Liquid-style templates for programmatic SEO (source → destination collection population)
- Content health score as a generated field (configurable SEO rubric)
- Blocks (reusable rich text content by reference, auto-updating)
- Internal-only fields that don't sync to Webflow
- Unlimited collections regardless of pricing tier

## Intentional omissions

Inbind does not replace Webflow Designer — it's a content layer, not a site builder. Users still design in Webflow; Inbind handles the content editing and publishing side only.

No public API — by design. Content is stored in users' own S3/R2 storage, so users host and own their content directly. See [[Product/Roadmap]] for more context.
