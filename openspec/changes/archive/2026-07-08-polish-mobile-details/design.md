## Context

Static HTML pages with embedded CSS; each page already has an `@media (max-width: 768px)` block. The
six defects were observed on a real iPhone against the live site. Two are genuine bugs (the arrow bar
and the placeholder overlay); four are alignment/proportion polish.

Root causes confirmed in code:

- **Fix 1** — `.hero-photo img` uses `object-position: center top`; on the 260px mobile crop that shows
  the top of the frame (sky), not the subject who sits lower.
- **Fix 2** — mobile `.hero-stats { gap: 2rem; flex-wrap: wrap }` leaves the three items left-aligned
  and full-width-stacked with large gaps.
- **Fix 3** — `.hero-pills { display:flex; flex-wrap:wrap }` has no `justify-content`, so pills pack to
  the left of the centered mobile column.
- **Fix 4** — `.pipeline` is a 5-node horizontal scroller (`overflow-x:auto`, nodes `min-width:88px`);
  on a phone it clips and reads as broken. Markup connectors are `→ → → ↔` — the `↔` is the odd one.
- **Fix 5** — mobile `.ai-arrow` inherits `align-items:stretch` from `.ai-flow`, so it is full-width;
  `transform: rotate(90deg)` then turns that wide bar into a ~300px-tall vertical strip overlapping the
  cards. `.ai-flow` has `overflow:hidden`, so the rotated bar is clipped into a column down the middle.
- **Fix 6** — `.about-photo-placeholder::before` paints an inline-SVG head+shoulders silhouette on top
  of the real `<img>` (it's absolutely positioned, so it wins the paint order).

## Goals / Non-Goals

**Goals:** each defect resolved at 375px and 320px; desktop (≥769px) unchanged except Fix 6 (the
overlay should not appear on any viewport); no content lost.

**Non-Goals:** no redesign of these components, no framework, no JS, no CSS dedup.

## Decisions

- **Fix 1 — shift the focal point, don't change the image.** Set `.hero-photo img { object-position }`
  toward the bottom on mobile so the subject shows. Exact value tuned in preview (likely `center
  bottom` or a high percentage). Rationale: keeps one image, one file; focal point is the right lever.
- **Fix 2 — centered, compact stat group.** On mobile, center the stats (`text-align:center`, centered
  items) and cut the gap so they occupy far less vertical space. Whether a centered single row or a
  tight centered column reads best is settled in preview against the "compact + centered" goal;
  long labels must stay legible (no 4-line wrapping in a too-narrow column).
- **Fix 3 — center the pills.** Add `justify-content: center` to `.hero-pills` in each project page's
  mobile block. Applies to all 7 project pages for consistency.
- **Fix 4 — fit the pipeline on one row.** On mobile, drop the node `min-width`, let nodes flex to
  share the width, shrink the icon/caption sizes, and keep captions centered under each icon; remove
  the horizontal scroll. Change the `↔` glyph to `→` in markup for uniform connectors. If five full
  nodes with sub-captions are too dense at 320px, hiding the secondary `.pipe-sub` line on mobile is an
  acceptable simplification to keep icons+names on one clean line. Rationale: the user explicitly wants
  a single aligned row, which a scroller doesn't deliver.
- **Fix 5 — stop stretching the arrow before rotating.** On mobile, give `.ai-arrow` `align-self:
  center` (so its box is only glyph-sized) before the 90° rotation, or replace the rotation with a
  centered `↓`. Either way it becomes a small centered down-arrow between the stacked cards instead of
  a full-width bar. Apply to both `project-fpl-advisor.html` and `project-wc-bracket-analyst.html`.
- **Fix 6 — delete the vestigial overlay.** Remove (or neutralize) the `.about-photo-placeholder::before`
  rule entirely. It's a placeholder artifact that shouldn't render on any viewport now that a real
  photo fills the box; removing globally is correct, not just a mobile hide.

## Risks / Trade-offs

- **Pipeline too dense at 320px** → hide `.pipe-sub` and/or reduce icon size; verify captions aren't
  clipped. Horizontal scroll is the fallback only if a clean single row proves unreadable.
- **Changing `↔`→`→` loses the "two-way sync" hint** → acceptable; the user asked for consistent
  connectors, and the write-back is explained in the prose/flow cards below.
- **Hero `object-position` cropping the wrong part** → verify against the actual image in preview at
  both widths; adjust the percentage until face+body show.
- **Desktop regression** → all layout changes stay in `max-width` queries; re-check desktop at 1280px.
  Fix 6 is intentionally global and improves desktop too.
