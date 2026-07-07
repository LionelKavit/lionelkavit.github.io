## Context

The site is 13 hand-written static HTML pages; each embeds its CSS in a single `<style>` block. Pages already declare `<meta name="viewport" content="width=device-width, initial-scale=1.0">` and a `@media (max-width: 768px)` block, so the responsive scaffolding exists — it is just incomplete. Distortion comes from desktop-only rules that the mobile block never overrides.

Confirmed gaps on the two pages in scope:

- **`index.html` hero** (`index.html:76`–`129`): `.hero-content { max-width: 58%; }`, `.hero-photo { position: absolute; width: 42%; }`, and decorative circles `.hero-bg-circle.c1 { width: 600px; height: 600px; right: -100px; }` / `.c2 { width: 300px; height: 300px; right: 300px; }`. The mobile block at `index.html:870` resets padding and some grids but never touches these, so on a phone the text sits in 58% width with an overlapping photo and the circles push horizontal overflow.
- **`index.html` nav** (`index.html:872`): `.nav-links { display: none; }` on mobile with no replacement — there is no way to reach in-page sections from a phone.
- **`journey_1.html`**: mobile block only shifts padding, the timeline spine `left`, and stacks `.tl-dual-roles`. The absolute spine + card offsets and background decorations need checking at ~375px for overflow.

## Goals / Non-Goals

**Goals:**
- Both pages render with no horizontal overflow and no overlapping/distorted elements at 320–430px.
- Desktop multi-column layouts collapse to a clean single-column stack on phones.
- A usable navigation affordance exists on mobile for the homepage.
- Desktop layout (≥769px) is unchanged.

**Non-Goals:**
- No framework, TypeScript, build step, or new dependency.
- No content/copy rewrites, no redesign — only responsive layout correctness.
- No CSS deduplication across files (a separate future concern); fixes stay inline per page.
- Other pages (projects, blogs) are handled in sibling changes.

## Decisions

- **Fix in the existing `@media (max-width: 768px)` block, add finer breakpoints only if needed.** Rationale: matches the site's established pattern; a 480px or 380px breakpoint is added only where a two-up grid still crowds (e.g. metric grids). Alternative — a full mobile-first rewrite of each stylesheet — rejected as far more invasive for a portfolio and higher regression risk.
- **Hero photo: restack, don't just hide.** On mobile, take `.hero-photo` out of absolute positioning and render it as a normal block above or below the copy (or hide it if stacking harms the composition), and reset `.hero-content { max-width: 100%; }`. Rationale: keeps the visitor's photo visible rather than discarding it; avoids the overlap.
- **Decorative circles: cap or hide on mobile.** Shrink and/or reposition `.c1`/`.c2` so they stay within the viewport, or set `overflow` containment / `display: none` at phone widths. They are opacity ~0.05–0.08 background flourishes, so hiding them on small screens is visually safe.
- **Mobile nav: lightweight, no JS if avoidable.** Prefer showing the nav links as a simple wrapped/inline row or an always-visible compact set rather than a JS hamburger, to honor the "no added JS" goal. A minimal CSS-only disclosure is acceptable if a plain wrapped row looks poor. Decision finalized during preview iteration.
- **Verify in a real mobile viewport.** Use the browser preview at mobile presets (375×812 and a 320px check) and inspect for overflow, rather than reasoning from CSS alone.

## Risks / Trade-offs

- **Restacking the hero may need a small HTML/markup tweak** (e.g. source order) → keep any markup change minimal and confirm desktop is visually identical afterward.
- **Hiding decorative circles changes the mobile aesthetic slightly** → acceptable; they are subtle background elements, and correctness outweighs the flourish on small screens.
- **Regression on desktop** → all new rules live inside `max-width` media queries, so ≥769px is untouched; verify desktop once after changes.
- **A CSS-only mobile nav may be less slick than a JS menu** → acceptable trade for zero added JS; revisit only if unusable.
