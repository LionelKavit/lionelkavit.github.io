## Why

The hero, receipts, and reflection now tell the success story, but the remaining content sections
(bracket-predictor intro, demo beat, pool-winning strategy, group stage, Ask the Analyst, trust, CTA)
still read as a generic product pitch written before the run happened. A visitor moving through the
page feels the narrative drop out between the proof sections. Every section should read as a chapter
of one story — the engine Kavit built, proven with his own bracket — woven in where it's natural, not
bolted on.

## What Changes

- A copy pass over the content sections of `project-wc-bracket-analyst.html` to thread the success
  story through each, in the storytelling order established by `restructure-wc-story-order`:
  - **Intro / demo beat:** one connective line pointing forward to the graded bracket ("the same
    autofill that seeded my bracket below").
  - **Pool-winning strategy / upset watch:** tie the boldness engine to the run (bold branches that
    survived shifted paths), consistent with the receipts.
  - **Group stage:** connect the third-place/group predictions to how the real groups resolved, only
    as far as decided facts support.
  - **Ask the Analyst:** frame the chat as the same grounded analyst that backed the run's calls.
  - **Trust section:** transitional framing only (its substantive rewrite is
    `strengthen-wc-trust-mechanics`).
  - **CTA:** invite the visitor to run their own bracket the way Kavit ran his.
  - **Seam lead-ins** where the reorder created abrupt transitions (e.g. reflection → trust).
- Honesty guards carried over verbatim from the reframe change: decided results only; champion pick
  in play until Sunday; no lock claims; no pool-win claim; no self-applied "expert" label; nothing
  that contradicts the receipts (misses included).

## Capabilities

### New Capabilities
<!-- None. -->

### Modified Capabilities
- `project-showcase`: Adds a requirement that the success-story narrative is threaded through all
  content sections coherently and truthfully.

## Impact

- File: `project-wc-bracket-analyst.html`, text-only copy edits inside existing blocks.
- Depends on `restructure-wc-story-order` (implement after it, so lead-ins match the final order).
- Mobile: text-only; verified at 375px/320px for type scale and overflow regardless.
