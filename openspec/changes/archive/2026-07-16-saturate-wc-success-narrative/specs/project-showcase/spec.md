## ADDED Requirements

### Requirement: Success-story narrative threads through all content sections

Every content section of the Bracket Analyst case-study page SHALL carry the user-success narrative
where appropriate to that section's subject — a brief story touch connecting the section's capability
to Kavit's World Cup 2026 run — so the page reads as one continuous story in the order product →
proof → person → trust → depth. Each woven claim MUST correspond to a decided result shown in the
receipts or scoreboard; the champion pick MUST remain framed as in play until decided; and no section
may repeat another section's stat or contradict the receipts. Sections joined abruptly by the
storytelling reorder SHALL receive a transitional lead-in. The voice guardrails of the proven-record
narrative requirement (no self-applied "expert" label, no lock claims, no pool-win claims) apply to
every woven line.

#### Scenario: Each section carries its own story angle

- **WHEN** a visitor reads the pool-winning strategy, group stage, and Ask the Analyst sections
- **THEN** each contains a brief, section-appropriate reference to the run (e.g. strategy → bold
  branches that survived shifted paths; group stage → how the predicted groups resolved; chat → the
  same grounded analyst behind the calls), with no stat repeated across sections

#### Scenario: Woven claims trace to the receipts

- **WHEN** any story touch makes a factual claim
- **THEN** that claim matches a decided result in the receipts or scoreboard, and no touch states the
  champion pick as won before the final is decided

#### Scenario: Reordered seams read smoothly

- **WHEN** a visitor crosses a seam created by the storytelling reorder (e.g. reflection into trust)
- **THEN** a transitional line carries the narrative across the seam rather than an abrupt topic jump

#### Scenario: Text-only and mobile-safe

- **WHEN** the woven copy renders at phone widths (320px–430px) and desktop
- **THEN** no layout, overflow, or type-scale regressions are introduced (copy-only change)
