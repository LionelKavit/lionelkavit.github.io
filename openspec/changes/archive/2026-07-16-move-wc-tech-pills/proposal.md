## Why

The hero's technology pills (Next.js, TypeScript, Claude, Monte Carlo, Vitest, zod) are stack
reference for technical readers, not part of the success-story argument the hero now makes. Kavit
wants them moved to the bottom of the page — between the Ask the Analyst section and the
unofficial-project disclaimer — where they read as a "built with" footnote rather than an opening
claim. They are also the last implementation jargon left above the fold.

## What Changes

- Remove the `.hero-pills` block from the hero of `project-wc-bracket-analyst.html`.
- Add a small "Built with" beat between Ask the Analyst and the disclaimer carrying the same pills,
  with a light-surface pill variant (the current pill styling is white-on-dark and would be illegible
  on the cream content background).
- Mobile behavior preserved: pills wrap centered at phone widths as before.

## Capabilities

### New Capabilities
<!-- None. -->

### Modified Capabilities
- `project-showcase`: The page-structure requirement's hero clause drops the technology pills; the
  pills become a "built with" element between the final feature section and the disclaimer.

## Impact

- File: `project-wc-bracket-analyst.html` (markup move + one pill style variant). Verified at
  375px/320px and desktop.
