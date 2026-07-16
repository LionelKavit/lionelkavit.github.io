## ADDED Requirements

### Requirement: Receipts rows are outcome color-coded

The receipts table rows on the Bracket Analyst case-study page SHALL be color-coded by outcome:
**green** for every correct pick (any row whose picked team advanced from that round, including rows
where the predicted opponent path broke but the picked winner still advanced), **red** for every
wrong pick (including busted picks whose team was already out and shootout losses), and **black
(neutral dark)** for undecided rows. The coloring SHALL apply to the row's mark and text treatment
consistently on desktop and mobile, remain legible at phone-width text sizes on the section's
background, and use a red that sits within the page's muted palette. This supersedes the earlier
muted-miss visual treatment; the underlying grading logic is unchanged.

#### Scenario: Correct picks are green — including shifted-path wins

- **WHEN** a visitor scans rows like `Spain over Austria` or `England over Brazil` (won its
  quarterfinal against Norway after Brazil's exit)
- **THEN** both render green as correct picks

#### Scenario: Wrong picks are red — including busted picks

- **WHEN** a visitor scans rows like `Germany over Paraguay` (lost on pens), `Netherlands over
  Canada` (picked team already out), or `Brazil over Norway` (upset)
- **THEN** all render red as wrong picks

#### Scenario: Undecided rows are black until graded

- **WHEN** a row's match has not been decided (currently the final/champion row)
- **THEN** it renders in the neutral dark treatment, turning green or red only after the result

#### Scenario: Legible at phone widths

- **WHEN** the table renders at 320px–430px
- **THEN** all three colors remain distinguishable and readable at the table's mobile text size, with
  no other layout change
