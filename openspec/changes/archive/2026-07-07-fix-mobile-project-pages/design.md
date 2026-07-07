## Context

The seven project pages are built from one template and share class names (`.hero`, `.hero-bg`, `.hero-inner`, `.hero-pills`, `.impact-bar`, `.impact-inner`, `.impact-stat`, `.content`, `.cta`, plus page-specific content grids). Each already resets padding, collapses most grids, and stacks the impact bar and CTA inside `@media (max-width: 768px)`. Verified residual risks at ≤375px:

- **Two-up grids that crowd**: `.impact-inner { grid-template-columns: 1fr 1fr }` on `project-fpl-advisor.html` and `project-epl-analysis_3_1.html`; `.eval-grid { grid-template-columns: 1fr 1fr }` on `project-wattbot_2.html`.
- **Fixed pixel-column rows**: `.spec-row { 100px 1fr }` (buyside), `.dec-row { 8rem 1fr }` (fpl), `.llm-node-row { 7rem 1fr }` (epl), leaderboard `.lb-header/.lb-row { 2rem 1fr 4rem 4rem }` (epl).
- **Horizontal step flows**: `.ai-flow` (fpl, epl) is rotated/stacked, but `.pipeline { justify-content: flex-start }` (msa) stays horizontal and may overflow.
- **Hero**: dark hero background, long titles with `<br>`, and technology pills need overflow/wrap checks at 320px.

Because the pages are near-duplicates, most fixes are the same rule applied per file, but each page's content grids differ, so each must be verified individually.

## Goals / Non-Goals

**Goals:**
- All seven pages: no horizontal overflow and no distortion at 320–430px.
- Content grids single-column (or comfortably readable) on phones; fixed-column rows adapt; horizontal flows stack or scroll within a contained region.
- Desktop layout (≥769px) unchanged; all content, images, captions, and links preserved.

**Non-Goals:**
- No framework, TypeScript, build step, or added JavaScript.
- No content/copy edits, no redesign, no CSS deduplication across files.
- Homepage, journey, and blog pages are out of scope (sibling changes).

## Decisions

- **Fix per page inside the existing `@media (max-width: 768px)` block, adding a finer breakpoint (~480px or ~380px) only where a two-up grid or fixed row still crowds.** Rationale: consistent with the site's pattern and low regression risk. Alternative — refactor all seven into a shared responsive stylesheet — rejected here to keep this change scoped to correctness (dedup is a separate future effort).
- **Fixed pixel-column rows → fluid or scrollable.** Prefer converting rigid pixel columns to `minmax`/`fr` or stacking label-over-value; where a row is genuinely tabular (leaderboard), wrap it in an `overflow-x: auto` container so the row scrolls inside itself instead of widening the page. Rationale: preserves the data layout without breaking the page.
- **Horizontal step flows → stack or contain.** Match the established `.ai-flow` treatment (stack vertically with a rotated connector) for `.pipeline`; if stacking is awkward, wrap in `overflow-x: auto`. Rationale: reuse the pattern already present in the codebase.
- **Verify each page individually in a real mobile viewport** (375×812 and a 320px pass) rather than assuming the shared template behaves identically — content grids differ per page.
- **Batch identical fixes but confirm separately.** Apply the same rule pattern across pages that share a class, but screenshot/inspect each page to catch page-specific content that overflows.

## Risks / Trade-offs

- **Seven near-duplicate pages invite copy-paste mistakes** → verify each page in preview, not just the first; keep a per-page checklist in tasks.
- **A leaderboard/table forced to scroll horizontally is less elegant than a reflow** → acceptable for dense tabular data; the page itself must not scroll, only the contained table.
- **Wrapping a row/pipeline may need a small markup addition (a scroll container)** → keep markup changes minimal and confirm desktop is visually unchanged.
- **Desktop regression** → all new rules stay within `max-width` media queries; verify one representative page at desktop width after changes.
