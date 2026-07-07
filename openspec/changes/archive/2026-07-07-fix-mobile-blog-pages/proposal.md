## Why

The four blog/essay pages share one template (blog hero, a two-column article-plus-sidebar `.blog-content-wrap`, photo galleries/mosaics, and a footer nav) and each already has a reasonably complete `@media (max-width: 768px)` block that stacks the content column and sidebar. But the blocks were not verified at true phone widths (~320–375px) and a few residual desktop rules survive: `blog-atthai.html` keeps `.days-grid { grid-template-columns: repeat(4, 1fr) }` (four columns crammed on a phone), galleries/mosaics and hero-overlay elements need overflow checks, and — unlike the project pages — the blog nav keeps its links visible, so on a narrow screen they can wrap or overflow. The net effect is cramped grids and possible horizontal scrolling on phones.

This is a CSS-completeness fix, page by page, keeping the current static HTML/CSS — no framework or language change.

## What Changes

- Audit and fix mobile responsiveness for the four blog pages:
  - `blog-kalsubai.html`
  - `blog-atthai.html`
  - `blog-drama-club.html`
  - `blog-comics-for-change.html`
- For each page, at 320–430px:
  - Eliminate horizontal overflow (contain hero images/overlays, galleries, mosaics, and wide media).
  - Collapse over-dense grids to a legible column count — in particular `.days-grid` on `blog-atthai.html` (from four columns to a comfortable count).
  - Ensure the two-column content/sidebar layout stacks cleanly (already partly handled) and that pull quotes, images, and captions stay within the viewport.
  - Ensure the top nav links wrap or adapt gracefully at narrow widths rather than overflowing.
  - Confirm the blog hero (image, overlay text, badges, meta) renders without clipping or overlap.
- Preserve desktop layout (≥769px) and all existing content, images, and links.
- Verify every page in a live mobile browser preview and iterate until each distortion is gone.

## Capabilities

### New Capabilities
- `responsive-layout`: Adds the mobile responsiveness requirement for the blog/essay pages (no horizontal overflow, legible grid collapse, adaptive nav and galleries). Shares the capability introduced by the homepage/journey change.

### Modified Capabilities
<!-- None. Content/structure of the essays is unchanged; only mobile-width presentation is added. -->

## Impact

- Affected files (embedded `<style>` blocks; minimal markup wrapping only if a gallery/media element needs containment): the four `blog-*.html` pages listed above.
- No dependencies, build tooling, or JavaScript added. Shared design system preserved.
- Verification requires running the static site in a local mobile preview.
