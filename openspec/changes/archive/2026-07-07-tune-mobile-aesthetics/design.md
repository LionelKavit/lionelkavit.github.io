## Context

The site's pages embed their CSS in one `<style>` block and already carry an
`@media (max-width: 768px)` block. The `fix-mobile-*` changes removed overflow/distortion; this
change is purely aesthetic tuning of the phone rendering, driven by the `mobile-design-review` skill
and its three pillars.

Baseline measured at 375px (via the skill's `references/measure.md` scanner):

| Page | hero h1 | h2 | body | verdict |
|---|---|---|---|---|
| `index.html` | 2.8rem (44.8px), 2.2 wpl | 2rem (32px) | 1.1rem / lh 1.8 | **type too big** |
| `project-fpl-advisor.html` | 2rem, 2.3 wpl | 1.5rem | 1rem / 7.1 wpl | good |
| `project-buyside-agent_3.html` | 2rem, 3 wpl | 1.5rem | 1rem | good |
| `blog-atthai.html` | 2.2rem, 3.5 wpl | — | 1.05rem / 6.8 wpl | good |
| `journey_1.html` | 2.4rem (short title, no bad wrap) | — | 0.97rem | borderline-fine |

Symmetry passed on every page sampled (main-column left/right gutters equal, diff 0). Cohesion passed
on `index.html` (stat number→label 3px, tight; CTA buttons paired). So the work is concentrated on
`index.html` type, with the other pages already embodying the target proportions.

## Goals / Non-Goals

**Goals:**
- `index.html` mobile type matches the proportions the rest of the site already achieves: hero `h1`
  ~2.2–2.4rem, `h2` ~1.7rem, body ~1.0–1.05rem at line-height ~1.6, with no heading wrapping into
  4+ stubby lines and body ≥5 words/line.
- The three pillars are recorded as a reusable standard (the `mobile-aesthetics` spec) so future
  pages can be reviewed against them.
- Symmetry and cohesion confirmed to hold on every touched page.
- Desktop (≥769px) unchanged.

**Non-Goals:**
- No framework, TypeScript, build step, or JavaScript.
- No copy/content edits, no redesign, no CSS deduplication.
- Do **not** shrink type that already measures in range (the project/blog pages) — over-tuning is a
  regression too.

## Decisions

- **Tune inside the existing `@media (max-width: 768px)` block; add `@media (max-width: 400px)` only
  if 320px specifically still overpowers.** Rationale: matches the site pattern, keeps desktop
  untouched, and avoids a second breakpoint unless the numbers demand it.
- **Target the proportions the good pages already use, not arbitrary values.** `index.html` should
  converge on the fpl/blog scale rather than a number picked in isolation — consistency across the
  site is the real goal. Alternative (a global shared type scale) is out of scope here (no CSS
  dedup) but noted as a future option.
- **Let the review loop, not a single guess, settle the exact rem values.** Set an initial value,
  reload, re-measure `wpl`/sizes, and adjust. Design values rarely land first try; the skill's loop
  is the mechanism.
- **Leave well-scaled pages alone.** The scanner is the gate: a page is touched only if a pillar
  concretely fails on it. This prevents "tuning" from degrading pages that already pass.

## Risks / Trade-offs

- **Over-shrinking type** → text that's too small to read comfortably. Mitigation: hold body ≥
  ~0.95rem and hero `h1` ≥ ~2rem; verify words-per-line stays in the 6–10 band, not higher.
- **A fix escaping its media query and moving desktop** → keep every rule inside `max-width` queries
  and re-check desktop at 1280px after edits.
- **Chasing the preview's screenshot crop artifact** → judge type/gutters by DOM measurement
  (`clientWidth`, `getBoundingClientRect`, computed `font-size`), using screenshots only for feel.
- **Scope creep across 13 pages** → the scanner keeps this honest; only `index.html` is expected to
  need real edits.
