# project-showcase Specification

## Purpose
TBD - created by archiving change replace-epl-with-pocket-scout. Update Purpose after archive.
## Requirements
### Requirement: Narrative leads with the user problem

The Pocket Scout case-study page SHALL frame its primary value proposition as solving a real problem for the millions of people who play Fantasy Premier League: delivering personalized transfer, captaincy, and chip advice on demand — every question about your squad answered at your fingertips. Groundedness in real data SHALL be presented as a supporting feature that makes the advice reliable, NOT as the headline selling point.

#### Scenario: Hero foregrounds personalized advice

- **WHEN** a visitor reads the hero and lead section of `project-fpl-advisor.html`
- **THEN** the headline and opening copy emphasize personalized transfer/captaincy/chip advice for FPL managers (the problem solved and the value delivered)
- **AND** any mention of data-groundedness frames it as what makes that advice trustworthy, not as the main pitch

#### Scenario: Groundedness positioned as a reliability feature

- **WHEN** a visitor reaches the section about data-groundedness
- **THEN** that section is presented as one feature among the product's value (reliability/trust), positioned after the value/problem framing rather than as the page's central thesis

### Requirement: Home-page project card contract

Each project shown in the home page `#projects` grid SHALL be represented by a card containing a category tag, a title, a one-paragraph description, a thumbnail image with descriptive `alt` text, and a "Read case study" link. The thumbnail, title, and link MUST all point to the same project case-study page.

#### Scenario: Pocket Scout replaces the EPL card

- **WHEN** a visitor views the `#projects` grid on `index.html`
- **THEN** the card previously titled "Premier League Quant Analysis" is gone
- **AND** in its place is a card titled "Pocket Scout — Fantasy Premier League Advisor" with a tag referencing agentic AI / full-stack work and a description that leads with the personalized transfer/captaincy/chip advice it gives FPL managers (with groundedness mentioned as the reliability feature)
- **AND** the card's thumbnail link, title link, and "Read case study" link all resolve to `project-fpl-advisor.html`

#### Scenario: Old project is orphaned, not deleted

- **WHEN** the change is applied
- **THEN** the file `project-epl-analysis_3_1.html` still exists in the repository
- **AND** no other file links to `project-epl-analysis_3_1.html` (it is unreachable through site navigation)
- **AND** no linked page references `prompt-flow-graph.png`

### Requirement: Project case-study page structure

A project case-study page SHALL reuse the shared design system (pitch-green palette, Lora + DM Sans typography, fixed nav with an "All projects" back link, scroll-reveal animations) and SHALL include, in order: a hero with category tag, title, and technology pills; an impact bar of four headline metrics; body sections describing how the system works and its architecture; a personal reflection; and a closing call-to-action.

#### Scenario: Pocket Scout page matches the project-page template

- **WHEN** a visitor opens `project-fpl-advisor.html`
- **THEN** the page renders a dark "pitch" hero with the Pocket Scout title and technology pills
- **AND** an impact bar shows four headline figures framed around the problem and value (e.g. the size of the FPL audience, the decisions advised per gameweek, the season-long coverage, and data-grounded reliability) rather than internal engineering metrics
- **AND** body sections explain how the personalized advice is produced (the two-phase deterministic + Claude engine), how it stays reliable by grounding in real FPL data, and the technology stack / architecture
- **AND** the page ends with a reflection and a call-to-action that links to the contact section and to the project's GitHub repository

#### Scenario: Accurate, sourced metrics

- **WHEN** the page presents quantitative claims
- **THEN** app-specific figures (e.g. rank correlation, test count, seasons of data) match the values documented in the Pocket Scout repository README at publish time
- **AND** audience/scale figures (e.g. the number of FPL managers) reflect publicly reported facts about Fantasy Premier League

### Requirement: Annotated product screenshots

The Pocket Scout case-study page SHALL feature real product screenshots from the `images/` folder to demonstrate the working application, not only prose. Screenshots MUST be presented in framed containers consistent with the page's design system (rounded border, subtle shadow, pitch-green caption bar) and each MUST carry a caption describing what the visitor is looking at.

#### Scenario: Screenshots illustrate the key features

- **WHEN** a visitor scrolls the `project-fpl-advisor.html` body
- **THEN** the lead visual near the top is a click-to-play demo video of the working app, using the dashboard screenshot (squad ratings + Ask the Scout) as its poster image
- **AND** the grounded chat, the This Week / Long Term / Chips planner, the player-detail dialog, and the demo-mode dream team are each illustrated by their corresponding screenshot from `images/`
- **AND** every screenshot or video sits in a framed container with a descriptive caption

#### Scenario: Lead demo video loads responsibly

- **WHEN** the page first loads
- **THEN** the lead video does not download its full payload up front (it uses `preload="metadata"` with a poster image)
- **AND** the video exposes native playback controls so the visitor plays it on demand

#### Scenario: Images use descriptive alt text

- **WHEN** any product screenshot is rendered
- **THEN** its `img` element has descriptive `alt` text naming the feature shown

