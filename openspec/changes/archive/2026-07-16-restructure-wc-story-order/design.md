## Context

Current order (comment anchors in `project-wc-bracket-analyst.html`): HERO (228) → LIVE SCOREBOARD
(248) → IMPACT BAR (262) → BRACKET PREDICTOR (286, demo video embedded at its end) → POOL-WINNING
STRATEGY (300) → GROUP STAGE (313) → ASK THE ANALYST (330) → WHY YOU CAN TRUST IT (343) → THE
RECEIPTS (394) → REFLECTION (444) → DISCLAIMER (455) → CTA (460).

Target order: HERO → SCOREBOARD → IMPACT BAR → BRACKET PREDICTOR (intro copy only) → DEMO VIDEO →
THE RECEIPTS → REFLECTION → WHY YOU CAN TRUST IT → POOL-WINNING STRATEGY → GROUP STAGE → ASK THE
ANALYST → DISCLAIMER → CTA.

## Goals / Non-Goals

**Goals:** story arc product → proof → person → trust → depth; blocks move intact; divider/reveal
rhythm preserved; receipts stay before reflection (their delta wording made order-agnostic).

**Non-Goals:** no copy rewrites (sibling changes), no CSS changes, no section deletions.

## Decisions

- **Demo video becomes its own beat.** The `.shot` video block currently closes the intro section;
  split it into its own `reveal` block with a short label (e.g. `See it work`) so "what it is" and
  "watch it" are distinct steps in the arc. Rationale: the user's target order names the demo as its
  own position; a labeled beat also gives the receipts a cleaner runway.
- **Move blocks whole, including each section's `<hr class="divider">` seam,** then re-audit the
  divider sequence once at the end (exactly one divider between adjacent sections, none doubled).
- **Reveal animations need no rework** — the IntersectionObserver targets `.reveal` blocks wherever
  they sit in the DOM.
- **Sibling-delta coordination:** `add-wc-receipts` delta's "after the trust/guardrails section"
  phrase is edited to an order-agnostic "between the product/demo sections and the personal
  reflection" so the two deltas don't conflict at archive time.

## Risks / Trade-offs

- **A seam reads abruptly in the new order** (e.g. reflection → trust) → the narrative-saturation
  change owns lead-in lines; this change only guarantees clean structure.
- **Doubled/missing dividers after the move** → explicit end-of-move divider audit task.
- **Regression risk to reveal/lightbox scripts** → none expected (selectors are class-based);
  verified in preview at mobile and desktop.
