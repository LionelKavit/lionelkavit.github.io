## Why

The Bracket Analyst pages currently tell a product story: "here's a tool for bracket-pool players."
As of July 15, 2026 there is a stronger, verified story: Kavit's own bracket — built with the app —
has called all four semifinalists, both semifinal results exactly (Spain 2–0 France, Argentina 2–1
England), and the exact final (Spain vs Argentina, Sunday), with the champion pick still live. A
portfolio's most persuasive narrative is a user success story where the user is also the builder:
the analysis proved out in public, and the engine that produced it — Elo-grounded odds plus an
upset-watch/boldness engine that calibrates a bracket's risk to pool size and risk appetite — is
Kavit's own work. The narrative should lead with that record (subtle but punchy: the record does the
talking, no self-applied "expert" labels) while keeping the product value and groundedness story
intact underneath.

## What Changes

- **Reframe the case-study hero** (`project-wc-bracket-analyst.html`): headline and opening copy lead
  with the record-as-story ("my bracket called the final — I built the engine behind it"), naming the
  upset-watch engine as the method; product value (help for pool players) and Elo groundedness remain,
  now as the machinery behind a demonstrated run.
- **Weave "upset watch" into the pool-strategy section** so the engine the record rides on has a name
  on the page.
- **Extend the personal reflection** with the success-story close: builder becomes the tool's first
  proven user, receipts one scroll up.
- **Reframe the home-page card description** (`index.html`): the Bracket Analyst card leads with the
  called record and the expert-builder angle, keeping the card contract and both links intact.
- **Honesty constraints carried over:** only decided results stated as fact; the champion pick is "in
  play" until Sunday; no pre-tournament lock claim anywhere (the receipts note owns provenance); the
  narrative must remain truthful whether the final pick lands or misses.

## Capabilities

### New Capabilities
<!-- None. -->

### Modified Capabilities
- `project-showcase`: The "Bracket Analyst narrative leads with the user problem" requirement is
  renamed and rewritten to lead with the proven record (user-success + expert-builder framing), and a
  new requirement covers the home card's success-story description.

## Impact

- Files: `project-wc-bracket-analyst.html` (hero copy, pool-strategy label/copy, reflection) and
  `index.html` (one card description). Text-only — no layout, CSS, or structural changes.
- Mobile: copy lengths stay comparable, so existing responsive behavior holds; verified at 375px/320px
  regardless (mobile-aesthetics type scale, no overflow).
