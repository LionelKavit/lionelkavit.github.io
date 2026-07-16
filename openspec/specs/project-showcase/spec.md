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

### Requirement: Bracket Analyst case-study page structure

The Bracket Analyst case-study page SHALL reuse the shared design system (pitch-green palette, Lora +
DM Sans typography, fixed nav with an "All projects" back link, scroll-reveal animations) and SHALL
present its content in a storytelling order: a hero with category tag, title, and technology pills;
the live scoreboard strip; an impact bar of four headline metrics; then body sections in this order —
**(1)** what the app is (the bracket predictor intro), **(2)** the demo video as its own beat,
**(3)** the public grading of Kavit's bracket (the receipts), **(4)** the personal reflection,
**(5)** why it can be trusted (how it stays grounded plus the guardrails that govern the AI's
behaviour), **(6)** the app's feature sections (pool-winning strategy / upset watch, the group stage,
and Ask the Analyst) — followed by the unofficial-project disclaimer and a closing call-to-action
whose primary action links to the live app (see the Live application links requirement). The page
SHALL also carry a disclaimer that it is an unofficial hobby project, not affiliated with FIFA, using
original styling and no FIFA logos or imagery.

#### Scenario: Page matches the storytelling order

- **WHEN** a visitor opens `project-wc-bracket-analyst.html`
- **THEN** the page renders a dark "pitch" hero with technology pills, the live scoreboard strip, and
  an impact bar of four headline figures framed around the product's value and rigour (e.g. how fast
  a complete bracket can be produced, the simulations behind each pick, the verified tournament
  record, and the test coverage that keeps the numbers honest)
- **AND** the body reads product → proof → person → trust → depth: the bracket-predictor intro, then
  the demo video, then the receipts, then the reflection, then the trust/guardrails section (Elo
  ratings → a Monte Carlo engine → a grounded Analyst), then the feature sections (pool-winning
  strategy / upset watch, group stage, Ask the Analyst)
- **AND** the page ends with the disclaimer and a call-to-action whose primary action links to the
  live app (`https://fifa-wc-bracket.vercel.app/`), with links to the contact section and to the
  project's GitHub repository (`github.com/LionelKavit/fifa-wc-fantasy`) also present

#### Scenario: Section moves preserve rendering integrity

- **WHEN** the reordered page is viewed at phone widths (320px–430px) and at desktop (≥769px)
- **THEN** every section renders as before the move (scroll-reveal, dividers exactly one between
  adjacent sections, no overflow), with only the order changed

#### Scenario: Unofficial-project disclaimer is present

- **WHEN** a visitor reads the page
- **THEN** a disclaimer states that the project is an unofficial hobby project, not affiliated with
  FIFA, and uses original styling with no FIFA logos or imagery

#### Scenario: Accurate, sourced metrics

- **WHEN** the page presents quantitative claims
- **THEN** app-specific figures (e.g. test count, number of product surfaces) match the values
  documented in the project repository README/docs at publish time
- **AND** tournament/format figures (e.g. 48 teams, 12 groups, 8 best third-placed teams) reflect
  publicly reported facts about the FIFA World Cup 2026

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

### Requirement: Live tournament scoreboard strip

The Bracket Analyst case-study page SHALL display a slim scoreboard strip between the hero and the
impact bar summarizing the app's real-World Cup 2026 prediction record. The strip SHALL contain an
uppercase label (`LIVE · WORLD CUP 2026` while the tournament is ongoing, switching to a
permanent-record label after the final), three to four short result pills, and an "as of <date>"
stamp. Each pill SHALL carry exactly one of three visual states — correct (✓), missed (✗), or
in play — and only results already decided in the real tournament SHALL be marked ✓ or ✗; undecided
picks MUST be shown as in play. The strip SHALL reuse the page's existing design system (pitch
palette, DM Sans label typography, established pill idiom) and SHALL introduce no JavaScript.

#### Scenario: Strip summarizes the record at a glance

- **WHEN** a visitor loads `project-wc-bracket-analyst.html` during the tournament
- **THEN** a strip appears directly below the hero and above the impact bar with the `LIVE · WORLD
  CUP 2026` label, result pills (e.g. `✓ 4/4 semifinalists called`, `✓ Spain over France — called`,
  `Final pick: Argentina — in play`), and an "as of" date stamp

#### Scenario: Only decided results are claimed

- **WHEN** a pick's real-world match has not yet been played
- **THEN** its pill renders in the in-play state and is not presented as correct or missed

#### Scenario: Strip flips to a permanent record after the final

- **WHEN** the tournament ends and the page is updated
- **THEN** the label reads as a final-record variant (e.g. `FINAL RECORD · WORLD CUP 2026`) with the
  same strip structure and updated pill states, without structural rework

#### Scenario: Strip is mobile-clean

- **WHEN** the strip is viewed at viewport widths between 320px and 430px
- **THEN** the pills wrap onto multiple centered rows with no horizontal overflow, the label and
  date stamp stack legibly, and pill text renders at a mobile-appropriate size (roughly 0.7–0.8rem)
- **AND** spacing within a pill is visibly tighter than spacing between pills

#### Scenario: Desktop layout is preserved

- **WHEN** the page is viewed at a desktop width (≥769px)
- **THEN** the hero and impact bar render as before, with the strip forming a continuous dark band
  between them and no other section shifted

### Requirement: Prediction receipts section

The Bracket Analyst case-study page SHALL include a "receipts" section presenting the bracket's
predicted-vs-actual record for World Cup 2026, placed before the personal reflection at the position
the page-structure requirement assigns it in the narrative order. The section SHALL group picks by round with a per-round tally, showing for
each pick the prediction, the real result, and a correct/missed/in-play mark. Misses decided by
penalty shootouts SHALL be annotated as such. The section SHALL state the overall record honestly —
including the misses — and every displayed pick MUST match the bracket export verbatim: no pick may
be altered, added, or reframed after its real-world result is known. The section SHALL include a
provenance note that attributes the bracket accurately (Kavit's bracket, built with the app — model
autofill plus hand-tweaked picks) and, because no pre-tournament lock evidence exists, makes no
locked-before-kickoff claim, plus a link to the live app. Real-world results MUST match the
user-verified scorecard; undecided matches MUST be marked in play rather than correct or missed. The
section SHALL reuse the page's existing design system and introduce no JavaScript. The section's
on-page title SHALL NOT use the internal "receipts" name; it SHALL present the bracket's identity —
a balanced-risk bracket built for a 50-person pool (settings per Kavit, user-verified) — so a neutral
fan can identify with it, with the intro noting that this balanced philosophy showed most from the
quarterfinals onward. On-page cross-references from other sections SHALL match this public framing
rather than the internal name.

#### Scenario: Round-grouped record with tallies

- **WHEN** a visitor reads the receipts section
- **THEN** picks are grouped by round (Round of 32 through Final), each round headed by its tally
  (e.g. `ROUND OF 32 · 12/16`), with one row per pick showing prediction, result, and a ✓/✗/– mark

#### Scenario: Shootout misses are annotated

- **WHEN** a missed pick was decided by a penalty shootout
- **THEN** its result cell carries a "lost on pens" (or equivalent) annotation alongside the ✗ mark

#### Scenario: Provenance is claimed only as strongly as the evidence

- **WHEN** the provenance note is rendered
- **THEN** it attributes the bracket as Kavit's own, built with the app (model autofill plus
  hand-tweaked picks), makes no locked-before-kickoff claim (no verifiable pre-tournament evidence
  exists), and links the live app

#### Scenario: No pick is retconned

- **WHEN** any pick's displayed value is compared against the bracket export (`my-bracket (7).csv`)
- **THEN** they match exactly — in particular the Round-of-16 Brazil pick is shown as a miss (upset
  by Norway), and no after-the-fact "hand-tweak" pick appears anywhere in the section

#### Scenario: Undecided picks are not graded

- **WHEN** a pick's real-world match has not been played at publish time
- **THEN** its row shows an in-play mark and is updated only after the match is decided

#### Scenario: Section is mobile-clean

- **WHEN** the section is viewed at viewport widths between 320px and 430px
- **THEN** every row reflows to remain readable with no horizontal page overflow, round subheaders
  remain scannable, and the marks stay visually attached to their rows

#### Scenario: Desktop layout is preserved

- **WHEN** the page is viewed at a desktop width (≥769px)
- **THEN** the new section follows the page's existing section rhythm (labels, dividers, spacing)
  and no other section is altered

### Requirement: Impact bar carries a verified tournament-truth metric

The Bracket Analyst impact bar SHALL include a metric stating the app's verified real-World Cup 2026
prediction record (initially `4/4` semifinalists called), replacing the data-scale stat (`1,489`
players/teams) in the third slot. The bar SHALL retain exactly four stats and its existing styling
and structure. The tournament-truth metric MUST state only results already decided in the real
tournament, MAY be upgraded to a stronger decided claim after later rounds conclude, and SHALL use
the same wording for the record as the page's scoreboard strip.

#### Scenario: Third slot shows the tournament record

- **WHEN** a visitor views the impact bar on `project-wc-bracket-analyst.html`
- **THEN** the third stat reads `4/4` with a label identifying it as semifinalists called at World
  Cup 2026, and the `~60s`, `50,000`, and `287` stats are unchanged

#### Scenario: Only decided results appear in the bar

- **WHEN** the metric's underlying claim is chosen or later upgraded
- **THEN** it reflects only matches already decided in the real tournament, never a pending pick

#### Scenario: Metric fits the mobile grid

- **WHEN** the impact bar is viewed at viewport widths between 320px and 430px
- **THEN** the bar's existing 2×2 mobile grid renders the new number and label without clipping or
  overflow, with the label wrapping consistently with the sibling stat labels (which wrap to 4–5
  short lines at phone widths)

#### Scenario: Desktop layout is preserved

- **WHEN** the page is viewed at a desktop width (≥769px)
- **THEN** the impact bar renders four stats in its existing four-column layout with unchanged
  styling

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

### Requirement: Success-story narrative threads through all content sections

Every content section of the Bracket Analyst case-study page SHALL carry the user-success narrative
where appropriate to that section's subject — a brief story touch connecting the section's capability
to Kavit's World Cup 2026 run — so the page reads as one continuous story in the order product →
proof → person → trust → depth. Each woven claim MUST correspond to a decided result shown in the
receipts or scoreboard; the champion pick MUST remain framed as in play until decided; and no section
may repeat another section's stat or contradict the receipts. Sections joined abruptly by the
storytelling reorder SHALL receive a transitional lead-in. The voice guardrails of the proven-record
narrative requirement (no self-applied "expert" label, no lock claims, no pool-win claims) apply to
every woven line.

#### Scenario: Each section carries its own story angle

- **WHEN** a visitor reads the pool-winning strategy, group stage, and Ask the Analyst sections
- **THEN** each contains a brief, section-appropriate reference to the run (e.g. strategy → bold
  branches that survived shifted paths; group stage → how the predicted groups resolved; chat → the
  same grounded analyst behind the calls), with no stat repeated across sections

#### Scenario: Woven claims trace to the receipts

- **WHEN** any story touch makes a factual claim
- **THEN** that claim matches a decided result in the receipts or scoreboard, and no touch states the
  champion pick as won before the final is decided

#### Scenario: Reordered seams read smoothly

- **WHEN** a visitor crosses a seam created by the storytelling reorder (e.g. reflection into trust)
- **THEN** a transitional line carries the narrative across the seam rather than an abrupt topic jump

#### Scenario: Text-only and mobile-safe

- **WHEN** the woven copy renders at phone widths (320px–430px) and desktop
- **THEN** no layout, overflow, or type-scale regressions are introduced (copy-only change)

### Requirement: Product intro is outcome-first and unambiguous

The bracket-predictor intro section of the Bracket Analyst case-study page SHALL communicate, in
order: (1) what the app produces — a complete, editable World Cup bracket with real odds behind every
pick, ready for a pool, in about a minute; (2) the tournament complexity the engine handles invisibly
(48 teams, 12 groups, the 8 best third-placed teams) framed as handled-for-you, not as prerequisite
reading; (3) the interaction loop — autofill calibrated to pool size and risk appetite, edit with
real head-to-head odds and flagged underdogs, lock, export CSV to the pool. A reader with no World
Cup-format knowledge MUST understand what the product is from the first two sentences. Sentences
SHALL carry one idea each, and the section MUST NOT grow beyond its current length. All stated
capabilities MUST already be documented (page or repository README) — no new claims.

#### Scenario: A stranger gets it in two sentences

- **WHEN** a reader unfamiliar with World Cup formats reads the section's first two sentences
- **THEN** they can say what the app produces and roughly how fast, without needing the group-stage
  rules explained first

#### Scenario: Complexity reads as wow, not homework

- **WHEN** the reader reaches the 48-team/12-group/third-place material
- **THEN** it is framed as work the engine already did for them, after the outcome has been stated

#### Scenario: The loop reads in order

- **WHEN** the reader finishes the section
- **THEN** they know the sequence autofill → edit with odds and upset flags → lock → export CSV, and
  the demo beat below follows naturally

#### Scenario: No inflation

- **WHEN** the new copy is compared to the app's documented capabilities and the page's other claims
- **THEN** every stated capability already exists and no stat contradicts the impact bar or receipts

#### Scenario: Mobile-safe copy

- **WHEN** the section renders at 320px–430px
- **THEN** the copy wraps cleanly with no overflow or type-scale regressions (text-only change)

### Requirement: Receipts rows are outcome color-coded

The receipts table rows on the Bracket Analyst case-study page SHALL be color-coded by outcome:
**green** for every correct pick (any row whose picked team advanced from that round, including rows
where the predicted opponent path broke but the picked winner still advanced), **red** for every
wrong pick (including busted picks whose team was already out and shootout losses), and **black
(neutral dark)** for undecided rows. The coloring SHALL apply to the row's mark and text treatment
consistently on desktop and mobile, remain legible at phone-width text sizes on the section's
background, and use a red that sits within the page's muted palette. This supersedes the earlier
muted-miss visual treatment; the underlying grading logic is unchanged.

#### Scenario: Correct picks are green — including shifted-path wins

- **WHEN** a visitor scans rows like `Spain over Austria` or `England over Brazil` (won its
  quarterfinal against Norway after Brazil's exit)
- **THEN** both render green as correct picks

#### Scenario: Wrong picks are red — including busted picks

- **WHEN** a visitor scans rows like `Germany over Paraguay` (lost on pens), `Netherlands over
  Canada` (picked team already out), or `Brazil over Norway` (upset)
- **THEN** all render red as wrong picks

#### Scenario: Undecided rows are black until graded

- **WHEN** a row's match has not been decided (currently the final/champion row)
- **THEN** it renders in the neutral dark treatment, turning green or red only after the result

#### Scenario: Legible at phone widths

- **WHEN** the table renders at 320px–430px
- **THEN** all three colors remain distinguishable and readable at the table's mobile text size, with
  no other layout change

### Requirement: Trust section explains true decision mechanics

The "Why you can trust it" section of the Bracket Analyst case-study page SHALL explain concretely
how a matchup is decided — the two teams' Elo-derived win probability, played out across 50,000
simulated tournaments to produce standings, knockout odds, and pool verdicts — and SHALL frame the
model's edge as consistency versus form: Elo encodes long-run results where pundit narratives chase
recent form, evidenced only by decided, receipts-backed outcomes (the model's faith in Spain and
Argentina against the form-favored France and England). The section SHALL state the role of pool size
and risk appetite correctly as pick-boldness calibration (which underdogs are worth backing for
differentiation), never as part of match simulation. The section MUST NOT claim goal-count prediction
or any per-stat capability not documented by the application's repository, and every mechanical claim
MUST be consistent with the repository README at publish time. The pipeline diagram and guardrail
cards remain.

#### Scenario: A reader can explain one matchup

- **WHEN** a visitor finishes the section's opening copy
- **THEN** they can state how a single matchup is decided (Elo gap → win probability → simulated
  outcome) before the 50,000-tournament scale is invoked

#### Scenario: Form vs consistency lands on decided facts

- **WHEN** the section makes the consistency-over-form argument
- **THEN** it cites only decided results the receipts show (semifinal outcomes), keeps the champion
  pick in play, and avoids match-narration claims (no "flawless"/"dominant" assertions)

#### Scenario: Calibration is attributed correctly

- **WHEN** the section mentions pool size or risk appetite
- **THEN** they are described as calibrating pick boldness/differentiation only, distinctly separate
  from how matches are simulated

#### Scenario: No undocumented mechanics

- **WHEN** the section's mechanical claims are compared against the repository README
- **THEN** every claim is supported, and no goal-count or minute-level stat prediction is asserted
  anywhere in the section

#### Scenario: Mobile-safe copy

- **WHEN** the section renders at 320px–430px and desktop
- **THEN** the rewritten copy introduces no overflow or type-scale regressions (text-only; diagram
  and cards unchanged)

