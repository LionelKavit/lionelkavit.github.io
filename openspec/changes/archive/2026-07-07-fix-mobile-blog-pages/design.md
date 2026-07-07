## Context

The four blog pages share a template with classes like `.blog-hero`, `.blog-content-wrap` (article + `.blog-sidebar`), `.blog-photo-gallery` / `.photo-mosaic`, `.section-divider`, and `.blog-footer-nav`. Each `@media (max-width: 768px)` block already stacks `.blog-content-wrap` to one column, makes the sidebar `position: static`, and stacks the footer nav. Verified residual risks at ≤375px:

- **`blog-atthai.html`**: `.days-grid { grid-template-columns: repeat(4, 1fr) }` is kept on mobile — four columns are far too tight on a phone.
- **`blog-kalsubai.html`**: `.photo-mosaic { grid-template-columns: 1fr 1fr }` with a `.span-col` spanning 2, plus a `50vh` hero image with absolutely-positioned overlay text and an altitude badge — check overlap/overflow at 320px.
- **All blogs**: unlike project pages, the top `.nav-links` stay visible on mobile (only `gap` is reduced), so at 320px they can wrap awkwardly or overflow.
- **Galleries and wide media** (`.blog-photo-gallery`, gallery image heights, `.blog-hero-image` widths): confirm images use `max-width: 100%` and don't push the page wide.

Pages are near-duplicates, so most fixes repeat, but hero/gallery treatments differ per page and must be verified individually.

## Goals / Non-Goals

**Goals:**
- All four pages: no horizontal overflow and no distortion at 320–430px.
- Over-dense grids (notably `.days-grid`) collapse to a legible column count; galleries/mosaics and hero overlays stay within the viewport; nav links adapt gracefully.
- Desktop layout (≥769px) unchanged; all content, images, and links preserved.

**Non-Goals:**
- No framework, TypeScript, build step, or added JavaScript.
- No content/copy edits, no redesign, no CSS deduplication across files.
- Homepage, journey, and project pages are out of scope (sibling changes).

## Decisions

- **Fix per page inside the existing `@media (max-width: 768px)` block, adding a finer breakpoint (~480px/~380px) where a grid is still too dense.** Rationale: consistent with the site's pattern, low regression risk.
- **`.days-grid` → fewer columns on phones** (e.g. two, or the pattern that reads best) rather than four. Rationale: four fixed columns are unreadable at 320–375px.
- **Nav links → wrap or adapt, no JS.** Prefer allowing the links to wrap (`flex-wrap`) or reducing them to a compact row; a CSS-only disclosure only if wrapping looks poor. Rationale: honor the "no added JS" goal; blogs currently show the links, so keep them reachable.
- **Images/galleries → fluid and contained.** Ensure gallery and hero images use `max-width: 100%` / fluid heights and that any absolutely-positioned hero overlay/badge stays inside the image at small widths. Rationale: prevent the most common overflow source.
- **Verify each page individually in a real mobile viewport** (375×812 plus a 320px pass); hero and gallery treatments differ per page.

## Risks / Trade-offs

- **Near-duplicate pages invite copy-paste errors** → verify each page in preview, keep a per-page checklist in tasks.
- **Reducing `.days-grid` columns changes the visual rhythm of that section** → acceptable; legibility on phones outweighs the denser desktop look, and desktop is untouched.
- **Hero overlay text over a shorter mobile hero image may crowd** → adjust overlay position/size at phone widths; verify no clipping.
- **Desktop regression** → all new rules stay within `max-width` media queries; verify one representative page at desktop width after changes.
