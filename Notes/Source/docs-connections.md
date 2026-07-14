# Inbind Docs — Connections
Source: https://docs.inbind.app/ (multiple pages)
Fetched: 2026-07-13

---

## Managing Connections Overview

Connections let you publish Inbind content to external destinations. A Connection stores the credentials and configuration needed to publish to a destination. Once created, you can link one or more collections to it and choose which fields to publish.

### Connection Types

**Webflow**
- Connects directly to the Webflow CMS API
- Bidirectional sync: edits in Inbind push to Webflow; edits in Webflow sync back to Inbind
- Requires: Webflow site on CMS plan or higher

**Storage-Based (Webstudio, Astro, Next.js, Nuxt, SvelteKit)**
- Publishes content as JSON files to S3-compatible object storage
- Your website/app fetches those JSON files to display content
- Requires: S3-compatible storage credentials (Amazon S3, Cloudflare R2, etc.)
- JSON format is the same for all frameworks; framework options in Inbind provide tailored setup instructions

### Content URL structure (storage-based)
- Index URL: `{base-url}/content/{organization-id}/{collection-slug}/_index.json`
- Item URL: `{base-url}/content/{organization-id}/{collection-slug}/{item-slug}.json`

### Field Selection when connecting a collection
- **Published fields**: included in the full item data (used on detail pages)
- **Index fields** (storage-based only): included in the collection index file (used on listing pages, kept lightweight)
- `name` and `slug` fields are always required and cannot be deselected

---

## Connect to Webflow

### Prerequisites
- Webflow site on a CMS plan or higher

### API Token permissions required
| Resource | Access level | Reason |
|---|---|---|
| Assets | Read & Write | Retrieve, update, and create images in asset manager |
| CMS | Read & Write | Retrieve, update, and create collection items; retrieve collection info |
| Sites | Read & Write | Retrieve site info, create webhooks |

### Setup
1. In Webflow dashboard → site settings → Apps & integrations → API access → Generate API token
2. In Inbind → Connections → + → Select Webflow → Paste API token → Create Connection
3. Select connection → + Connect Collection → choose collection → select fields → Connect Collection

### Sync behavior
- Inbind → Webflow: changes pushed automatically on create/edit/publish
- Webflow → Inbind: changes synced automatically when CMS item created/updated/deleted in Webflow

---

## Connect to Webstudio

### Prerequisites
- Paid plan to hosted Webstudio (or self-hosted with CMS capabilities)
- S3-compatible object storage (Amazon S3 or Cloudflare R2)

### Setup in Inbind
1. Connections → + → Select Webstudio → Provide S3/R2 credentials → Create Connection
2. + Connect Collection → select published fields + index fields → Connect Collection
3. Check Usage Instructions tab for content URLs

### Setup in Webstudio
**Listing page:**
- Add Resource variable on Body element with index URL (GET)
- Bind Collection component Data property to `resource.data.items`
- Bind child components (link href to slug, heading to title, etc.)

**Detail page:**
- Create page with dynamic path `/blog/:slug`
- Add Resource variable using `system.params.slug` to build item URL
- Bind components to Resource data fields

**404 handling:**
- Set Status Code expression: `!postData.title ? 404 : 200`
- Show/hide content sections based on whether data exists

---

## Connect to Astro

### Prerequisites
- Existing Astro site
- S3-compatible object storage

### Listing page example (Astro)
```astro
const response = await fetch('YOUR_INDEX_URL');
const data = await response.json();
const posts = data.items;
```

### Detail pages (pre-render at build time)
```astro
export async function getStaticPaths() {
  const response = await fetch('YOUR_INDEX_URL');
  const data = await response.json();
  return data.items.map((post) => ({ params: { slug: post.slug } }));
}
```

---

## Connect to Next.js

### Prerequisites
- Existing Next.js site
- S3-compatible object storage

### Listing page (App Router, Server Component)
```jsx
const response = await fetch('YOUR_INDEX_URL');
const data = await response.json();
const posts = data.items;
```

### Detail pages (generateStaticParams)
```jsx
export async function generateStaticParams() {
  const response = await fetch('YOUR_INDEX_URL');
  const data = await response.json();
  return data.items.map((post) => ({ slug: post.slug }));
}
```

---

## Connect to Nuxt

### Prerequisites
- Existing Nuxt site
- S3-compatible object storage

### Listing page
```vue
const { data } = await useFetch('YOUR_INDEX_URL');
const posts = computed(() => data.value?.items ?? []);
```

### Detail pages
```vue
const { data: post } = await useFetch(() => `YOUR_BASE_URL/.../posts/${slug}.json`);
```

---

## Connect to SvelteKit

### Prerequisites
- Existing SvelteKit site
- S3-compatible object storage

### Listing page
Uses `+page.server.js` loader with `fetch('YOUR_INDEX_URL')`.

### Detail pages
Uses `+page.server.js` loader with route params slug to build item URL.

---

## Object Storages Supported
- Amazon S3
- Cloudflare R2
