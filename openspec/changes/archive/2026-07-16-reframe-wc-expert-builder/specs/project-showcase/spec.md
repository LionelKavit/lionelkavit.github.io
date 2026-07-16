## RENAMED Requirements

- FROM: `### Requirement: Bracket Analyst narrative leads with the user problem`
- TO: `### Requirement: Bracket Analyst narrative leads with the proven record`

## MODIFIED Requirements

### Requirement: Bracket Analyst narrative leads with the proven record

The Bracket Analyst case-study page SHALL frame its primary narrative as a first-person user success
story: Kavit's own World Cup 2026 bracket — built with the app — whose record is proven in public
(all four semifinalists, both semifinal results called exactly, the exact final called, champion pick
in play), with Kavit credited in the same breath as the builder of the engine behind it. The
upset-watch engine (Elo-grounded odds plus boldness calibrated to pool size and risk appetite) SHALL
be named as the method. The voice MUST be subtle but punchy: only decided results stated as fact, no
self-applied "expert" labels (the record demonstrates expertise), no pre-tournament lock claims, and
no claim of winning a pool. The product's value for bracket-pool players and its groundedness in real
Elo data SHALL remain present as the machinery behind the record, and the narrative MUST remain
truthful without rework whether the champion pick lands or misses.

#### Scenario: Hero leads with the record and the builder

- **WHEN** a visitor reads the hero of `project-wc-bracket-analyst.html`
- **THEN** the headline and opening copy lead with the bracket's decided record and credit Kavit as
  the builder of the engine that produced it
- **AND** the champion pick is framed as in play, not as won

#### Scenario: Voice is demonstrated, not self-labeled

- **WHEN** the page's narrative copy is reviewed
- **THEN** it contains no self-applied "expert" label, no lock claim, and no pool-win claim — every
  factual assertion is a decided result backed by the receipts section

#### Scenario: Upset-watch engine is named

- **WHEN** a visitor reaches the pool-winning strategy section
- **THEN** the upset-watch engine is named there (label and/or copy), connecting the record to the
  boldness-calibration method the page already explains

#### Scenario: Product value and groundedness retained

- **WHEN** a visitor reads the hero and body
- **THEN** they still learn what the app does for a bracket-pool player, with Elo groundedness
  presented as what makes the advice trustworthy

#### Scenario: Narrative survives the final either way

- **WHEN** the final is decided and the page is updated
- **THEN** if the champion pick lands the copy may upgrade to the stronger decided claim, and if it
  misses no previously published narrative statement becomes false

## ADDED Requirements

### Requirement: Bracket Analyst home card tells the success story

The Bracket Analyst card on the home page `#projects` grid SHALL lead its one-paragraph description
with the proven World Cup 2026 record (expert-builder framing) and name the upset-watch method, while
continuing to satisfy the home-page project card contract (tag, title, description, thumbnail, "Read
case study" link, "Live app" link). Only decided results SHALL be stated as fact.

#### Scenario: Card description leads with the record

- **WHEN** a visitor reads the Bracket Analyst card on `index.html`
- **THEN** its description opens with the called record (semifinalists / semifinal results / exact
  final) framed as Kavit's run with the engine he built, mentions the upset-watch method, and states
  no undecided result as fact

#### Scenario: Card contract preserved

- **WHEN** the card is rendered on desktop and at phone widths (320px–430px)
- **THEN** the tag, title, thumbnail, "Read case study" link, and "Live app" link are unchanged and
  the card renders with no overflow, meeting the site's mobile standards
