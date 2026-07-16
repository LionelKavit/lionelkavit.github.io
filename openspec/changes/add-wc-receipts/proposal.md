## Why

The scoreboard strip (sibling change `add-wc-live-scoreboard`) makes the headline claim; this change
adds the proof layer. A compact predicted-vs-actual table — every pick by round, ✓/✗ per result,
with the honest annotations (three of the four Round-of-32 misses went to penalty shootouts, i.e.
coin flips) — turns a brag into evidence. Showing the misses is deliberate: a 12/16 R32 with
annotated shootout losses reads as a real, rigorous record; a curated highlights reel does not. The
section also carries the provenance note (how a visitor can verify the picks predate the tournament)
and links to the live app.

## What Changes

- Add a **"Receipts" body section** to `project-wc-bracket-analyst.html`, placed after the
  "Why you can trust it" section and before the personal reflection (it is the empirical answer to
  "is it any good?").
- Content: a compact predicted-vs-actual table grouped by round (Round of 32 → Final), one row per
  pick: matchup, the bracket's pick, the real result, and a ✓/✗ mark. Misses that were decided by
  penalty shootouts carry a "lost on pens" annotation. Undecided matches show as "in play", never ✓/✗.
- A short intro paragraph states the record plainly (including the misses) and a **provenance note**
  attributes the bracket honestly: it is Kavit's bracket, built with the app (model autofill plus
  hand-tweaked picks). No verifiable pre-tournament lock evidence exists, so the note makes **no
  locked-before-kickoff claim**, and no pick is altered or reframed after the fact — every displayed
  pick matches the bracket export verbatim.
- The section links to the live app (`https://fifa-wc-bracket.vercel.app/`).
- Styling reuses the page's design system (`.label` section headers, `--border` hairlines,
  `--warm-white` panels, DM Mono for marks/numbers where the page already uses it).
- Fully responsive: rows reflow (or scroll within their own container) at phone widths with no page
  overflow, per the site's responsive-layout and mobile-aesthetics standards.

## Capabilities

### New Capabilities
<!-- None. -->

### Modified Capabilities
- `project-showcase`: Adds a requirement for the prediction-receipts section on the Bracket Analyst
  page (structure, honesty rules, provenance note, live-app link, mobile behavior).

## Impact

- File: `project-wc-bracket-analyst.html` only (markup + embedded CSS; mobile rules in its existing
  `@media (max-width: 768px)` block).
- Data inputs: resolved — results are user-verified against the live feed (full scorecard in
  design.md), and attribution/provenance wording is settled (hand-tweaked bracket, no lock claim).
- No dependencies or JavaScript. Verified in the mobile preview at 375px/320px and desktop.
