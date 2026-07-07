## ADDED Requirements

### Requirement: Mobile content is symmetric and balanced

On mobile viewport widths (320px–430px) every page's main content column SHALL be balanced within the
viewport — left and right gutters approximately equal — rather than retaining a desktop asymmetry
(e.g. a column hugging one edge with dead space on the other). Desktop multi-column layouts SHALL
collapse to a single centered/balanced stack, and section eyebrows, headings, and body SHALL share a
consistent, deliberate horizontal alignment. Desktop rendering at ≥769px SHALL be unchanged.

#### Scenario: Main column gutters are balanced

- **WHEN** a page's primary content column is measured at 375px and 320px
- **THEN** its left and right gutters differ by no more than ~4px
- **AND** no major section is pinned to one side with a large empty band on the other

#### Scenario: Alignment is consistent within a section

- **WHEN** a section's eyebrow, heading, and body are viewed at a phone width
- **THEN** they share one deliberate alignment (all to the same gutter, or all centered), not a mix
  that reads as accidental

### Requirement: Type is scaled to mobile proportions

On mobile viewport widths every page's typography SHALL be sized for a small screen rather than
inheriting desktop display sizes. Headings SHALL scale down more than body copy (display type is what
most overpowers a phone). No heading SHALL wrap into four or more stubby lines, and body copy SHALL
average at least five words per line. These overrides SHALL live inside `max-width` media queries so
desktop type at ≥769px is unchanged.

#### Scenario: Heading and body sizes fit mobile ranges

- **WHEN** a page is measured at 375px
- **THEN** the hero `h1` is roughly 2rem–2.6rem, section `h2` roughly 1.5rem–1.9rem, and body copy
  roughly 0.95rem–1.05rem with line-height roughly 1.5–1.65

#### Scenario: No oversized heading wrap

- **WHEN** a hero or section heading is rendered at 375px and 320px
- **THEN** it does not wrap into four or more short lines, and body paragraphs average at least five
  words per line

#### Scenario: Already-scaled type is left alone

- **WHEN** a page already measures within the mobile type ranges
- **THEN** its type is not further shrunk (avoiding an over-tuning regression)

### Requirement: Components read as cohesive groups

On mobile viewport widths, elements that belong to one component SHALL be grouped by proximity so the
grouping is legible: the space within a component (e.g. a stat's number and its label, a bullet and
its text, a card's title and body) SHALL be visibly smaller than the space to the next separate
component. Buttons or controls that act on a panel SHALL sit adjacent to it, and related controls that
stack on mobile SHALL stay visually tied. Desktop rendering at ≥769px SHALL be unchanged.

#### Scenario: Proximity encodes grouping

- **WHEN** a grouped pair (number+label, bullet+text, icon+text) is measured at a phone width
- **THEN** the intra-group gap is clearly smaller than the gap to the next separate component

#### Scenario: Related controls stay tied

- **WHEN** a set of related controls (e.g. a call-to-action's buttons) stacks on mobile
- **THEN** they remain visually connected (small, consistent gap; shared alignment or width) rather
  than drifting apart

### Requirement: Index page meets the mobile aesthetic pillars

The home page `index.html` SHALL satisfy all three pillars (symmetry, mobile type scale, component
cohesion) at 375px and 320px. In particular its previously oversized hero `h1` (~2.8rem), section
`h2` (~2rem), and hero body copy (~1.1rem) SHALL be tuned to the mobile ranges so the hero heading no
longer wraps into stubby lines, converging on the proportions the site's project and blog pages
already use.

#### Scenario: Index hero and section type are mobile-proportioned

- **WHEN** `index.html` is measured at 375px
- **THEN** the hero `h1` is within ~2rem–2.6rem and no longer wraps into five short lines
- **AND** section `h2` is within ~1.5rem–1.9rem
- **AND** hero body copy is within ~0.95rem–1.05rem at line-height ~1.5–1.65

#### Scenario: Index remains symmetric and cohesive

- **WHEN** `index.html` is reviewed at 375px and 320px after tuning
- **THEN** the main content column gutters remain balanced (≤~4px difference)
- **AND** grouped elements (e.g. stat number/label, CTA buttons) remain cohesive
- **AND** the desktop layout at ≥769px is unchanged
