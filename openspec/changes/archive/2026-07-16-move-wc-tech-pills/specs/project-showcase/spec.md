## MODIFIED Requirements

### Requirement: Bracket Analyst case-study page structure

The Bracket Analyst case-study page SHALL reuse the shared design system (pitch-green palette, Lora +
DM Sans typography, fixed nav with an "All projects" back link, scroll-reveal animations) and SHALL
present its content in a storytelling order: a hero with category tag and title; the live scoreboard
strip; an impact bar of four headline metrics; then body sections in this order —
**(1)** what the app is (the bracket predictor intro), **(2)** the demo video as its own beat,
**(3)** the public grading of Kavit's bracket (the receipts), **(4)** the personal reflection,
**(5)** why it can be trusted (how it stays grounded plus the guardrails that govern the AI's
behaviour), **(6)** the app's feature sections (pool-winning strategy / upset watch, the group stage,
and Ask the Analyst), **(7)** a "built with" technology-pills beat styled for the light content
surface — followed by the unofficial-project disclaimer and a closing call-to-action whose primary
action links to the live app (see the Live application links requirement). The page SHALL also carry
a disclaimer that it is an unofficial hobby project, not affiliated with FIFA, using original styling
and no FIFA logos or imagery.

#### Scenario: Page matches the storytelling order

- **WHEN** a visitor opens `project-wc-bracket-analyst.html`
- **THEN** the page renders a dark "pitch" hero (category tag and title, no technology pills), the
  live scoreboard strip, and an impact bar of four headline figures framed around the product's value
  and rigour (e.g. how fast a complete bracket can be produced, the simulations behind each pick, the
  verified tournament record, and the test coverage that keeps the numbers honest)
- **AND** the body reads product → proof → person → trust → depth: the bracket-predictor intro, then
  the demo video, then the receipts, then the reflection, then the trust/guardrails section (Elo
  ratings → a Monte Carlo engine → a grounded Analyst), then the feature sections (pool-winning
  strategy / upset watch, group stage, Ask the Analyst), then the "built with" technology pills
- **AND** the page ends with the disclaimer and a call-to-action whose primary action links to the
  live app (`https://fifa-wc-bracket.vercel.app/`), with links to the contact section and to the
  project's GitHub repository (`github.com/LionelKavit/fifa-wc-fantasy`) also present

#### Scenario: Technology pills are legible at the bottom

- **WHEN** a visitor reaches the "built with" beat between Ask the Analyst and the disclaimer
- **THEN** the pills render in a light-surface variant readable on the cream background, wrapping
  centered at phone widths (320px–430px) with no overflow

#### Scenario: Section moves preserve rendering integrity

- **WHEN** the reordered page is viewed at phone widths (320px–430px) and at desktop (≥769px)
- **THEN** every section renders as before the move (scroll-reveal, dividers exactly one between
  adjacent sections, no overflow), with only the order changed

#### Scenario: Unofficial-project disclaimer is present

- **WHEN** a visitor reads the page
- **THEN** a disclaimer states that the project is an unofficial hobby project, not affiliated with
  FIFA, and uses original styling with no FIFA logos or imagery

#### Scenario: Accurate, sourced metrics

- **WHEN** the page presents quantitative claims
- **THEN** app-specific figures (e.g. test count, number of product surfaces) match the values
  documented in the project repository README/docs at publish time
- **AND** tournament/format figures (e.g. 48 teams, 12 groups, 8 best third-placed teams) reflect
  publicly reported facts about the FIFA World Cup 2026
