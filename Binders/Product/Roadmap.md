---
last_synced: 2026-07-14
source: Notes/Onboarding/Product/Roadmap.md
---
# Roadmap

> ⚠️ This page was generated from incomplete source material. Review and expand the sections that are missing or thin.

## Now

Polishing the core experience and deepening programmatic SEO and generated fields. Specifically: ready-made templates for generated fields so users can add a word count field, a reading time field, or a content quality linter in one click — without writing Liquid template syntax themselves. Internally these all use Liquid templates; the templates make them accessible without setup work.

## Next

The multi-platform expansion (S3/R2 storage integrations for Webstudio, Astro, Next.js, Nuxt, SvelteKit) was the most recent major chapter — now wrapping up or recently completed. The near-term focus is on quality and depth of the existing feature set rather than new platform connections.

## Later

An opinionated, AI-powered platform covering the full content operations lifecycle — from content brief or idea through to published article, tweet, post, or video. See [[Product/Vision]] for the full picture.

## Not doing

**Public API** — by design. Content is stored in users' own S3/R2 storage, which means users host and own their content directly. Serving content through an Inbind-owned API would add cost and a dependency that contradicts this architecture. The S3/R2 approach keeps serving costs on the user's own infrastructure.

## Priority in 90 days

Not documented. Likely: generated field templates (word count, content linter) based on the current focus.

## If we had more resources

Not documented.
