## Context

Current copy (two paragraphs) opens with the *problem's* mechanics (group-stage survival, third-place
rules) and arrives at the product's outcome late ("export to CSV straight into your pool" is the last
clause). The user's verdict: confusing, weak sentence formation, no wow. The section sits directly
after the impact bar (which already promises "~60s from one chat to a complete, editable bracket")
and directly above the demo beat — so the intro's job is to make those two believable, fast.

## Goals / Non-Goals

**Goals:** outcome-first clarity a stranger gets in two sentences; wow from concrete capability
(a whole 48-team tournament, resolved into an odds-backed bracket in a minute); mechanics repositioned
as handled complexity; sequential interaction loop; punchy short sentences.

**Non-Goals:** no new claims (all capabilities already on the page/README); no length growth (target
equal or shorter than current); no structural/CSS change.

## Decisions

- **Outcome first, complexity second.** Open with what you get; then "here's the monster it tamed"
  (48 teams, 12 groups, the third-place puzzle) as the wow-amplifier; then the loop; then the export
  payoff. Rationale: the current copy inverts this and loses the reader in tournament rules.
- **Draft copy (tuned at implementation, kept to this shape):**
  - h2: `One chat. A complete, odds-backed bracket.`
  - P1: "Tell the Analyst your pool size and how bold you feel, and about a minute later you're
    looking at a complete World Cup bracket — every pick backed by real odds, ready to defend. The
    hard part happens invisibly: 48 teams, 12 groups, and the puzzle of the 8 best third-placed
    teams, all resolved into a filled-in knockout draw before you touch a thing."
  - P2: "From there it's yours. Keep the autofill or overrule it — every matchup shows its real
    head-to-head odds, bold underdogs are flagged as you go. Happy with it? Lock it and export the
    CSV straight into your pool. It's the same autofill that seeded my bracket, graded below."
  - Label stays `The bracket predictor`; final line doubles as the narrative connective (coordinated
    with `saturate-wc-success-narrative`).
- **Sentence discipline:** no sentence carries more than one idea; em-dashes at most one per
  paragraph; numbers stay concrete (48, 12, 8, a minute).

## Risks / Trade-offs

- **Wow drifting into hype** → every clause maps to an existing verified capability; nothing new is
  promised.
- **Duplicating the impact bar's ~60s** → the intro says "about a minute" once, as narrative, not as
  a repeated stat block.
- **Third-place rule lovers lose detail** → the group-stage feature section still explains it fully;
  the intro only needs it as handled complexity.
