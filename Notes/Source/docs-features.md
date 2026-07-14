# Inbind Docs — Features
Source: https://docs.inbind.app/ (multiple pages)
Fetched: 2026-07-13

---

## Managing Content

(Page: /managing-content.html — content not fully captured in scrape)

---

## Creating & Editing Content

(Page: /creating-content.html — content not fully captured in scrape)

---

## Blocks

Blocks let you insert the content of another item's rich text field directly into a rich text field. When the referenced item's value changes, the block automatically updates everywhere it's used, so there's no need to find and update every occurrence manually.

Common use cases: reusable CTAs, legal disclaimers, author bios, shared boilerplate text, and any other content that appears in multiple items.

### Inserting a block
- Place your cursor in the rich text field
- Type `/` to open the command menu
- Select Block, then choose a collection, item, and field
- Block is inserted with a live preview

### Automatic updates
When you update the referenced item's field value, all blocks that reference it are automatically re-rendered and published to connected platforms.

---

## Publishing Content

### Publishing Statuses
- **Draft** — created or modified but not yet published
- **Published** — live on your connected platform
- **Archived** — removed from publication

### Webflow Status Mapping
| Webflow status | Inbind status |
|---|---|
| Draft | Draft |
| Changes in draft | Draft |
| Queued to publish | Draft |
| Published | Published |
| Archived | Archived |

Deleting items in Inbind will also delete the item in Webflow.

### Publishing Limitation
If you're creating items in a collection that was created after the latest site publishing, you must first publish the site in Webflow before publishing the items in this collection.

---

## Edit Fields

Two types of fields in Inbind:
1. **Regular fields**
2. **Generated fields**

### Supported field types:
| Field Type | Description |
|---|---|
| Text | Plain text content without formatting |
| Rich text | Formatted text with headings, lists, links, images, and custom code |
| Number | Numeric values for quantities, prices, or calculations |
| Boolean | True/false values for toggles and checkboxes |
| Datetime | Date and time values for scheduling and timestamps |
| Url | Web addresses and links |
| Image | Single image uploads |
| Multi image | Multiple image uploads |
| File | Document and file uploads |
| Video | Video file uploads |
| Color | Color values for styling and design |
| Choice | Single selection from predefined options |
| Reference | Link to a single item from another collection |
| Multi reference | Link to multiple items from another collection |

New fields can be added and existing fields deleted. New fields and their values are by default only visible within Inbind and do not get synced to connected platforms (you choose which fields to sync per collection).

---

## Generated Fields

A generated field uses a template to populate its value from other fields in the same collection or a related collection.

### Key concepts
- Templates use Liquid-style syntax: `{{field-name}}`, `{{related-collection.field}}`
- Can reference fields from related collections via reference fields (e.g., `{{author.name}}`)
- Can be used for programmatic SEO: a source collection populates an entire destination collection

### Generated field types supported:
- Text
- Rich Text
- Color
- Number
- URL

### Rendering
Generated fields are re-rendered automatically when you create or update a field's template. Can also be triggered manually: click ⋮ above content table → "Render generated fields".

### Example use cases (with templates):
- **Word count**: splits body text and counts words
- **Reading time**: divides word count by 225 words/minute, rounds up, appends "min read"
- **JSON-LD Schema**: BlogPosting structured data template
- **Shorten text**: `{{ body | strip_html | truncatewords: 30, "..." }}`
- **UTM links**: `{{ post-url }}?utm_source=webflow&utm_medium=blog&utm_campaign={{ slug }}`
- **Content health score**: calculates 0–100 SEO health score checking title, headings, word count, images, links, freshness

### Programmatic SEO via source collections
- Define a source collection in Inbind
- Inbind auto-generates items in a destination collection from the source
- Source and destination always have equal number of items
- When a new item is added to the source, a corresponding item is created in the destination with generated field values
