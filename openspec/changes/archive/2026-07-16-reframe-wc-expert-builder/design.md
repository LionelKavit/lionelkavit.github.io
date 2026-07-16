## Context

Decided facts (web-verified July 15, 2026): Spain 2–0 France; Argentina 2–1 England; final Sunday is
Spain vs Argentina — the bracket's exact predicted final. Bracket record: 12/16 R32 (3 of 4 misses on
pens), 5/8 R16, 4/4 QF, 2/2 semifinal results called exactly, champion pick (Argentina) in play. The
page already carries the live scoreboard strip, the receipts section (with the no-lock-claim
provenance note), and the 4/4 impact stat — this change is purely the surrounding narrative voice.

Current copy being reframed:
- Hero h1: "Fill out a World Cup bracket / like you actually know ball." + product-pitch sub.
- Pool section: label "Pool-winning strategy", callout "You vs. the Model" (the boldness engine —
  differentiation vs chalk, calibrated to pool size — already described but unnamed as "upset watch").
- Reflection: two paragraphs about why he built it.
- Home card: "Your expert friend for a World Cup bracket pool…" (product pitch).

## Goals / Non-Goals

**Goals:**
- Narrative leads with the record as a first-person success story; builder credit lands in the same
  breath ("expert who is also a builder").
- Subtle but punchy voice: short declaratives, numbers as evidence, zero self-applied labels — the
  word "expert" never appears as a self-description; the record demonstrates it.
- "Upset watch" named as the engine's identity in the pool-strategy section.
- Survives Sunday either way: if Argentina wins, copy upgrades; if not, nothing already published
  becomes false (champion consistently framed as in play).

**Non-Goals:**
- No layout/CSS/structural changes; no new sections (scoreboard + receipts already exist).
- No provenance claims in the narrative (receipts note owns that); no pool-win claim (no pool result
  exists); no retconned picks.

## Decisions

- **Hero h1:** `My bracket called the final.<br><em>I built the engine behind it.</em>` — the
  success story and the builder credit in eleven words. Rationale: "called the final" is decided-true
  (matchup called exactly); the italic second line is the page's established em-accent pattern.
- **Hero sub (draft, tuned at implementation):** "All four semifinalists. Both semifinal results. The
  exact final — Spain vs Argentina — with the champion pick still live. Not luck, and not chalk: the
  Bracket Analyst pairs Elo-grounded odds with an upset-watch engine that calculates how bold a
  bracket should be for your pool size and risk appetite. I built it for everyone who picks by flag —
  then trusted it with my own bracket. Receipts below." Rationale: record → method → product value →
  personal stake, no timing claims (provenance stays in the receipts note).
- **Pool section:** label becomes `Upset watch · pool-winning strategy`; first sentence names the
  upset-watch engine explicitly. "You vs. the Model" callout unchanged.
- **Reflection:** append one paragraph closing the loop — built the analyst, became its first proven
  user, receipts one scroll up. Keeps the reflective register (no chest-thumping).
- **Home card description:** "The engine behind my World Cup 2026 run — all four semifinalists, both
  semifinal results, and the exact final called, with the receipts public. Elo-grounded odds plus an
  upset-watch engine that sizes your boldness to your pool, so your bracket stands out for the right
  reasons." Rationale: record first, method second, value close; fits the one-paragraph card contract.
- **Voice guardrails:** never "I am an expert" / "expert analysis by me"; never "champion called"
  before Sunday; never "locked before the tournament"; misses stay acknowledged via the receipts the
  hero points to.

## Risks / Trade-offs

- **Champion pick misses Sunday** → every narrative line is anchored to decided calls; the only edit
  needed is the same post-final flip the scoreboard already plans for.
- **Reads as bragging** → mitigated by the receipts-forward framing (every claim sits one scroll above
  its proof, misses included) and by keeping the product's user-value story intact.
- **Hero h1 shorter than the old one** → visually verify the dark hero still balances at desktop and
  mobile; type scale rules unchanged.
- **"Upset watch" naming drifts from app UI** → it names the boldness engine concept ("You vs. the
  Model" + calibrated risk), which the page already describes; the callout name is untouched.
