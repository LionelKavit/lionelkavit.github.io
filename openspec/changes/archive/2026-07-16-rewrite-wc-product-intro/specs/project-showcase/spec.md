## ADDED Requirements

### Requirement: Product intro is outcome-first and unambiguous

The bracket-predictor intro section of the Bracket Analyst case-study page SHALL communicate, in
order: (1) what the app produces — a complete, editable World Cup bracket with real odds behind every
pick, ready for a pool, in about a minute; (2) the tournament complexity the engine handles invisibly
(48 teams, 12 groups, the 8 best third-placed teams) framed as handled-for-you, not as prerequisite
reading; (3) the interaction loop — autofill calibrated to pool size and risk appetite, edit with
real head-to-head odds and flagged underdogs, lock, export CSV to the pool. A reader with no World
Cup-format knowledge MUST understand what the product is from the first two sentences. Sentences
SHALL carry one idea each, and the section MUST NOT grow beyond its current length. All stated
capabilities MUST already be documented (page or repository README) — no new claims.

#### Scenario: A stranger gets it in two sentences

- **WHEN** a reader unfamiliar with World Cup formats reads the section's first two sentences
- **THEN** they can say what the app produces and roughly how fast, without needing the group-stage
  rules explained first

#### Scenario: Complexity reads as wow, not homework

- **WHEN** the reader reaches the 48-team/12-group/third-place material
- **THEN** it is framed as work the engine already did for them, after the outcome has been stated

#### Scenario: The loop reads in order

- **WHEN** the reader finishes the section
- **THEN** they know the sequence autofill → edit with odds and upset flags → lock → export CSV, and
  the demo beat below follows naturally

#### Scenario: No inflation

- **WHEN** the new copy is compared to the app's documented capabilities and the page's other claims
- **THEN** every stated capability already exists and no stat contradicts the impact bar or receipts

#### Scenario: Mobile-safe copy

- **WHEN** the section renders at 320px–430px
- **THEN** the copy wraps cleanly with no overflow or type-scale regressions (text-only change)
