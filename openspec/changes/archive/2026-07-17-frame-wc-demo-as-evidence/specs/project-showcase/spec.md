## ADDED Requirements

### Requirement: Demo video is framed as the verified real session

The Bracket Analyst case-study page SHALL present the demo video as the real recorded session behind
Kavit's bracket lineage — balanced risk setting, 50-person pool, completed and exported on camera —
connecting it explicitly to the graded section, with the in-video Analyst's backbone assessment
("well-supported by the model" for Argentina, France, Spain, and England) cited as on-camera
evidence. Timing claims SHALL be limited to the public record (in the repository since July 1, live
on the page before the quarterfinals) and SHALL NOT be presented as a pre-tournament lock. The copy
MUST disclose that the graded export post-dates the recording (further saves with pick tweaks) and
MUST NOT claim the on-screen bracket is pick-for-pick the graded bracket. Every stated detail MUST be
verifiable in the footage or the public git/deploy history.

#### Scenario: Demo beat reads as evidence

- **WHEN** a visitor reaches the "See it work" beat
- **THEN** a lead-in presents the video as the real session (balanced, pool of 50, recorded in the
  knockouts' opening days) with the Analyst's on-camera backbone quote, and the caption labels the
  footage as the real session rather than a generic walkthrough

#### Scenario: Divergence is disclosed, not hidden

- **WHEN** a visitor reads the provenance note in the graded section
- **THEN** it states that the graded export came after the recording (later saves, a couple of
  Round-of-16 tweaks), so a viewer comparing the video's final bracket to the graded table finds the
  difference already acknowledged

#### Scenario: Timing claim matches the public record

- **WHEN** the copy references when the session became public
- **THEN** it claims only repo/deploy-verifiable timing (public since July 1, live before the
  quarterfinals) and continues to make no pre-tournament lock claim

#### Scenario: Mobile-safe copy

- **WHEN** the updated beat and note render at 320px–430px and desktop
- **THEN** no overflow or type-scale regressions are introduced (text-only change)
