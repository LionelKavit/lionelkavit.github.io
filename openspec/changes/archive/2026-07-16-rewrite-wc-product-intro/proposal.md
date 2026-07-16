## Why

The bracket-predictor intro ("A complete World Cup bracket, in one sitting…") is the page's
what-is-this moment, and it currently front-loads mechanics — group-stage survival, "8 best
third-placed teams drawn from across the 12 groups", seeding a Round of 32 — before the reader knows
what the product does for them. It reads like a rules explainer, not a product intro. The first
section a visitor reads after the impact bar should land the outcome in one breath (complete,
odds-backed, pool-ready bracket in about a minute), then earn the wow with the hard parts the engine
handles invisibly.

## What Changes

- Rewrite the bracket-predictor intro section copy (label, heading, and both paragraphs may change)
  in `project-wc-bracket-analyst.html` so that:
  - The first sentence tells a stranger exactly what the app produces (a complete, editable World Cup
    bracket with real odds behind every pick, ready for their pool, in about a minute).
  - The 48-team complexity (12 groups, 8 best third-placed teams) appears as *what the engine handles
    for you* — supporting wow, not opening homework.
  - The interaction loop reads in order: autofill (calibrated to pool size and risk appetite) → edit
    with real head-to-head odds and flagged upsets → lock → export CSV into the pool.
  - One idea per sentence; no clause pile-ups; the ~60s impact stat and the demo beat directly below
    are set up, not repeated.
- Include the one story-connective line owned by `saturate-wc-success-narrative` (coordination, not
  duplication).

## Capabilities

### New Capabilities
<!-- None. -->

### Modified Capabilities
- `project-showcase`: Adds a requirement pinning what the product-intro section must communicate and
  the clarity/wow bar it must meet.

## Impact

- File: `project-wc-bracket-analyst.html`, one section's copy only; no structure or CSS changes.
- Mobile: text-only; verified at 375px/320px for wrap and overflow.
