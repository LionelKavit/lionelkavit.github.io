## 1. Author the Pocket Scout case-study page

- [x] 1.1 Create `project-fpl-advisor.html` by copying the shared structure/stylesheet from `project-epl-analysis_3_1.html` (nav, hero, impact bar, content, reflection, CTA, footer, reveal script)
- [x] 1.2 Write the hero: tag "Agentic AI · Next.js · Claude", title conveying "grounded in real data, not vibes", sub-paragraph, and technology pills (Next.js 16 · React 19 · TypeScript · Claude · Vitest · FPL API)
- [x] 1.3 Fill the impact bar with four metrics: `0.53` within-position rank correlation (vs FPL's 0.59), `331` automated tests, `10` seasons of training data, `2`-phase engine
- [x] 1.4 Write the "two-phase engine" section using the `ai-flow` three-node layout (deterministic base analysis → Claude insights → personalized recommendation)
- [x] 1.5 Write the "how it stays grounded" section (public FPL API, tool-call chat that refuses to invent stats, deterministic 0–10 ratings) using `feature-callout`
- [x] 1.6 Write the tech-stack / architecture `arch-grid` cards (front end, Claude + prompt caching, eval harness, Docker + Caddy deploy)
- [x] 1.7 Write the "eval-first engineering decisions" section (ranking-model lift 0.33→0.53, optimizer over-churn fixed with hold gates, rejected fixture-difficulty upgrade)
- [x] 1.8 Add a framed screenshot component (rounded border, shadow, pitch-green caption bar) and weave in the `images/fpl-advisor-*.png` screenshots: dashboard hero as lead visual, grounded chat, This Week/Long Term/Chips planner, player dialog, and demo mode — each with descriptive caption + `alt`
- [x] 1.9 Write the reflection and update the CTA to include a "View on GitHub" link to the Pocket Scout repo
- [x] 1.10 Set `<title>` and ensure no EPL-specific markup remains (SWOT card, leaderboard, quadrants, dataset, research-question, prompt-flow image)

## 2. Repoint the home page

- [x] 2.1 In `index.html` `#projects` grid, replace the EPL card's tag, title (×2 links), description, thumbnail `alt`, and all three `href`s to point at `project-fpl-advisor.html`

## 3. Orphan the old project

- [x] 3.1 Leave `project-epl-analysis_3_1.html` in place (do NOT delete) — it stays as an unlinked file
- [x] 3.2 Grep the repo to confirm no remaining links to `project-epl-analysis_3_1.html`, and that `prompt-flow-graph.png` is only referenced by that orphaned page (if at all)

## 4. Verify

- [x] 4.1 Cross-check every quantitative claim on the new page against the Pocket Scout README
- [x] 4.2 Preview `project-fpl-advisor.html` and the updated home card; confirm styling matches the other project pages and links resolve
- [x] 4.3 Run `openspec validate replace-epl-with-pocket-scout --strict`
