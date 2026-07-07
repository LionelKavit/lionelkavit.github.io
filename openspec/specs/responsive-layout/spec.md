# responsive-layout Specification

## Purpose
TBD - created by archiving change fix-mobile-home-journey. Update Purpose after archive.
## Requirements
### Requirement: Homepage renders correctly on mobile

The homepage `index.html` SHALL render without horizontal overflow or overlapping/distorted elements across mobile viewport widths (320px–430px). Desktop multi-column layouts SHALL collapse to a single-column stack at phone widths, the hero SHALL NOT retain its desktop two-column text/photo split, and fixed-size decorative elements SHALL NOT extend the page beyond the viewport. All primary navigation destinations SHALL remain reachable on mobile. Content SHALL remain legible and interactive targets usable. Desktop rendering at widths ≥769px SHALL be unchanged.

#### Scenario: No horizontal overflow on a phone

- **WHEN** `index.html` is viewed at a viewport width between 320px and 430px
- **THEN** the page does not scroll horizontally (document width does not exceed the viewport width)
- **AND** no decorative element (e.g. `.hero-bg-circle`) forces the page wider than the viewport

#### Scenario: Hero stacks into a single column

- **WHEN** the hero is viewed at a phone width (~375px)
- **THEN** the heading, subheading, and any hero stats occupy the full content width in a single column
- **AND** the hero photo does not overlap the hero text (it is restacked as a block or hidden), rather than sitting absolutely positioned beside a 58%-width text column

#### Scenario: Navigation is reachable on mobile

- **WHEN** a visitor views `index.html` at a phone width
- **THEN** the site's primary navigation destinations are reachable (via a visible menu affordance or an adapted nav), rather than the nav links being hidden with no replacement

#### Scenario: Section grids collapse cleanly

- **WHEN** the about, experience, projects, blog, and contact sections are viewed at a phone width
- **THEN** their multi-column grids and form rows render as a single readable column with content fully within the viewport

#### Scenario: Desktop layout is preserved

- **WHEN** `index.html` is viewed at a desktop width (≥769px)
- **THEN** the layout matches the pre-change desktop design (two-column hero, multi-column grids intact)

### Requirement: Journey page renders correctly on mobile

The journey page `journey_1.html` SHALL render without horizontal overflow or distortion across mobile viewport widths (320px–430px). The timeline (spine, pips, cards, and dual-role rows) SHALL stack cleanly within the viewport, and background decorations SHALL NOT cause horizontal scrolling. Desktop rendering at widths ≥769px SHALL be unchanged.

#### Scenario: Timeline fits within the viewport

- **WHEN** `journey_1.html` is viewed at a phone width (~375px)
- **THEN** the timeline spine, pips, and cards remain within the viewport with no horizontal scroll
- **AND** dual-role entries stack vertically rather than sitting side by side

#### Scenario: Background decorations do not overflow

- **WHEN** the page is viewed at a phone width
- **THEN** decorative background elements do not extend the page beyond the viewport width

#### Scenario: Desktop layout is preserved

- **WHEN** `journey_1.html` is viewed at a desktop width (≥769px)
- **THEN** the timeline renders in its original desktop layout

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

### Requirement: Blog and essay pages render correctly on mobile

Each blog/essay page — `blog-kalsubai.html`, `blog-atthai.html`, `blog-drama-club.html`, and `blog-comics-for-change.html` — SHALL render without horizontal overflow or distortion across mobile viewport widths (320px–430px). The article/sidebar layout SHALL stack into a single column; over-dense grids (notably `.days-grid` on `blog-atthai.html`) SHALL collapse to a legible column count; photo galleries, mosaics, hero images, and hero-overlay elements SHALL stay within the viewport; and the top navigation links SHALL wrap or adapt gracefully rather than overflowing. All existing content, images, and links SHALL be preserved, and desktop rendering at widths ≥769px SHALL be unchanged.

#### Scenario: No horizontal overflow on a phone

- **WHEN** any of the four blog pages is viewed at a viewport width between 320px and 430px
- **THEN** the page does not scroll horizontally (document width does not exceed the viewport width)
- **AND** hero images/overlays, galleries, mosaics, and any wide media stay within the viewport

#### Scenario: Article and sidebar stack

- **WHEN** a blog page's `.blog-content-wrap` is viewed at a phone width (~375px)
- **THEN** the article body and sidebar render as a single readable column with the sidebar below the article

#### Scenario: Dense grids collapse to a legible count

- **WHEN** `blog-atthai.html`'s `.days-grid` (and any similarly dense grid on the other blogs) is viewed at a phone width
- **THEN** it renders with a legible number of columns (not four cramped columns) and content is not clipped

#### Scenario: Navigation adapts at narrow widths

- **WHEN** the top navigation is viewed at a phone width
- **THEN** the nav links wrap or adapt so they remain usable and do not overflow the viewport

#### Scenario: Galleries and hero overlays contained

- **WHEN** a photo gallery/mosaic or a hero image with overlay text/badges is viewed at a phone width
- **THEN** images are fluid (`max-width: 100%`), and overlay text/badges stay within the image without clipping or overlap

#### Scenario: Content and links preserved

- **WHEN** a blog page is compared before and after the change
- **THEN** all copy, images, captions, and links (footer nav, back links) are still present and functional

#### Scenario: Desktop layout is preserved

- **WHEN** any blog page is viewed at a desktop width (≥769px)
- **THEN** the layout matches the pre-change desktop design

