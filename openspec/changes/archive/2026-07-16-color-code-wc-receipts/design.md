## Context

Receipts rows already carry outcome classes: default (hit), `.miss`, `.pending`, with `.r-mark`
colored `--green` for hits and `--text-light` (muted) for misses/pending. The grading rule (✓ = picked
team advanced from the round, regardless of opponent shifts) is already encoded in the rows — this
change is purely the visual layer. The page palette: greens (`--green #2D6B2D`, `--text-light
#5A845A`), creams, `--text-dark #0D1F0D`; the only red anywhere on the site is index's Wisconsin
accent `#C5050C`, which is too loud for table text on `--warm-white`.

## Goals / Non-Goals

**Goals:** instant scorecard legibility — green right, red wrong, black undecided — at desktop and
phone widths, without making the misses look like error states screaming over the page's calm
aesthetic.

**Non-Goals:** no grading/content changes, no row structure changes, no changes to the scoreboard
strip pills (they keep their dark-surface scheme).

## Decisions

- **Red value:** a muted brick in the page's earthy register, target ≈ `#A63A2E` (tuned in preview),
  used for the miss rows' mark and text tint. Rationale: `#C5050C` fights the palette;
  the chosen red must hold ~4.5:1 contrast on `--warm-white (#FFF9F3)` at 0.75–0.82rem text.
- **Encoding weight:** color the `✓/✗/–` mark at full strength and tint the row's pick/result text in
  the same hue (misses currently dim the pick text; that dimming is replaced by the red tint). No
  full-row background tints — 31 alternating tinted bands would dominate the section. Pending rows:
  mark and text in `--text-dark` (reads "ungraded", distinct from both outcomes).
- **Class mapping stays as-is** (`default/.miss/.pending`) — only the CSS behind the classes changes,
  so the post-final flip remains a class swap.
- **"Busted but correct winner" rows are green by construction** (they're graded hits); the QF rows'
  "Advanced — beat X" result text already explains the shifted path. No new annotation needed.

## Risks / Trade-offs

- **Red misses read harsher than the page's tone** → mitigated by the muted brick and text-tint (not
  background) treatment; the misses are the credibility feature, and the user explicitly wants them
  legible as misses.
- **Contrast at small mobile sizes** → verify the red and `--text-dark` at 0.75rem on `--warm-white`
  at 320px; bump darkness before size.
- **Semis flip Sunday** → pending → green/red is a class change only; no CSS rework.
