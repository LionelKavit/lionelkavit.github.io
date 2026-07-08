## ADDED Requirements

### Requirement: Home hero photo shows the subject on mobile

On mobile viewport widths, the home page hero photo SHALL be framed so the subject's face and body are
visible, rather than cropping them out by showing the top of the image. Desktop rendering at ≥769px
SHALL be unchanged.

#### Scenario: Subject is visible in the mobile hero crop

- **WHEN** `index.html` is viewed at 375px and 320px
- **THEN** the hero photo's focal point shows the subject's face and body (not just sky/background)

### Requirement: Home hero stats are centered and compact on mobile

The home page hero statistics SHALL be center-aligned and grouped compactly on mobile viewport widths,
rather than left-aligned and spread across excessive vertical space. Desktop rendering at ≥769px SHALL
be unchanged.

#### Scenario: Stats read as a centered, compact group

- **WHEN** the hero stats are viewed at 375px and 320px
- **THEN** each stat's number and label are center-aligned
- **AND** the group occupies noticeably less vertical space than three far-apart full-width rows

### Requirement: Project tech-stack pills are centered on mobile

On mobile viewport widths, the technology pills in each project case-study hero (`.hero-pills`) SHALL be
center-aligned within the column. Desktop rendering at ≥769px SHALL be unchanged.

#### Scenario: Pills are centered

- **WHEN** any `project-*.html` hero is viewed at 375px and 320px
- **THEN** the tech-stack pills are centered as a group rather than packed to the left edge

### Requirement: MSA metadata pipeline aligns on one row on mobile

On mobile viewport widths, the MSA "end-to-end metadata pipeline" SHALL render as a single horizontal
row: the step icons on one line, a connector between each pair of icons, and each icon's caption
center-aligned directly below its icon, with no clipped text. All connectors SHALL use a consistent
arrow (`→`) rather than mixing `→` with `↔`. Desktop rendering at ≥769px SHALL be unchanged.

#### Scenario: Pipeline is a clean single row

- **WHEN** `project-msa-data-agent_3.html`'s pipeline is viewed at 375px and 320px
- **THEN** the icons sit on one line with a connector between each pair and captions centered below
- **AND** no caption or icon is clipped, and the page does not scroll horizontally because of it

#### Scenario: Connectors are consistent

- **WHEN** the pipeline connectors are rendered
- **THEN** every connector between nodes is `→` (the previous `↔` between SharePoint and Copilot Agent
  is replaced for uniformity)

### Requirement: Infographic flow arrows do not overlap the cards on mobile

The phase-flow connector arrows (`.ai-arrow`) on the Pocket Scout and Bracket Analyst pages SHALL render
as a small centered down-arrow between the stacked flow cards on mobile, and SHALL NOT render as a
full-width bar that overlaps or blocks the flow cards. Desktop rendering at ≥769px SHALL be unchanged.

#### Scenario: Arrows sit between cards, not over them

- **WHEN** the phase-flow infographic on `project-fpl-advisor.html` and `project-wc-bracket-analyst.html`
  is viewed at 375px and 320px
- **THEN** each connector is a small centered down-arrow between two stacked cards
- **AND** no arrow forms a vertical bar overlapping the card content

### Requirement: About photo has no placeholder overlay

The About section graduation photo on `index.html` SHALL render without the vestigial person-silhouette
placeholder icon overlaid on it. The placeholder overlay SHALL NOT appear on any viewport.

#### Scenario: No silhouette over the About photo

- **WHEN** the About section is viewed at any width
- **THEN** the real photo is shown unobstructed, with no gray person-shaped placeholder icon on top of it
