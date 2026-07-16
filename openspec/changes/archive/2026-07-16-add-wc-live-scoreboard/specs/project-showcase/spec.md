## ADDED Requirements

### Requirement: Live tournament scoreboard strip

The Bracket Analyst case-study page SHALL display a slim scoreboard strip between the hero and the
impact bar summarizing the app's real-World Cup 2026 prediction record. The strip SHALL contain an
uppercase label (`LIVE · WORLD CUP 2026` while the tournament is ongoing, switching to a
permanent-record label after the final), three to four short result pills, and an "as of <date>"
stamp. Each pill SHALL carry exactly one of three visual states — correct (✓), missed (✗), or
in play — and only results already decided in the real tournament SHALL be marked ✓ or ✗; undecided
picks MUST be shown as in play. The strip SHALL reuse the page's existing design system (pitch
palette, DM Sans label typography, established pill idiom) and SHALL introduce no JavaScript.

#### Scenario: Strip summarizes the record at a glance

- **WHEN** a visitor loads `project-wc-bracket-analyst.html` during the tournament
- **THEN** a strip appears directly below the hero and above the impact bar with the `LIVE · WORLD
  CUP 2026` label, result pills (e.g. `✓ 4/4 semifinalists called`, `✓ Spain over France — called`,
  `Final pick: Argentina — in play`), and an "as of" date stamp

#### Scenario: Only decided results are claimed

- **WHEN** a pick's real-world match has not yet been played
- **THEN** its pill renders in the in-play state and is not presented as correct or missed

#### Scenario: Strip flips to a permanent record after the final

- **WHEN** the tournament ends and the page is updated
- **THEN** the label reads as a final-record variant (e.g. `FINAL RECORD · WORLD CUP 2026`) with the
  same strip structure and updated pill states, without structural rework

#### Scenario: Strip is mobile-clean

- **WHEN** the strip is viewed at viewport widths between 320px and 430px
- **THEN** the pills wrap onto multiple centered rows with no horizontal overflow, the label and
  date stamp stack legibly, and pill text renders at a mobile-appropriate size (roughly 0.7–0.8rem)
- **AND** spacing within a pill is visibly tighter than spacing between pills

#### Scenario: Desktop layout is preserved

- **WHEN** the page is viewed at a desktop width (≥769px)
- **THEN** the hero and impact bar render as before, with the strip forming a continuous dark band
  between them and no other section shifted
