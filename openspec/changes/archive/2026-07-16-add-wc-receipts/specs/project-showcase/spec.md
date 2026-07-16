## ADDED Requirements

### Requirement: Prediction receipts section

The Bracket Analyst case-study page SHALL include a "receipts" section presenting the bracket's
predicted-vs-actual record for World Cup 2026, placed before the personal reflection at the position
the page-structure requirement assigns it in the narrative order. The section SHALL group picks by round with a per-round tally, showing for
each pick the prediction, the real result, and a correct/missed/in-play mark. Misses decided by
penalty shootouts SHALL be annotated as such. The section SHALL state the overall record honestly —
including the misses — and every displayed pick MUST match the bracket export verbatim: no pick may
be altered, added, or reframed after its real-world result is known. The section SHALL include a
provenance note that attributes the bracket accurately (Kavit's bracket, built with the app — model
autofill plus hand-tweaked picks) and, because no pre-tournament lock evidence exists, makes no
locked-before-kickoff claim, plus a link to the live app. Real-world results MUST match the
user-verified scorecard; undecided matches MUST be marked in play rather than correct or missed. The
section SHALL reuse the page's existing design system and introduce no JavaScript. The section's
on-page title SHALL NOT use the internal "receipts" name; it SHALL present the bracket's identity —
a balanced-risk bracket built for a 50-person pool (settings per Kavit, user-verified) — so a neutral
fan can identify with it, with the intro noting that this balanced philosophy showed most from the
quarterfinals onward. On-page cross-references from other sections SHALL match this public framing
rather than the internal name.

#### Scenario: Round-grouped record with tallies

- **WHEN** a visitor reads the receipts section
- **THEN** picks are grouped by round (Round of 32 through Final), each round headed by its tally
  (e.g. `ROUND OF 32 · 12/16`), with one row per pick showing prediction, result, and a ✓/✗/– mark

#### Scenario: Shootout misses are annotated

- **WHEN** a missed pick was decided by a penalty shootout
- **THEN** its result cell carries a "lost on pens" (or equivalent) annotation alongside the ✗ mark

#### Scenario: Provenance is claimed only as strongly as the evidence

- **WHEN** the provenance note is rendered
- **THEN** it attributes the bracket as Kavit's own, built with the app (model autofill plus
  hand-tweaked picks), makes no locked-before-kickoff claim (no verifiable pre-tournament evidence
  exists), and links the live app

#### Scenario: No pick is retconned

- **WHEN** any pick's displayed value is compared against the bracket export (`my-bracket (7).csv`)
- **THEN** they match exactly — in particular the Round-of-16 Brazil pick is shown as a miss (upset
  by Norway), and no after-the-fact "hand-tweak" pick appears anywhere in the section

#### Scenario: Undecided picks are not graded

- **WHEN** a pick's real-world match has not been played at publish time
- **THEN** its row shows an in-play mark and is updated only after the match is decided

#### Scenario: Section is mobile-clean

- **WHEN** the section is viewed at viewport widths between 320px and 430px
- **THEN** every row reflows to remain readable with no horizontal page overflow, round subheaders
  remain scannable, and the marks stay visually attached to their rows

#### Scenario: Desktop layout is preserved

- **WHEN** the page is viewed at a desktop width (≥769px)
- **THEN** the new section follows the page's existing section rhythm (labels, dividers, spacing)
  and no other section is altered
