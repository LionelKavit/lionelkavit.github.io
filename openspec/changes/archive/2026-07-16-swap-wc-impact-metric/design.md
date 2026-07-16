## Context

The impact bar (`project-wc-bracket-analyst.html`, ~lines 213–232) is a `--pitch-accent` band with a
4-column grid (`.impact-inner`), each `.impact-stat` holding a Lora 2.4rem white `.impact-num` and a
two-line `.impact-label` (with a manual `<br>`). Current stats: `~60s` (speed), `50,000` (simulation
depth), `1,489` (data scale), `287` (test coverage). Mobile (existing 768px block): grid collapses to
`1fr 1fr` 2×2 with adjusted borders — no new mobile plumbing needed, just label-fit verification.

## Goals / Non-Goals

**Goals:**
- Slot 3 tells the "and it was right" story: `4/4` semifinalists called at the real World Cup 2026.
- Zero structural or styling change; the swap is text-only.
- Label fits the established two-line rhythm and the 2×2 mobile grid without clipping.

**Non-Goals:**
- No reordering of the other three stats, no fifth slot, no styling changes.
- No pending claims (champion pick etc.) in the bar — it's the page's most-skimmed surface and must
  never need a retraction.

## Decisions

- **Which slot: `1,489`.** Speed (`~60s`), rigor depth (`50,000` sims), and honesty (`287` tests)
  each carry a distinct argument; data scale is the most redundant (the grounded-model story is told
  in prose and its own section). Alternative — swapping `~60s` — rejected: speed-to-value is the
  product hook.
- **Copy: number `4/4`, label `Semifinalists called —<br>World Cup 2026`.** Reads as a graded result
  with a real-world anchor; matches neighbors' `<br>` two-line pattern. `4/4` keeps the numeral short
  so Lora 2.4rem doesn't crowd the 2×2 mobile cell. If the final is decided before this ships and a
  stronger *decided* claim exists (e.g. champion called), upgrade the copy then — decided results
  only.
- **Consistency with siblings:** this metric also appears in the scoreboard strip
  (`add-wc-live-scoreboard`) — acceptable repetition: the strip is the live ticker, the bar is the
  permanent skim layer. Wording should match between the two so the record is stated one way.

## Risks / Trade-offs

- **Losing the data-scale stat** → the 1,489-player model is still covered in the body prose; nothing
  is deleted from the page's argument, only from the bar.
- **Label wraps to three lines in the 2×2 mobile cell** → verify at 320px; shorten to
  `Semifinalists called<br>WC 2026` if needed.
- **Stat goes stale/gets superseded** → it's a decided historical fact; it can only be upgraded
  (post-final), never falsified.
