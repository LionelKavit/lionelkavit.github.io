## Why

The "Why you can trust it" section explains the pipeline (FIFA JSON → Elo engine → grounded Analyst)
but never concretely answers the reader's real question: *how does it actually decide who wins a
matchup, and why should I trust that over the pundit narrative?* Kavit flagged the copy as weak and
proposed explaining it as goal-count prediction — but the repository README documents the engine as
**Elo-strength Monte Carlo over win probabilities, with no goal modeling**, and pool size / risk
appetite calibrating **pick boldness (differentiation vs the chalk), not goal counts**. The rewrite
must therefore get its strength from the true mechanics — and the true mechanics happen to be the
strongest version of Kavit's upset-watch thesis: Elo is a measure of **long-run consistency**, while
pundit narratives chase **short-term form**. France and England carried the form; Spain and Argentina
carried the consistency — and consistency is literally what the engine scores.

## What Changes

- Rewrite the trust section's narrative copy (heading and paragraphs; the pipeline flow diagram and
  guardrail cards stay) in `project-wc-bracket-analyst.html` so it:
  - Explains match decision mechanics concretely and truthfully: each matchup's outcome is drawn from
    the two teams' Elo-derived win probability, and the engine plays the whole tournament out 50,000
    times to turn those per-match odds into standings, knockout odds, and pool verdicts.
  - Frames the form-vs-consistency thesis: short-term form is loud and recent; Elo encodes years of
    results — the long-term trend — which is why the model kept faith with Spain and Argentina while
    the form narrative favored France and England (decided facts, receipts-backed).
  - States the boldness calibration correctly: pool size and risk appetite decide *which* underdogs
    are worth backing (differentiation payoff), not how matches are simulated.
  - Explicitly does NOT claim goal-count prediction or per-stat outputs (e.g. goals after minute 75)
    unless the app documents such a capability — the section's own guardrail ("never makes up a
    number") applies to the page describing it.
- Coordination: the section's position (after the reflection) and its transitional lead-in come from
  the restructure and saturation changes.

## Capabilities

### New Capabilities
<!-- None. -->

### Modified Capabilities
- `project-showcase`: Adds a requirement pinning what the trust section must explain (true decision
  mechanics, form-vs-consistency framing, correct role of risk/pool calibration) and what it must not
  claim.

## Impact

- File: `project-wc-bracket-analyst.html`, one section's copy; flow diagram and guardrail cards
  untouched structurally.
- Verified against the repository README at implementation; mobile text-only verification at
  375px/320px.
