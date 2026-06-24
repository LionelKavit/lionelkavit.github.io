## Context

The portfolio is a static, hand-authored HTML site (no framework, no build) deployed on GitHub Pages at `kavitmehta.blog`. Each project has its own self-contained `.html` page with an inlined `<style>` block, all sharing the same design language: cream background, "pitch-green" accent palette (`--green`, `--pitch`, `--pitch-light`), Lora + DM Sans typography, scroll `.reveal` animations, and a fixed nav. The existing `project-epl-analysis_3_1.html` is the richest of these pages and acts as the de-facto template (hero on a dark pitch background → impact bar → content sections → reflection → CTA).

The replacement subject, **Pocket Scout**, is documented in its GitHub README: an agentic FPL advisor with a two-phase engine (deterministic base analysis + Claude-powered insights), a grounded "Ask The Scout" chat, a constraint-aware transfer optimizer, and an eval-first ranking model (within-position rank correlation improved ~0.33 → 0.53, vs FPL's ~0.59). Stack: Next.js 16, React 19, TypeScript, Tailwind + shadcn, Anthropic Claude (Sonnet, prompt caching), Vitest (331 tests), Docker + Caddy.

## Goals / Non-Goals

**Goals:**
- Present Pocket Scout as a polished case study that visually matches the other four project pages with zero new dependencies.
- Keep the home-page project grid consistent (same card markup contract as the other four cards).
- Make the swap auditable: clear before/after for every touched file.

**Non-Goals:**
- No redesign of the shared design system or other pages.
- No live embed/iframe of the Pocket Scout app, no new screenshots authored in this change (reuse `img-epl.png`; real screenshot is a flagged follow-up).
- No URL redirect from the old path (static host; a 404 on the retired page is acceptable since nothing else links to it).

## Decisions

**1. New filename `project-fpl-advisor.html`, and orphan the old page rather than delete it.**
Rationale: the old filename encodes the wrong subject (`epl-analysis`) and a versioning suffix (`_3_1`), so a clean, descriptive slug is created fresh. The old page is kept on disk but de-linked (no longer reachable via navigation) at the user's request — preserving the prior work without surfacing it. Alternatives considered: (a) overwrite the old file — rejected, the misleading slug would persist and the original would be lost; (b) delete the old file outright — rejected by the user, who prefers to keep it sitting unreferenced.

**2. Reuse the existing page's CSS wholesale, adapt the content.**
Rationale: the EPL page's stylesheet already defines every component we need (hero, `impact-bar`, `arch-grid`, `feature-callout`, `ai-flow`, `reflection`, `cta`, responsive rules). Copy it verbatim and repurpose the semantic blocks. Alternative: trim unused classes — deferred to avoid risk; dead CSS in an inlined block is harmless.

**3. Section mapping (old EPL section → new Pocket Scout section):**
- Hero tag/title/pills → "Agentic AI · Next.js · Claude", thesis line, stack pills.
- Impact bar (4 stats) → `0.53` rank correlation · `331` tests · `10` seasons of data · `2`-phase engine.
- "Sample output" SWOT card → repurposed into a **two-phase engine** explainer using the `ai-flow` three-node layout (Base / Claude Insights / Recommendation).
- Datasets section → **"How it stays grounded"** (FPL API + tool-call chat + deterministic 0–10 model) via `feature-callout`.
- Architecture / arch-grid → **tech stack + architecture** cards (Next.js front end, Claude + prompt caching, eval harness, Docker/Caddy deploy).
- Research-question cards → **eval-first engineering decisions** (ranking-model lift, optimizer over-churn fix, rejected fixture-difficulty upgrade).
- Reflection → Kavit's reflection on building trustworthy, grounded AI.
- CTA → existing "Get in touch" plus a **"View on GitHub"** secondary link to the repo.

**4. Add a "View on GitHub" link in the CTA.**
Rationale: it's a real, browsable repo — linking it strengthens credibility. Implemented with the existing `.btn-primary` style plus a plain text link to avoid new CSS.

## Risks / Trade-offs

- **Reused thumbnail looks generic** → Mitigation: flagged as an explicit follow-up to drop in a real Pocket Scout screenshot; `img-epl.png` is football-themed so it is not jarring in the interim.
- **Orphaned page is still reachable by direct URL** → Accepted: the file is intentionally kept; it is simply unlinked from navigation, so it won't appear in the portfolio's flow but won't 404 either.
- **Metric drift** (README numbers change later) → Mitigation: numbers are sourced from the README at proposal time and called out in tasks for a final accuracy pass before publish.

## Migration Plan

1. Author `project-fpl-advisor.html`.
2. Repoint the home-page card.
3. Confirm no linked page references `project-epl-analysis_3_1.html` or `prompt-flow-graph.png`; leave the old file in place, unlinked.
4. Preview locally, then publish via push (GitHub Pages auto-deploys). Rollback = `git revert` the commit.
