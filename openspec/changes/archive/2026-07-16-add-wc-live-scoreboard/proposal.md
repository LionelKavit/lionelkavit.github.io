## Why

The Bracket Analyst's pre-tournament predictions have performed remarkably at the real World Cup 2026:
all four semifinalists called, Spain-over-France called as a result, all four quarterfinal advancement
calls correct, and the final pick (Argentina) still in play as of July 15, 2026. The case-study page
currently says nothing about this — the single most persuasive piece of evidence for the app's whole
"grounded, not guessing" thesis is missing while the tournament is still live. A slim, hand-updated
scoreboard strip directly under the hero puts the record in front of every visitor at the moment it's
most compelling.

## What Changes

- Add a **live scoreboard strip** to `project-wc-bracket-analyst.html`, between the hero and the
  impact bar: a `LIVE · WORLD CUP 2026` label, 3–4 short result pills (e.g. `4/4 semifinalists ✓`,
  `Spain over France ✓`, `Final pick: Argentina — in play`), and an "as of <date>" stamp.
- Pills carry one of three visual states: **correct (✓)**, **missed (✗)**, **in play** — so the strip
  is updated by editing pill text/state after each remaining match, not by restructuring.
- After the final, the `LIVE` label flips to a permanent-record label (e.g. `FINAL RECORD · WORLD CUP
  2026`) with the same structure.
- Styling reuses the page's existing design system (pitch palette, DM Sans labels, pill shapes) —
  no new fonts or colors.
- Fully responsive: pills wrap/stack cleanly and stay centered at phone widths, honoring the site's
  mobile-aesthetics pillars (no overflow at 320–430px, mobile-scale type, cohesive grouping).
- Only truthful, already-decided results are stated as ✓/✗; undecided picks are explicitly marked
  "in play". No claim of pre-tournament lock is made in this strip (provenance is handled by the
  receipts change).

## Capabilities

### New Capabilities
<!-- None. -->

### Modified Capabilities
- `project-showcase`: Adds a requirement for the live tournament scoreboard strip on the Bracket
  Analyst page (placement, content states, update mechanism, mobile behavior).

## Impact

- File: `project-wc-bracket-analyst.html` only (markup + embedded CSS; mobile rules inside its
  existing `@media (max-width: 768px)` block).
- No dependencies or JavaScript; the strip is static and hand-updated (~2 more edits before the
  tournament ends). Verified in the mobile preview at 375px/320px and desktop.
