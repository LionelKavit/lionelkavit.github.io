## Context

The portfolio is a static, hand-authored HTML site (no framework, no build) deployed on GitHub Pages at `kavitmehta.blog`. Each project has its own self-contained `.html` page with an inlined `<style>` block, all sharing the same design language: cream background, "pitch-green" accent palette, Lora + DM Sans typography, scroll `.reveal` animations, and a fixed nav with an "All projects" back link. `project-fpl-advisor.html` is the newest and richest of these pages — it already defines the components this change needs (hero, `impact-bar`, feature callouts, `arch-grid`, framed-screenshot component with a pitch-green caption bar, reflection, CTA with a "View on GitHub" link) — so it is the de-facto template.

The subject, **The Bracket Analyst**, is documented in its GitHub README and `CLAUDE.md`. It serves casual FIFA World Cup 2026 bracket-pool players at two moments of need: *before the deadline* ("help me fill this out without looking clueless — and maybe win") and *during the tournament* ("is my bracket still alive?"). It has three product surfaces — a **Bracket Predictor** (autofill + per-pick odds + CSV export), a **Group-stage dashboard** (12 groups, live-aware standings, Next-Round %, the 8 best third-placed teams), and **Ask the Analyst** (a grounded chat). Under the hood: FIFA public JSON → a data layer (fetch + validate + normalize with zod) → a pure, framework-agnostic TypeScript engine (standings, verdicts, Elo-strength Monte Carlo, knockout bracket + odds + pool-finish) → a grounding layer → the grounded LLM Analyst → a Next.js UI. Stack: TypeScript, Next.js 16 (App Router), React 19, Tailwind CSS 4, Vitest, zod, `@anthropic-ai/sdk` (`claude-sonnet-4-6`).

## Goals / Non-Goals

**Goals:**
- Present The Bracket Analyst as a polished sixth case study that visually matches the existing project pages with zero new dependencies.
- Keep the home-page project grid consistent (same card markup contract as the other cards) and additive (existing five cards unchanged).
- Lead the narrative with the user problem and the value delivered (pick guidance, pool-winning strategy), with groundedness framed as the reliability feature — mirroring the Pocket Scout page's framing.
- Feature real product screenshots, not just prose.

**Non-Goals:**
- No redesign of the shared design system or any existing page.
- No live embed/iframe of the app.
- No replacement or removal of any existing project (this is purely additive).
- No consolidation of the per-project `project-showcase` requirements into generic shared ones — the spec deliberately keeps a Bracket-Analyst-scoped set, matching the precedent set by the Pocket Scout change.

## Decisions

**1. New descriptive filename `project-wc-bracket-analyst.html`.**
Rationale: matches the site's convention of descriptive project slugs (`project-fpl-advisor.html`, `project-wattbot_2.html`). "wc-bracket-analyst" reads clearly and avoids tying the slug to a single tournament year in the URL more than necessary.

**2. Use `project-fpl-advisor.html` as the structural/CSS template, not the older EPL page.**
Rationale: the FPL page is the most recent, already contains the framed-screenshot component and the "View on GitHub" CTA, and shares the exact narrative framing this project wants (value-first, groundedness-as-reliability). Copy its stylesheet wholesale and repurpose the semantic blocks. Dead CSS in an inlined block is harmless.

**3. Copy screenshots into the site repo rather than hotlinking GitHub.**
Rationale: the site is self-contained and offline-deployable on GitHub Pages; hotlinking `raw.githubusercontent.com` is fragile. Copy the five `docs/images/*.png` into `images/` with a `wc-analyst-` prefix. The README's demo is a GitHub-hosted video asset (not a file in the repo); the lead visual on the case study is therefore the framed `predictor-hero` screenshot, not a video. (Embedding a downloaded demo video is a possible follow-up, not part of this change.)

**4. Section mapping (Bracket Analyst → template blocks):**
- Hero tag/title/pills → "Agentic AI · Full-Stack · Claude", a thesis line ("your expert friend for a World Cup bracket pool — grounded in the numbers, not vibes"), and stack pills (Next.js 16 · React 19 · TypeScript · Tailwind 4 · Claude · Vitest).
- Impact bar (4 stats) → framed around the problem/value and the format it demystifies, using publicly reported WC 2026 facts and product facts (e.g. 48 teams / 12 groups, the 8 best third-placed teams it untangles, 3 product surfaces, grounded odds that are never invented). Any engineering figure (e.g. test count) is verified against the repo before publish.
- Value section → the "two moments of need" (before the deadline vs. during the tournament) and the three surfaces.
- "You vs. the Model" → the pool-winning-strategy feature callout (smart differentiation vs. chalk, contrarian payoff calibrated to pool size).
- "How it stays grounded" → FIFA public JSON → Elo-strength Monte Carlo → a grounded Analyst that never makes up a number, via a feature callout / flow layout.
- Architecture `arch-grid` → the pure TS engine, the zod-validated data layer, the Monte Carlo engine, the grounded LLM Analyst, and the Next.js UI shell.
- Screenshots → framed containers with captions, one per key surface.
- Reflection → Kavit's reflection on building grounded, trustworthy AI for casual users.
- CTA → existing "Get in touch" plus a "View on GitHub" link to `github.com/LionelKavit/fifa-wc-fantasy`.

**5. Card thumbnail is a real screenshot.**
Rationale: the earlier FPL card reused a generic football image and flagged a real screenshot as follow-up. Here a real product screenshot (`wc-analyst-hero`, the knockout predictor) exists, so use it directly for a stronger, honest preview.

**6. Carry the "unofficial / not affiliated with FIFA" disclaimer on the page.**
Rationale: the project README is explicit that it is an unofficial hobby project reading FIFA's undocumented public JSON, using original styling only (no FIFA logos or imagery). Reproducing that disclaimer on the case study is honest and low-cost.

## Risks / Trade-offs

- **Metric drift / unsourced numbers** → Mitigation: impact-bar and body figures are drawn from the repo README/docs and publicly reported WC 2026 facts at proposal time, with a final accuracy pass called out in tasks before publish.
- **Two sports-AI case studies could feel repetitive** → Mitigation: the copy deliberately differentiates the audiences (casual bracket players vs. FPL managers) and the engines (Elo Monte Carlo tournament simulation vs. player-level FPL ratings).
- **Screenshots may age** as the app evolves → Accepted: they are a point-in-time snapshot, consistent with how the other project pages treat their screenshots.

## Migration Plan

1. Copy `docs/images/*.png` from the project repo into `images/` as `wc-analyst-*.png`.
2. Author `project-wc-bracket-analyst.html` from the `project-fpl-advisor.html` template.
3. Append the new card to the `#projects` grid in `index.html` (existing cards untouched).
4. Cross-check every quantitative claim against the repo; preview locally; then publish via push (GitHub Pages auto-deploys). Rollback = `git revert` the commit.
