## ADDED Requirements

### Requirement: Project case-study pages render correctly on mobile

Each project case-study page — `project-fpl-advisor.html`, `project-wc-bracket-analyst.html`, `project-msa-data-agent_3.html`, `project-buyside-agent_3.html`, `project-wattbot_2.html`, `project-process-capability_2.html`, and `project-epl-analysis_3_1.html` — SHALL render without horizontal overflow or distortion across mobile viewport widths (320px–430px). Multi-column content grids SHALL collapse to a single readable column (or otherwise remain legible) at phone widths; fixed pixel-column rows and tabular rows SHALL adapt (fluid columns, wrapping, or horizontal scroll contained within their own element) rather than widening the page; and horizontal step flows SHALL stack or scroll within a contained region. Hero titles, technology pills, impact-bar metrics, screenshot captions, and the closing call-to-action SHALL remain legible and within the viewport. All existing content, images, and links SHALL be preserved, and desktop rendering at widths ≥769px SHALL be unchanged.

#### Scenario: No horizontal overflow on a phone

- **WHEN** any of the seven project pages is viewed at a viewport width between 320px and 430px
- **THEN** the page does not scroll horizontally (document width does not exceed the viewport width)
- **AND** the hero background, technology pills, content grids, tabular rows, and step flows all stay within the viewport

#### Scenario: Content grids collapse cleanly

- **WHEN** a project page's content grids (e.g. impact bar, architecture/eval/problem grids) are viewed at a phone width (~375px)
- **THEN** they render as a single readable column, or a two-up layout only where it remains comfortably legible, with no clipped or overlapping content

#### Scenario: Fixed-column and tabular rows adapt

- **WHEN** a fixed pixel-column row (e.g. `.spec-row`, `.dec-row`, `.llm-node-row`) or a tabular row (e.g. the leaderboard rows on `project-epl-analysis_3_1.html`) is viewed at a phone width
- **THEN** it adapts by reflowing, wrapping, or scrolling within its own container
- **AND** it does not force the page to scroll horizontally

#### Scenario: Horizontal step flows contained

- **WHEN** a horizontal step flow (e.g. `.ai-flow`, `.pipeline`) is viewed at a phone width
- **THEN** it stacks vertically or scrolls inside a contained region, rather than widening the page

#### Scenario: Content and links preserved

- **WHEN** a project page is compared before and after the change
- **THEN** all copy, images, captions, and links (case study, live app, GitHub, contact) are still present and functional

#### Scenario: Desktop layout is preserved

- **WHEN** any project page is viewed at a desktop width (≥769px)
- **THEN** the layout matches the pre-change desktop design
