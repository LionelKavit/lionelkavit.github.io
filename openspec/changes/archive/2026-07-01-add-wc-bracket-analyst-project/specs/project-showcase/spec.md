## MODIFIED Requirements

### Requirement: Home-page project card contract

Each project shown in the home page `#projects` grid SHALL be represented by a card containing a category tag, a title, a one-paragraph description, a thumbnail image with descriptive `alt` text, and a "Read case study" link. The thumbnail, title, and link MUST all point to the same project case-study page. Adding a new project to the showcase SHALL append a new card following this contract without altering the existing cards.

#### Scenario: Bracket Analyst card is added

- **WHEN** a visitor views the `#projects` grid on `index.html`
- **THEN** there is a card titled "The Bracket Analyst — FIFA World Cup 2026" with a tag referencing agentic AI / full-stack work and a description that leads with the value it delivers to a bracket-pool player (pick guidance and pool-winning strategy), with groundedness mentioned as the reliability feature
- **AND** the card's thumbnail link, title link, and "Read case study" link all resolve to `project-wc-bracket-analyst.html`
- **AND** the thumbnail is a real product screenshot (`images/wc-analyst-hero.png`) with descriptive `alt` text

#### Scenario: Existing project cards are preserved

- **WHEN** the change is applied
- **THEN** the five previously existing project cards (MSA data agent, Buy-side analyst agent, Process capability, WattBot, and Pocket Scout) remain present and unchanged in the `#projects` grid
- **AND** each still links to its own existing case-study page

## ADDED Requirements

### Requirement: Bracket Analyst narrative leads with the user problem

The Bracket Analyst case-study page SHALL frame its primary value proposition as helping a FIFA World Cup bracket-pool player at their two moments of need — filling out a bracket well before the deadline (and standing out enough to win the pool) and following the bracket's fate once the tournament starts. Groundedness in real data (Elo-strength probabilities that are never invented) SHALL be presented as the feature that makes that advice trustworthy, NOT as the headline selling point.

#### Scenario: Hero foregrounds the bracket-player value

- **WHEN** a visitor reads the hero and lead section of `project-wc-bracket-analyst.html`
- **THEN** the headline and opening copy emphasize the value delivered to a bracket-pool player (pick guidance, pool-winning strategy, and demystifying the confusing format)
- **AND** any mention of data-groundedness frames it as what makes the advice trustworthy, not as the main pitch

#### Scenario: Groundedness positioned as a reliability feature

- **WHEN** a visitor reaches the section about how the app stays grounded
- **THEN** that section is presented as one feature among the product's value (reliability/trust — real Elo-based odds, never a made-up number), positioned after the value/problem framing rather than as the page's central thesis

### Requirement: Bracket Analyst case-study page structure

The Bracket Analyst case-study page SHALL reuse the shared design system (pitch-green palette, Lora + DM Sans typography, fixed nav with an "All projects" back link, scroll-reveal animations) and SHALL include, in order: a hero with category tag, title, and technology pills; an impact bar of four headline metrics; body sections describing the product's value, its pool-winning strategy, and why it can be trusted (how it stays grounded plus the guardrails that govern the AI's behaviour); a personal reflection; and a closing call-to-action. The page SHALL also carry a disclaimer that it is an unofficial hobby project, not affiliated with FIFA, using original styling and no FIFA logos or imagery.

#### Scenario: Page matches the project-page template

- **WHEN** a visitor opens `project-wc-bracket-analyst.html`
- **THEN** the page renders a dark "pitch" hero with the Bracket Analyst title and technology pills
- **AND** an impact bar shows four headline figures framed around the product's value and rigour (e.g. how fast a complete bracket can be produced, the number of simulated tournaments behind each pick, the scale of the grounded data model, and the test coverage that keeps the numbers honest) rather than incidental facts
- **AND** body sections explain the product's value (the bracket predictor and the group stage), the "You vs. the Model" pool-winning strategy, and why it can be trusted — how it stays grounded (Elo ratings → a Monte Carlo engine → a grounded Analyst) plus the guardrails that keep the AI from inventing or contradicting numbers
- **AND** the page ends with a reflection and a call-to-action that links to the contact section and to the project's GitHub repository (`github.com/LionelKavit/fifa-wc-fantasy`)

#### Scenario: Unofficial-project disclaimer is present

- **WHEN** a visitor reads the page
- **THEN** a disclaimer states that the project is an unofficial hobby project, not affiliated with FIFA, and uses original styling with no FIFA logos or imagery

#### Scenario: Accurate, sourced metrics

- **WHEN** the page presents quantitative claims
- **THEN** app-specific figures (e.g. test count, number of product surfaces) match the values documented in the project repository README/docs at publish time
- **AND** tournament/format figures (e.g. 48 teams, 12 groups, 8 best third-placed teams) reflect publicly reported facts about the FIFA World Cup 2026

### Requirement: Bracket Analyst annotated product screenshots

The Bracket Analyst case-study page SHALL feature real product screenshots, copied into the site's `images/` folder from the project repository, to demonstrate the working application rather than relying on prose alone. Screenshots MUST be presented in framed containers consistent with the page's design system (rounded border, subtle shadow, pitch-green caption bar) and each MUST carry a caption describing what the visitor is looking at and descriptive `alt` text.

#### Scenario: Screenshots illustrate the key surfaces

- **WHEN** a visitor scrolls the `project-wc-bracket-analyst.html` body
- **THEN** the lead visual near the top is a click-to-play demo video of the working app, using the knockout-predictor screenshot (`images/wc-analyst-hero.png`) as its poster image
- **AND** the grounded "Ask the Analyst" chat, the group-stage dashboard, and the team-detail view are each illustrated by their corresponding screenshot copied from the project repository
- **AND** every screenshot or video sits in a framed container with a descriptive caption

#### Scenario: Lead demo video loads responsibly

- **WHEN** the page first loads
- **THEN** the lead video does not download its full payload up front (it uses `preload="metadata"` with a poster image)
- **AND** the video exposes native playback controls so the visitor plays it on demand

#### Scenario: Images use descriptive alt text

- **WHEN** any product screenshot is rendered
- **THEN** its `img` element has descriptive `alt` text naming the surface shown
