## Context

Source of truth for picks: Kavit's bracket export (`my-bracket (7).csv`) — 31 picks: 16 Round-of-32,
8 Round-of-16, 4 quarterfinals, 2 semifinals, 1 final (champion: Argentina). The bracket is a blend of
the app's model autofill and Kavit's own hand-tweaked picks, and is attributed as such ("my bracket,
built with the Bracket Analyst"), never as the model's pure output.

**Verified results (user-confirmed against the live feed, July 15, 2026).** Grading rule: a pick is ✓
if the picked team advanced from that round, even when the real opponent differed from the predicted
one once the bracket diverged (standard bracket scoring — noted in the section intro).

- **R32 — 12/16.** ✓ Canada, Brazil, France, Norway, Mexico, England, USA, Belgium, Portugal, Spain,
  Argentina, Colombia. ✗ Germany (lost to Paraguay **on penalties**), Netherlands (lost to Morocco
  **on penalties**), Algeria (lost to Switzerland), Australia (lost to Egypt **on penalties**) —
  three of four misses were shootouts.
- **R16 — 5/8.** ✓ France, England, Spain, Belgium, Argentina. ✗ Netherlands (busted — never reached
  the round; Morocco took the slot and beat Canada), Brazil (upset by Norway), Colombia (upset by
  Switzerland).
- **QF — 4/4.** ✓ France (beat Morocco), Spain (beat Belgium), England (beat Norway), Argentina
  (beat Switzerland). Two of these wins came against different opponents than predicted (England drew
  Norway, not Brazil; France drew Morocco, not the Netherlands) — the deep branches survived the
  path shifts, which the intro copy may highlight.
- **SF.** ✓ Spain over France (called as a result). Argentina over England — **in play**.
- **Final / champion.** Argentina — **in play**.

Honesty guard: the R16 Brazil pick is shown as a miss (Norway's upset was NOT predicted — the bracket
picked Brazil). No pick may be retconned. The honest Norway story is: Norway was picked into the R16
(✓), and the England-through-that-quarter call survived Brazil's exit.

Page insertion point: after `<!-- WHY YOU CAN TRUST IT -->` (ends ~line 343) and before
`<!-- REFLECTION -->` (line 344), separated by the page's `.divider` idiom like other sections.

Design tokens available: `.label` (0.7rem uppercase, 0.16em tracking, `--green`), `--border`
hairlines, `--warm-white` card surfaces, `--mono` (DM Mono) for tabular marks, `.disclaimer` idiom
(thin left-accent panel) as a model for the provenance note. The EPL page's mobile leaderboard
(4-column grid rows that reflow at phone widths) is the in-repo precedent for tabular data on mobile.

## Goals / Non-Goals

**Goals:**
- One glanceable section: intro (the record, stated plainly, misses included) → per-round table →
  provenance note → live-app link.
- Honesty rules baked in: ✓/✗ only for decided matches; shootout misses annotated; provenance wording
  matched to actual evidence.
- Mobile: readable one-row-per-pick at 375px; zero page overflow at 320px.

**Non-Goals:**
- No JavaScript, no collapsible/interactive rows (static page; the table is short enough).
- Not a replay of the whole tournament — only the bracket's 31 picks.
- No provenance infrastructure (hash publishing etc.) — that's a future-app concern.

## Decisions

- **Structure: round-grouped rows, not one monolithic table.** Each round gets a small
  `.label`-style subheader (`ROUND OF 32 · 12/16`) followed by rows. The per-round tallies do the
  storytelling; a 31-row undifferentiated table would bury it. Rows use a 3-column grid:
  `pick | result | mark` — the matchup is implicit in pick-vs-result text, keeping columns few for
  mobile.
- **Row anatomy:** pick text (`Norway over Côte d'Ivoire`), result text (`Norway won` /
  `lost on pens` / `in play`), and a DM Mono ✓/✗/– mark right-aligned. Marks: ✓ `--green`,
  ✗ `--text-light` (muted, not red — the page palette has no red and misses aren't shameful),
  – for in-play.
- **Shootout annotation lives in the result cell** (`✗ lost on pens`) so the coin-flip context sits
  exactly where the miss is, per the cohesion pillar.
- **R32 density:** 16 rows is acceptable on desktop; on mobile, rows compress (0.78rem text, tighter
  padding) but stay one-line-per-pick. If a row wraps awkwardly at 320px, truncate team pairs to the
  picked team + opponent abbreviation rather than adding horizontal scroll — prefer reflow, scroll
  only as fallback (matches responsive-layout precedent).
- **Provenance: resolved to the no-lock-claim fallback.** The bracket contains hand-tweaked picks, so
  reproducibility-from-the-repo doesn't apply, and the only artifact is a CSV export whose timestamp
  is neither server-side nor pre-tournament-provable. Therefore the note makes NO "locked before the
  tournament" claim. It states attribution and method honestly: this is Kavit's bracket, built with
  the Bracket Analyst (model autofill plus his own judgment calls), with the record presented as-is
  and a link to the live app so visitors can build their own. Optional forward-looking line: "next
  tournament, the bracket gets published before kickoff." A stronger claim may only be added later if
  real evidence (e.g. a server-side timestamp) turns up.
- **Placement before the reflection** — the reflection can then reference the record ("is it any
  good? — see the receipts above"), giving the page a natural evidence-then-verdict arc.

## Risks / Trade-offs

- **Wrong real-world results embedded in the page** → results are now user-verified (Context above);
  implementation still cross-checks every row against that list before publish.
- **Provenance overclaim** → resolved to the no-lock-claim fallback (see Decisions); any temptation to
  strengthen the claim (or retcon a pick, e.g. Norway-over-Brazil) is explicitly out of bounds — the
  spec requires results to match the bracket export verbatim.
- **16-row R32 feels long on a phone** → per-round tallies let mobile readers skim subheaders;
  density tuned in preview; acceptable because the completeness *is* the credibility.
- **Undecided matches at publish time** → in-play rows ship with a "–" mark and are flipped in the
  same follow-up edits as the scoreboard strip.
- **Desktop regression** → new self-contained section; verify divider rhythm and reflection spacing
  at 1280px.
