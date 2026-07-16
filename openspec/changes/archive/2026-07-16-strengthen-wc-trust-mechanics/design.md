## Context

Verified from the repository README (fetched July 15, 2026): the engine is "Elo-strength Monte Carlo,
knockout bracket + odds + pool-finish" — win-probability simulation with **no goal-count modeling**;
risk/pool settings "calibrate the risk to your pool size — so you stand out enough to win without
blowing it up" — i.e. **pick differentiation**, not match simulation. Kavit's proposed goal-based
explanation is therefore not shippable as-is; he was corrected and the rewrite draws its strength
from the true mechanics plus his upset-watch thesis (stored in memory), whose defensible core is
form (short-term, loud) vs consistency (long-term, what Elo measures).

Current copy: one dense paragraph ("The math is real; the AI can't fake it") + flow diagram + one
connector line + four guardrail cards. The paragraph explains *that* it simulates, not *how a winner
is decided* or *why that beats punditry*.

## Goals / Non-Goals

**Goals:** a reader finishes the section able to explain how one matchup gets decided; the
form-vs-consistency argument lands with the Spain/Argentina receipts as evidence; every mechanical
claim survives a README check.

**Non-Goals:** no diagram/card restructuring; no new engine capabilities implied; no thesis claims
that outrun decided results (champion pick stays in play).

## Decisions

- **Explain one matchup before 50,000 tournaments.** Draft shape: "Take one matchup. The engine
  turns the two teams' Elo gap into a win probability — nothing else, no vibes, no narratives — and
  draws the result from it. Now play the whole tournament that way, 50,000 times, and you get every
  standing, knockout odd, and pool verdict on this page." Concrete → scale → output.
- **Form vs consistency as the punchline, receipts as proof.** Draft: "This is also why the model
  kept faith with Spain and Argentina while the form narrative crowned France and England. Form is
  the last three games; Elo is years of results. Consistency beat form in both semifinals — and the
  receipts above were written before the pundits caught up." Tense check: decided facts only.
- **Correct the calibration sentence.** Boldness (pool size, risk appetite) selects which underdogs
  are worth backing given the differentiation payoff — it never touches how a match is simulated.
  One sentence, placed after the mechanics so the two ideas can't blur.
- **Goal-stat framing is out.** No "predicts goals per team", no minute-level stat claims. If Kavit
  later ships and documents goal modeling, this section can be upgraded then (noted as a follow-up,
  gated on docs).
- **Heading may sharpen** (e.g. `Consistency you can compute.` / keep `The math is real; the AI
  can't fake it.` as fallback) — settled at implementation.

## Risks / Trade-offs

- **Thesis framing drifting into punditry** → the section only claims what Elo mathematically is
  (long-run rating) plus receipts-decided outcomes; no "Spain were flawless" style match narration.
- **Reader wants goal-level depth we can't claim** → the guardrail cards' "grounded or it declines"
  already frames the honest boundary; the copy leans into it as a feature.
- **README drift** → implementation task re-checks the README the day it ships.
