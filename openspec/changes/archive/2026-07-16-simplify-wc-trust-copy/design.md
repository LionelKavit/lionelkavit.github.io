## Context

Trust section today: prose (mechanics + form-vs-consistency) → 3-node pipeline diagram → connector
line → 4 guardrail cards. Kavit's feedback: node copy lost him at "zod"/"typed snapshot"/"no I/O";
the four cards are content he doesn't care about. The prose already carries the argument; the
diagram and guardrails are supporting texture and must read at a skim.

## Goals / Non-Goals

**Goals:** every word in the diagram understandable by a non-engineer; guardrails reduced to one
sentence a visitor actually reads; section gets shorter, not longer.

**Non-Goals:** no change to the section's prose paragraphs, heading, or its specced claims (Elo
mechanics, form-vs-consistency, calibration); no removal of the diagram itself.

## Decisions

- **Node copy (drafts, tuned in place):**
  - `Real FIFA data` / "Live standings, fixtures, and results — straight from FIFA's public feed."
  - `The simulation engine` / "Plays the whole tournament out 50,000 times to turn team strength
    into every odd on the page."
  - `The Analyst` / "The AI reads those numbers and explains them — it never invents its own."
  Rationale: each node states what a visitor gets, not how it's built; implementation detail lives
  in the GitHub README the CTA links to.
- **Cards → one line.** Replace the connector + grid with a single closing sentence in the section's
  voice: "And it's governed by one hard rule: if the Analyst can't back an answer with those
  numbers, it says so — it will never invent one to fill the gap." This keeps the archived
  requirements' guardrail idea (grounded, no invention) without the taxonomy.
- **CSS cleanup:** delete `.arch-grid`/`.arch-card`/`.arch-card-icon`/`.arch-card-title`/
  `.arch-card-body` rules and drop `.arch-grid` from the mobile rule; keep the shared
  `.arch-card-body code` selector list entry harmless by leaving the combined `code` rule as-is.

## Risks / Trade-offs

- **Losing nuance (pinned facts, no-contradictions)** → deliberate; the one rule visitors remember
  is grounded-or-declines, and the guardrail detail remains in the repo/docs for anyone who digs.
- **Diagram titles drift from app terminology** → titles describe roles, not UI names; no claims
  change.
