## Why

The mobile pages are now free of overflow/distortion (the `fix-mobile-*` changes), but a design-rigor
review against three aesthetic pillars — mobile symmetry, mobile-proportioned type, and component
cohesion — found the pages are not yet uniformly *tuned* for a phone. Measured at 375px and 320px
with the `mobile-design-review` skill:

- **`index.html` type is oversized for a phone.** Hero `h1` renders at **2.8rem** (44.8px) and wraps
  into ~5 stubby lines at ~2.2 words/line; section `h2` renders at **2rem** (32px), wrapping into
  ~4 lines; hero body copy is **1.1rem** with a generous 1.8 line-height, running tall. Desktop
  display sizes are leaking onto the phone.
- The newer project pages (`project-fpl-advisor.html`, `project-buyside-agent_3.html`, etc.) and the
  blog pages are already well-scaled on mobile (hero `h1` ~2rem, `h2` ~1.5rem, body ~1rem) — they
  set the standard `index.html` should match.
- Symmetry passes everywhere sampled (main-column left/right gutters equal), and component cohesion
  passes on the pages sampled (e.g. `index.html` stat number→label gap is a tight 3px).

This change tunes `index.html` (and any other page the review flags) to the mobile type proportions
the rest of the site already achieves, and records the three pillars as an explicit, reviewable
standard so future pages can be held to it. Static HTML/CSS only — no framework.

## What Changes

- Add a `mobile-aesthetics` capability defining the three pillars (symmetry, mobile type scale,
  component cohesion) as the standard every page's phone rendering must meet.
- Tune `index.html` mobile typography inside its `@media (max-width: 768px)` block:
  - Hero `h1`: reduce from ~2.8rem toward ~2.2–2.4rem so it stops wrapping into stubby lines.
  - Section `h2`: reduce from ~2rem toward ~1.7rem.
  - Hero body copy: reduce from ~1.1rem toward ~1.0–1.05rem with line-height ~1.6.
  - Add a finer `@media (max-width: 400px)` step only if 320px still overpowers.
- Verify (and lightly adjust only if the review flags them) the remaining pages against the three
  pillars; confirm symmetry and cohesion hold and that already-well-scaled type is left alone.
- Preserve all content and desktop layout (≥769px unchanged); every edit lives inside a `max-width`
  media query.
- Run the review skill's fix→re-check loop until each touched page passes all three pillars at 375px
  and 320px.

## Capabilities

### New Capabilities
- `mobile-aesthetics`: The phone-rendering design standard — symmetric/balanced content columns,
  type scaled to mobile proportions, and cohesive component grouping — that the site's pages must
  satisfy, verified via the mobile browser preview.

### Modified Capabilities
<!-- None. This is presentation tuning; project-showcase content/structure and the responsive-layout
     overflow guarantees are unchanged. -->

## Impact

- Primary file: `index.html` (embedded `<style>` block, mobile media query only). Other pages touched
  only if the review flags a concrete pillar failure.
- No dependencies, tooling, or JavaScript. Shared design system (palette, fonts) preserved.
- Verification uses the `mobile-design-review` skill against the local mobile preview.
