## Why

The seven project case-study pages share one template (dark "pitch" hero, four-metric impact bar, multi-column content grids, horizontal AI-flow/pipeline rows, closing CTA) and each already has a `@media (max-width: 768px)` block. Those blocks are more complete than the homepage's, but they were never verified at true phone widths (~320–375px), and several residual desktop rules survive there: some impact bars and eval grids stay two-up and crowd, fixed-column rows (`.spec-row`, `.dec-row`, `.llm-node-row`, `.lb-row`) keep rigid pixel columns that can overflow, and horizontal pipelines (`.pipeline`, `.ai-flow`) may push the page wider than the viewport. The result is distortion and/or horizontal scrolling on phones.

This is a CSS-completeness fix, page by page, keeping the current static HTML/CSS — no framework or language change.

## What Changes

- Audit and fix mobile responsiveness for all seven project pages:
  - `project-fpl-advisor.html`
  - `project-wc-bracket-analyst.html`
  - `project-msa-data-agent_3.html`
  - `project-buyside-agent_3.html`
  - `project-wattbot_2.html`
  - `project-process-capability_2.html`
  - `project-epl-analysis_3_1.html`
- For each page, at 320–430px:
  - Eliminate horizontal overflow (contain hero background, pills, tables, and pipelines).
  - Collapse content grids to a single column; where a two-up grid (e.g. `.impact-inner`, `.eval-grid`) still crowds, add a finer breakpoint to go single-column.
  - Make fixed pixel-column rows (`.spec-row`, `.dec-row`, `.llm-node-row`, `.lb-row`, leaderboard rows) adapt (fluid columns, wrap, or horizontal scroll within their own container).
  - Ensure horizontal step flows (`.pipeline`, `.ai-flow`) stack or scroll within a contained region rather than widening the page.
  - Confirm hero titles, technology pills, impact numbers, captions, and the CTA remain legible and within the viewport.
- Preserve desktop layout (≥769px) and all existing content, images, and links.
- Verify every page in a live mobile browser preview and iterate until each distortion is gone.

## Capabilities

### New Capabilities
- `responsive-layout`: Adds the mobile responsiveness requirement for the project case-study pages (no horizontal overflow, single-column stacking, adaptive fixed-column rows and step flows). Shares the capability introduced by the homepage/journey change.

### Modified Capabilities
<!-- None. The project-showcase content/structure/link requirements are unchanged; only mobile-width presentation is added. -->

## Impact

- Affected files (embedded `<style>` blocks; minimal markup wrapping only if a row/pipeline needs a scroll container): the seven `project-*.html` pages listed above.
- No dependencies, build tooling, or JavaScript added. Shared design system preserved.
- Verification requires running the static site in a local mobile preview.
