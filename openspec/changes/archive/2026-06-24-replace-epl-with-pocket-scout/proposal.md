## Why

The "Premier League Quant Analysis" project is the weakest entry in the portfolio's work section: it is a coursework-style statistical analysis on a static 2023–24 dataset, whereas the rest of the portfolio leans on shipped, agentic AI systems. Kavit has since built **Pocket Scout**, a full-stack agentic FPL advisor (Next.js 16, React 19, Claude with prompt caching, 331 tests, eval-driven ranking model) that is a far stronger demonstration of the "AI you can trust" thesis the site is built around. Swapping it in raises the bar of the showcased work and keeps the narrative consistent.

## What Changes

- Add a new case-study page for **Pocket Scout — Fantasy Premier League Advisor**, reusing the existing project-page design system (pitch-green theme, hero, impact bar, arch cards, reflection, CTA) so it matches the other four project pages.
- Replace the EPL project card on `index.html` (`#projects` grid) — new tag, title, description, thumbnail `alt`, and link — pointing to the new page.
- **Orphan (not delete)** the old page `project-epl-analysis_3_1.html`: the file stays in the repo, but every link to it is removed so it is no longer reachable through the site's navigation. It remains accessible only by direct URL.
- Reuse `images/img-epl.png` as the thumbnail for now (football-themed); flag swapping in a real Pocket Scout screenshot as a follow-up.
- The orphaned `prompt-flow-graph.png` reference (only used by the old EPL page) is removed along with the page.

## Capabilities

### New Capabilities
- `project-showcase`: How project case studies are presented on the site — the home-page project card contract (tag, title, description, thumbnail, link) and the structure/sections a standalone project case-study page must contain.

### Modified Capabilities
<!-- None: no existing OpenSpec specs yet; this is the first capability documented. -->

## Impact

- **Files added:** `project-fpl-advisor.html` (new case-study page).
- **Files modified:** `index.html` (one project card in the `#projects` grid).
- **Files orphaned (kept, de-linked):** `project-epl-analysis_3_1.html` — no longer linked from anywhere, but not deleted.
- **Assets:** `images/img-epl.png` reused as the thumbnail; the `images/fpl-advisor-*.png` screenshots are featured in the new page. `prompt-flow-graph.png` is no longer referenced from any linked page.
- **No build step, dependencies, or backend** affected — static GitHub Pages site served at `kavitmehta.blog`.
- **Deploy:** change goes live on push to the repo's default branch (GitHub Pages).
