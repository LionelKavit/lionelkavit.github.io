## Context

Post-reorder page arc: intro → demo → receipts → reflection → trust → features → CTA. The hero,
scoreboard, receipts, and reflection already carry the story (from `reframe-wc-expert-builder`); the
sections between and after them don't reference it at all. Decided facts available for weaving:
4/4 semifinalists, 2/2 semifinal results, exact final called (Spain vs Argentina), champion pick in
play; QF calls that survived shifted opponents; Norway called into the R16; 12/16 R32 with three
shootout misses.

## Goals / Non-Goals

**Goals:**
- Each content section carries at most one or two story touches — a clause or sentence, not a
  paragraph — so the page reads as one narrative without becoming repetitive chest-thumping.
- Every woven claim maps to a receipts row or the scoreboard; zero new factual territory.
- Seams created by the reorder get a lead-in line so the arc flows (product → proof → person → trust
  → depth).

**Non-Goals:**
- No structural moves (restructure change), no intro rewrite (rewrite-wc-product-intro), no trust
  mechanics rewrite (strengthen-wc-trust-mechanics) — this change only adds their connective tissue
  and light touches, and must not conflict with those rewrites.

## Decisions

- **One-story rule:** each touch references the run from that section's angle — strategy section owns
  the "bold branches survived" angle, group stage owns the third-place-prediction angle, Ask the
  Analyst owns the "same analyst that backed the calls" angle. No two sections repeat the same stat.
- **Weave density:** a clause or a sentence per section. If a section needs more than two sentences
  of story to feel connected, the section copy itself is the problem (flag, don't pad).
- **Tense discipline:** decided results in past tense ("called", "landed"); the champion pick always
  present/"in play" until Sunday.
- **Implementation order:** after `restructure-wc-story-order` and alongside/after the two section
  rewrites, so touches land in final copy, not copy about to be replaced.

## Risks / Trade-offs

- **Bragging fatigue** → the one-story rule and per-section angle ownership keep repetition out;
  receipts stay the single source of numbers.
- **Conflict with the section-rewrite changes** → those changes own their sections' full copy; this
  change contributes only the story clause each rewrite should include (coordination note in each).
- **Champion result lands mid-work** → same post-final flip path as the other changes; no woven line
  may become false on a miss.
