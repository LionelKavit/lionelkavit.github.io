## Why

The receipts table currently renders hits in green and misses in a muted green-grey — a deliberately
soft treatment from the original design. Kavit wants the table to read at a glance like a graded
scorecard: outcome color-coding with green for correct calls, red for wrong ones, and black for
what's still undecided. This also resolves an ambiguity the muted treatment leaves open: rows where
the predicted path broke but the picked team still advanced (e.g. England over Brazil, won against
Norway) should unambiguously read as *correct* (green), and busted picks (e.g. Netherlands over
Canada) as *wrong* (red).

## What Changes

- Apply an outcome color scheme to `project-wc-bracket-analyst.html`'s receipts rows:
  - **Green** — every pick whose team advanced from that round, including "busted path but correct
    winner" rows (shifted-opponent QF wins). Uses the site's `--green`.
  - **Red** — every failed pick, including busted picks (picked team already out) and shootout
    losses. A muted brick red is introduced for this (the palette has no body-copy red today);
    exact value chosen in design for legibility on `--warm-white`.
  - **Black** — undecided rows (currently the final/champion row), using the site's near-black
    `--text-dark`, visually neutral until graded.
- The coloring applies to the row's mark and text treatment (exact weighting — mark, text, or subtle
  row tint — settled in design for legibility), consistently across desktop and mobile.
- This supersedes the "misses muted, not red" visual decision recorded in the `add-wc-receipts`
  change, at Kavit's direction. Grading logic is untouched — only its visual encoding changes.

## Capabilities

### New Capabilities
<!-- None. -->

### Modified Capabilities
- `project-showcase`: Adds a requirement for outcome color-coding of the receipts rows.

## Impact

- File: `project-wc-bracket-analyst.html` (receipts CSS + row classes; no row content changes).
- Mobile: same classes at phone widths; contrast verified at 375px/320px.
