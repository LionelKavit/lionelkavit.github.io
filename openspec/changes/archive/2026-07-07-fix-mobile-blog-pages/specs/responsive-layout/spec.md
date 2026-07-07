## ADDED Requirements

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
