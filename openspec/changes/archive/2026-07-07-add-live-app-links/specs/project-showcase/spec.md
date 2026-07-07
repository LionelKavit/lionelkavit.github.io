## ADDED Requirements

### Requirement: Live application links

A showcased project that has a publicly deployed, usable live app SHALL surface a link to that app from both its home-page card (in the `#projects` grid on `index.html`) and the closing call-to-action of its case-study page. The two projects with a deployed app, and their URLs, are:

- **Pocket Scout — Fantasy Premier League Advisor** → `https://fantasy-premier-league-advisor.vercel.app/`
- **The Bracket Analyst — FIFA World Cup 2026** → `https://fifa-wc-bracket.vercel.app/`

On the case-study page the live-app link SHALL be presented as the primary call-to-action. Every live-app link SHALL open in a new browser tab with `rel="noopener noreferrer"`. Adding a live-app link SHALL NOT remove the existing "Read case study", "View on GitHub", or "Get in touch" links. A project without a deployed app SHALL NOT show a live-app link.

#### Scenario: Pocket Scout live app is reachable

- **WHEN** a visitor views the Pocket Scout card on `index.html` and the closing CTA of `project-fpl-advisor.html`
- **THEN** both surfaces present a live-app link resolving to `https://fantasy-premier-league-advisor.vercel.app/`
- **AND** on the case-study page that link is the primary call-to-action, with "View on GitHub" and "Get in touch" still present

#### Scenario: Bracket Analyst live app is reachable

- **WHEN** a visitor views the Bracket Analyst card on `index.html` and the closing CTA of `project-wc-bracket-analyst.html`
- **THEN** both surfaces present a live-app link resolving to `https://fifa-wc-bracket.vercel.app/`
- **AND** on the case-study page that link is the primary call-to-action, with "View on GitHub" and "Get in touch" still present

#### Scenario: Live-app links open safely in a new tab

- **WHEN** any live-app link is rendered
- **THEN** it carries `target="_blank"` and `rel="noopener noreferrer"`

#### Scenario: Projects without a deployed app show no live-app link

- **WHEN** a visitor views the MSA data agent, Buy-side analyst agent, Process capability, or WattBot cards
- **THEN** none of them shows a live-app link (each keeps only its "Read case study" link)

## MODIFIED Requirements

### Requirement: Home-page project card contract

Each project shown in the home page `#projects` grid SHALL be represented by a card containing a category tag, a title, a one-paragraph description, a thumbnail image with descriptive `alt` text, and a "Read case study" link. The thumbnail, title, and "Read case study" link MUST all point to the same project case-study page. A card for a project that also has a publicly deployed live app MAY additionally include a link to that live app (see the Live application links requirement). Adding a new project to the showcase SHALL append a new card following this contract without altering the existing cards.

#### Scenario: Card carries the required contract

- **WHEN** a visitor views any card in the `#projects` grid
- **THEN** it shows a category tag, a title, a one-paragraph description, a thumbnail with descriptive `alt` text, and a "Read case study" link
- **AND** the thumbnail link, title link, and "Read case study" link all resolve to the same case-study page

#### Scenario: Cards for deployed projects also link to the live app

- **WHEN** a visitor views the Pocket Scout and Bracket Analyst cards
- **THEN** each additionally shows a "Live app" link (per the Live application links requirement) alongside its "Read case study" link
- **AND** the "Read case study" links still resolve to `project-fpl-advisor.html` and `project-wc-bracket-analyst.html` respectively

#### Scenario: Cards without a deployed app are unchanged

- **WHEN** a visitor views the four cards without a live app (MSA data agent, Buy-side analyst agent, Process capability, WattBot)
- **THEN** each shows only its "Read case study" link, with no live-app link

### Requirement: Project case-study page structure

A project case-study page SHALL reuse the shared design system (pitch-green palette, Lora + DM Sans typography, fixed nav with an "All projects" back link, scroll-reveal animations) and SHALL include, in order: a hero with category tag, title, and technology pills; an impact bar of four headline metrics; body sections describing how the system works and its architecture; a personal reflection; and a closing call-to-action. Where the project has a deployed live app, the closing call-to-action SHALL feature a link to that app as its primary action (see the Live application links requirement).

#### Scenario: Pocket Scout page matches the project-page template

- **WHEN** a visitor opens `project-fpl-advisor.html`
- **THEN** the page renders a dark "pitch" hero with the Pocket Scout title and technology pills
- **AND** an impact bar shows four headline figures framed around the problem and value (e.g. the size of the FPL audience, the decisions advised per gameweek, the season-long coverage, and data-grounded reliability) rather than internal engineering metrics
- **AND** body sections explain how the personalized advice is produced (the two-phase deterministic + Claude engine), how it stays reliable by grounding in real FPL data, and the technology stack / architecture
- **AND** the page ends with a reflection and a call-to-action whose primary action links to the live app, with links to the contact section and to the project's GitHub repository also present

#### Scenario: Accurate, sourced metrics

- **WHEN** the page presents quantitative claims
- **THEN** app-specific figures (e.g. rank correlation, test count, seasons of data) match the values documented in the Pocket Scout repository README at publish time
- **AND** audience/scale figures (e.g. the number of FPL managers) reflect publicly reported facts about Fantasy Premier League

### Requirement: Bracket Analyst case-study page structure

The Bracket Analyst case-study page SHALL reuse the shared design system (pitch-green palette, Lora + DM Sans typography, fixed nav with an "All projects" back link, scroll-reveal animations) and SHALL include, in order: a hero with category tag, title, and technology pills; an impact bar of four headline metrics; body sections describing the product's value, its pool-winning strategy, and why it can be trusted (how it stays grounded plus the guardrails that govern the AI's behaviour); a personal reflection; and a closing call-to-action whose primary action links to the live app (see the Live application links requirement). The page SHALL also carry a disclaimer that it is an unofficial hobby project, not affiliated with FIFA, using original styling and no FIFA logos or imagery.

#### Scenario: Page matches the project-page template

- **WHEN** a visitor opens `project-wc-bracket-analyst.html`
- **THEN** the page renders a dark "pitch" hero with the Bracket Analyst title and technology pills
- **AND** an impact bar shows four headline figures framed around the product's value and rigour (e.g. how fast a complete bracket can be produced, the number of simulated tournaments behind each pick, the scale of the grounded data model, and the test coverage that keeps the numbers honest) rather than incidental facts
- **AND** body sections explain the product's value (the bracket predictor and the group stage), the "You vs. the Model" pool-winning strategy, and why it can be trusted — how it stays grounded (Elo ratings → a Monte Carlo engine → a grounded Analyst) plus the guardrails that keep the AI from inventing or contradicting numbers
- **AND** the page ends with a reflection and a call-to-action whose primary action links to the live app (`https://fifa-wc-bracket.vercel.app/`), with links to the contact section and to the project's GitHub repository (`github.com/LionelKavit/fifa-wc-fantasy`) also present

#### Scenario: Unofficial-project disclaimer is present

- **WHEN** a visitor reads the page
- **THEN** a disclaimer states that the project is an unofficial hobby project, not affiliated with FIFA, and uses original styling with no FIFA logos or imagery

#### Scenario: Accurate, sourced metrics

- **WHEN** the page presents quantitative claims
- **THEN** app-specific figures (e.g. test count, number of product surfaces) match the values documented in the project repository README/docs at publish time
- **AND** tournament/format figures (e.g. 48 teams, 12 groups, 8 best third-placed teams) reflect publicly reported facts about the FIFA World Cup 2026
