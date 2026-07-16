## Context

`.hero-pills` sits at the end of `.hero-inner`; `.pill` styling is tuned for the dark hero
(`rgba(255,255,255,…)` background/border/text). Target position is inside `.content`, after the Ask
the Analyst section and before `<!-- DISCLAIMER -->` — a cream surface. The mobile block centers
`.hero-pills` via `justify-content: center`.

## Goals / Non-Goals

**Goals:** pills read as a quiet "built with" footnote at the bottom; legible on cream; hero loses
its last jargon; mobile centering preserved.

**Non-Goals:** no pill content changes; no hero layout rework beyond removing the block; no changes
to other sections.

## Decisions

- **Labeled beat, not a bare row.** The page's idiom is label + content; a floating pill row would
  look orphaned. New block: `<div class="reveal tech-stack">` with `.label` "Built with" + the
  existing `.hero-pills` div, preceded by a `divider` after Ask the Analyst (disclaimer keeps its own
  top margin).
- **Light-surface variant via wrapper scope:** `.tech-stack .pill { background:
  rgba(45,107,45,0.05); border-color: var(--border); color: var(--text-light); }` — same shape and
  size, page-palette colors. The base `.pill` rule stays (harmless if unused on dark).
- **Hero spacing:** `.hero-sub` carries `margin-bottom: 3rem` sized for the pills below it; reduce to
  ~0.5rem-equivalent visual gap if the hero bottom looks hollow after removal (judge in preview).
- **Mobile:** the existing `.hero-pills { justify-content: center; }` mobile rule targets the class,
  which moves with the block — centering carries over automatically.

## Risks / Trade-offs

- **Hero feels empty at the bottom** → tune `.hero-sub` bottom margin in preview.
- **Pills too faint on cream** → contrast-check `--text-light` at 0.74rem; darken to `--text-mid` if
  needed.
