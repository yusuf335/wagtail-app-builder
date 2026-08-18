# wagtail-app-builder

A drag-and-drop visual builder for Wagtail — build pages, headers, and footers with the same editor.

**Status:** early design phase. Not yet ready for production use.

## Problem statement

Wagtail's StreamField gives you structured, server-defined content blocks — but edits them through a form-based vertical list, and only for the content area of a page. There is no visual, canvas-style building experience: editors cannot drag widgets from a palette onto a live preview of the page. And there is no way to build the parts of the site *around* the content, like headers and footers.

wagtail-app-builder replaces StreamField's editing UI with a visual canvas — a widget palette on the left, a live preview on the right, and a settings inspector per element — and extends it to header and footer documents alongside pages. Storage stays in StreamField, so you keep everything Wagtail already gives you: revisions, drafts, moderation workflows, live preview, image renditions, and template rendering.

## Core concepts

- **Documents** — everything you build is a document with a kind: `page`, `header`, or `footer` (more kinds later). All kinds store the same recursive element tree (`id`, `type`, `settings`, `children`) and open in the same editor.
- **Widget registry** — widgets declared in Python with a settings schema, a Django template, and the document kinds they are allowed in (a nav-menu widget belongs in headers; a post-content widget does not). The editor UI is generated from the schema.
- **Regions and conditions** — your base template renders `{% render_region "header" %}`, and the header document whose display conditions match the current request is rendered there.
- **Kit (global styles)** — a special document holding site-wide colors, fonts, and defaults, so pages, headers, and footers look like one coherent site.

## Planned features

- **Drop-in StreamField widget** — swap the default block editor for the visual canvas via a telepath adapter; no changes to your page models' data
- **Header and footer documents** — build site parts with the same editor and render them by region with display conditions
- **Live canvas preview** — the editor renders your page through Wagtail's real preview endpoint in an iframe, so what you build is exactly what publishes
- **Wagtail image chooser integration** — image widgets use the native Wagtail image library and renditions
- **Revision-aware saving** — every builder save creates a normal Wagtail revision
- **Server-side rendering** — via recursive template tags; output is queryable structured data, never an HTML blob

## Roadmap

1. Widget registry, document model, render tags, and a minimal React editor for pages
2. Telepath widget replacing the StreamField editor, plus iframe live preview via Wagtail's preview endpoint
3. Header and footer documents, display conditions, region rendering, and Kit global styles
4. Responsive controls, per-document compiled CSS, template library

## Contributing

Contributions of all kinds are welcome — ideas, design feedback, bug reports, documentation, and code. See [CONTRIBUTING.md](CONTRIBUTING.md) and our [Code of Conduct](CODE_OF_CONDUCT.md).

## License

MIT
