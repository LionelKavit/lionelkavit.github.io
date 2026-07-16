## ADDED Requirements

### Requirement: Impact bar carries a verified tournament-truth metric

The Bracket Analyst impact bar SHALL include a metric stating the app's verified real-World Cup 2026
prediction record (initially `4/4` semifinalists called), replacing the data-scale stat (`1,489`
players/teams) in the third slot. The bar SHALL retain exactly four stats and its existing styling
and structure. The tournament-truth metric MUST state only results already decided in the real
tournament, MAY be upgraded to a stronger decided claim after later rounds conclude, and SHALL use
the same wording for the record as the page's scoreboard strip.

#### Scenario: Third slot shows the tournament record

- **WHEN** a visitor views the impact bar on `project-wc-bracket-analyst.html`
- **THEN** the third stat reads `4/4` with a label identifying it as semifinalists called at World
  Cup 2026, and the `~60s`, `50,000`, and `287` stats are unchanged

#### Scenario: Only decided results appear in the bar

- **WHEN** the metric's underlying claim is chosen or later upgraded
- **THEN** it reflects only matches already decided in the real tournament, never a pending pick

#### Scenario: Metric fits the mobile grid

- **WHEN** the impact bar is viewed at viewport widths between 320px and 430px
- **THEN** the bar's existing 2×2 mobile grid renders the new number and label without clipping or
  overflow, with the label wrapping consistently with the sibling stat labels (which wrap to 4–5
  short lines at phone widths)

#### Scenario: Desktop layout is preserved

- **WHEN** the page is viewed at a desktop width (≥769px)
- **THEN** the impact bar renders four stats in its existing four-column layout with unchanged
  styling
