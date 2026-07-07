## ADDED Requirements

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
