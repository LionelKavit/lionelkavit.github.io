## 1. Bring in the screenshots

- [x] 1.1 Copy the five product screenshots from the project repo `docs/images/` into the site's `images/` folder with a `wc-analyst-` prefix: `predictor-hero.png` → `wc-analyst-hero.png`, `build-your-bracket-with-ai.png` → `wc-analyst-autofill.png`, `analyst-bracket.png` → `wc-analyst-chat.png`, `group-dashboard.png` → `wc-analyst-groups.png`, `team-detail.png` → `wc-analyst-team.png`

## 2. Author the Bracket Analyst case-study page

- [x] 2.1 Create `project-wc-bracket-analyst.html` by copying the shared structure/stylesheet from `project-fpl-advisor.html` (nav with "All projects" back link, hero, impact bar, feature callouts, arch grid, framed-screenshot component, reflection, CTA, footer, reveal script)
- [x] 2.2 Write the hero: tag "Agentic AI · Full-Stack · Claude", title "The Bracket Analyst — FIFA World Cup 2026", a value-first thesis line (your expert friend for a bracket pool — grounded in the numbers, not vibes), and technology pills (Next.js 16 · React 19 · TypeScript · Tailwind 4 · Claude · Vitest)
- [x] 2.3 Fill the impact bar with four value/format-framed metrics sourced from the repo docs and publicly reported WC 2026 facts (e.g. 48 teams / 12 groups, the 8 best third-placed teams it untangles, 3 product surfaces, grounded odds never invented) — not internal engineering metrics
- [x] 2.4 Write the value section: the two moments of need (before the deadline vs. during the tournament) and the three product surfaces (Bracket Predictor, Group-stage dashboard, Ask the Analyst)
- [x] 2.5 Write the "You vs. the Model" pool-winning-strategy section (smart differentiation vs. chalk, contrarian payoff calibrated to pool size) using a feature callout
- [x] 2.6 Write the "How it stays grounded" section (FIFA public JSON → Elo-strength Monte Carlo → a grounded Analyst that never invents a number) using a feature callout / flow layout
- [x] 2.7 Write the architecture `arch-grid` cards (pure framework-agnostic TS engine, zod-validated data layer, Elo Monte Carlo engine, grounded LLM Analyst, Next.js UI shell)
- [x] 2.8 Weave in the framed screenshots (rounded border, shadow, pitch-green caption bar) — `wc-analyst-hero` as the lead visual, plus autofill, grounded chat, group dashboard, and team detail — each with a descriptive caption and `alt` text
- [x] 2.9 Write the reflection and set the CTA to include a "View on GitHub" link to `github.com/LionelKavit/fifa-wc-fantasy`
- [x] 2.10 Add the "unofficial hobby project · not affiliated with FIFA · original styling, no FIFA logos/imagery" disclaimer to the page
- [x] 2.11 Set `<title>` and confirm no FPL/Pocket-Scout-specific copy, metrics, or image references remain from the template

## 3. Add the home-page card

- [x] 3.1 Append a sixth card to the `#projects` grid in `index.html`: tag "Agentic AI · Full-Stack · Claude", title "The Bracket Analyst — FIFA World Cup 2026", a value-first one-paragraph description, thumbnail `images/wc-analyst-hero.png` with descriptive `alt`, and a "Read case study" link — with the thumbnail link, title link, and "Read case study" link all pointing to `project-wc-bracket-analyst.html`
- [x] 3.2 Confirm the existing five project cards are unchanged

## 4. Verify

- [x] 4.1 Cross-check every quantitative claim on the new page against the project repo README/docs and publicly reported WC 2026 facts
- [x] 4.2 Preview `project-wc-bracket-analyst.html` and the updated home grid; confirm styling matches the other project pages and all links/images resolve
- [x] 4.3 Run `openspec validate add-wc-bracket-analyst-project --strict`
