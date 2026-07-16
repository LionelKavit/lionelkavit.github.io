## ADDED Requirements

### Requirement: Trust section explains true decision mechanics

The "Why you can trust it" section of the Bracket Analyst case-study page SHALL explain concretely
how a matchup is decided — the two teams' Elo-derived win probability, played out across 50,000
simulated tournaments to produce standings, knockout odds, and pool verdicts — and SHALL frame the
model's edge as consistency versus form: Elo encodes long-run results where pundit narratives chase
recent form, evidenced only by decided, receipts-backed outcomes (the model's faith in Spain and
Argentina against the form-favored France and England). The section SHALL state the role of pool size
and risk appetite correctly as pick-boldness calibration (which underdogs are worth backing for
differentiation), never as part of match simulation. The section MUST NOT claim goal-count prediction
or any per-stat capability not documented by the application's repository, and every mechanical claim
MUST be consistent with the repository README at publish time. The pipeline diagram and guardrail
cards remain.

#### Scenario: A reader can explain one matchup

- **WHEN** a visitor finishes the section's opening copy
- **THEN** they can state how a single matchup is decided (Elo gap → win probability → simulated
  outcome) before the 50,000-tournament scale is invoked

#### Scenario: Form vs consistency lands on decided facts

- **WHEN** the section makes the consistency-over-form argument
- **THEN** it cites only decided results the receipts show (semifinal outcomes), keeps the champion
  pick in play, and avoids match-narration claims (no "flawless"/"dominant" assertions)

#### Scenario: Calibration is attributed correctly

- **WHEN** the section mentions pool size or risk appetite
- **THEN** they are described as calibrating pick boldness/differentiation only, distinctly separate
  from how matches are simulated

#### Scenario: No undocumented mechanics

- **WHEN** the section's mechanical claims are compared against the repository README
- **THEN** every claim is supported, and no goal-count or minute-level stat prediction is asserted
  anywhere in the section

#### Scenario: Mobile-safe copy

- **WHEN** the section renders at 320px–430px and desktop
- **THEN** the rewritten copy introduces no overflow or type-scale regressions (text-only; diagram
  and cards unchanged)
