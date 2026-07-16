## Why

The Bracket Analyst impact bar currently shows four engineering metrics (`~60s`, `50,000`, `1,489`,
`287`). Engineering metrics say "this was built well"; a real-tournament result says "and it was
right." Now that the app's predictions have a verified World Cup record (all four semifinalists
called), the weakest of the four slots — `1,489` players/teams, a data-scale stat that duplicates the
"grounded data model" story told elsewhere on the page — should yield its slot to the
tournament-truth metric `4/4 semifinalists called`. Cheapest possible change, highest-visibility
placement, structure untouched.

## What Changes

- In `project-wc-bracket-analyst.html`, replace the third impact stat (`1,489` / "Players, 48 teams —
  one grounded data model") with a tournament-record stat: number `4/4`, label
  `Semifinalists called — World Cup 2026` (final copy tuned at implementation to match the two-line
  label rhythm of its neighbors).
- The other three stats, the bar's four-slot structure, and all styling (`--pitch-accent` background,
  Lora numerals, existing borders) are unchanged.
- Only a decided, verified result appears in the metric (semifinalists is already decided; if a
  stronger decided record exists by publish time, the strongest *decided* claim may be used instead —
  never a pending one).
- Mobile behavior is inherited: the bar's existing 2×2 mobile grid must still render the new label
  without clipping at 320–430px.

## Capabilities

### New Capabilities
<!-- None. -->

### Modified Capabilities
- `project-showcase`: Adds a requirement that the Bracket Analyst impact bar carries a verified
  tournament-truth metric in place of the data-scale stat. (Coexists with the existing page-structure
  requirement: the bar keeps four headline metrics; that requirement's examples are illustrative.)

## Impact

- File: `project-wc-bracket-analyst.html` only (one `.impact-stat` block's text; possibly a small
  mobile label-size check).
- No dependencies, no JavaScript, no layout change. Verified in the mobile preview at 375px/320px
  and desktop.
