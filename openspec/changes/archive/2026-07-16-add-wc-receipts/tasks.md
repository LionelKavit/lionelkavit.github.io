## 1. Gather inputs (resolved — see design.md Context/Decisions)

- [x] 1.1 Results confirmed against the live feed: R32 12/16 (✗ Germany, Netherlands, Australia — all on pens — and Algeria), R16 5/8 (✗ Netherlands busted, Brazil upset by Norway, Colombia upset by Switzerland), QF 4/4, SF Spain ✓ / Argentina in play, final in play
- [x] 1.2 Attribution/provenance resolved: hand-tweaked bracket built with the app; no pre-tournament lock evidence → no-lock-claim wording; no retconned picks (Brazil R16 stays a miss)

## 2. Build the section

- [x] 2.1 Add the receipts section markup after "Why you can trust it" and before the reflection, using the page's `.label` + `.divider` idiom; intro paragraph states the record plainly, misses included — may highlight the honest resilience angles (Norway picked into the R16; England-through-that-quarter survived Brazil's exit; QF calls won against shifted opponents)
- [x] 2.2 Add round-grouped rows (`pick | result | mark` grid) from the verified scorecard in design.md, per-round tally subheaders (`ROUND OF 32 · 12/16`, `ROUND OF 16 · 5/8`, `QUARTERFINALS · 4/4`, `SEMIFINALS · 1/1 decided`), DM Mono ✓/✗/– marks (✓ green, ✗ muted, – in-play), "lost on pens" annotations on the Germany, Netherlands, and Australia rows
- [x] 2.3 Add the provenance note as a `.disclaimer`-style panel: Kavit's bracket built with the app (autofill + judgment tweaks), record as-is, no lock claim, live-app link; optional "next tournament the bracket gets published before kickoff" line

## 3. Mobile

- [x] 3.1 In the existing `@media (max-width: 768px)` block: compress rows (~0.78rem, tighter padding), keep one line per pick, marks attached to rows
- [x] 3.2 Verify at 375px and 320px: no horizontal overflow; if a row wraps awkwardly at 320px, shorten pick text rather than adding scroll

## 4. Verify

- [x] 4.1 Desktop (≥1280px): section rhythm matches neighbors; reflection unchanged below it
- [x] 4.2 Cross-check every ✓/✗ against the verified scorecard in design.md; confirm no undecided match is graded and no pick deviates from the CSV export
- [x] 4.3 Screenshot mobile + desktop as proof

## 5. Follow-up edits (after real matches)

- [ ] 5.1 After England vs Argentina and after the final: flip the in-play rows and update the per-round tallies
