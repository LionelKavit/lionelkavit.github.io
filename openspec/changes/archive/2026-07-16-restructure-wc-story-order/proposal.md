## Why

The page now carries a user success story, but its section order still follows the original
product-pitch arc: features (pool strategy, group stage, Ask the Analyst) come before the proof
(receipts) and the person (reflection). A success story reads product → proof → person → trust →
depth: say what the app is, show it working, grade the builder's own bracket in public, let him
reflect, explain why the numbers hold, then go deep on features. The current order buries the
strongest material mid-scroll.

## What Changes

- Reorder `project-wc-bracket-analyst.html` content sections to: **(1) what the app is** (bracket
  predictor intro), **(2) demo video** (split out of the intro section into its own beat directly
  after it), **(3) the receipts** (public grading of Kavit's bracket), **(4) personal reflection**,
  **(5) why you can trust it**, **(6) app features** (pool-winning strategy / upset watch, group
  stage, Ask the Analyst). Hero, scoreboard strip, impact bar, disclaimer, and CTA stay where they
  are.
- Preserve the divider rhythm and scroll-reveal behavior across the new order; move markup blocks
  intact (copy rewrites belong to sibling changes).
- Transitional stitching between reordered sections (one-line lead-ins where a seam reads abruptly)
  is owned by the `saturate-wc-success-narrative` change; this change is structure only.
- Supersedes placement prose in the active `add-wc-receipts` change docs (its delta wording is
  updated to be order-agnostic; receipts remain before the reflection in the new order).

## Capabilities

### New Capabilities
<!-- None. -->

### Modified Capabilities
- `project-showcase`: The "Bracket Analyst case-study page structure" requirement's mandated section
  order is rewritten to the storytelling order above.

## Impact

- File: `project-wc-bracket-analyst.html` (markup block moves only; no copy or CSS changes).
- Sibling coordination: `add-wc-receipts` delta placement phrase updated (done as part of this spec).
- Mobile: unaffected mechanically (same blocks, new order); verified at 375px/320px regardless.
