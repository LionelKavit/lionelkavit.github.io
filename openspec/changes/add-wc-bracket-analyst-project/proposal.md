## Why

The portfolio's work section currently shows five projects. Kavit has since shipped **The Bracket Analyst** (repo: `LionelKavit/fifa-wc-fantasy`), a full-stack agentic advisor for FIFA World Cup 2026 bracket pools: a pure-TypeScript Elo-strength Monte Carlo engine, a grounded "Ask the Analyst" chat, an autofill bracket predictor calibrated to pool size and risk, and a live-aware group-stage dashboard — built spec-first with OpenSpec on Next.js 16 / React 19 / Claude. It is a strong, self-contained demonstration of the same "grounded, agentic AI you can trust" thesis the site is built around, and it complements the existing Pocket Scout FPL case study with a second sports-AI product aimed at a different audience (casual bracket players, not FPL managers). Adding it as a sixth case study strengthens the showcase without displacing anything.

## What Changes

- Add a new case-study page `project-wc-bracket-analyst.html` for **The Bracket Analyst — FIFA World Cup 2026**, reusing the existing project-page design system (pitch-green theme, hero, impact bar, feature callouts, architecture grid, framed screenshots, reflection, CTA) so it matches the other project pages — most closely `project-fpl-advisor.html`, which is used as the template.
- Add a sixth project card to the `#projects` grid on `index.html` (tag, title, one-paragraph description, thumbnail with `alt`, and "Read case study" link), pointing to the new page. The existing five cards are unchanged.
- Copy the product screenshots from the project repo's `docs/images/` into the site's `images/` folder (prefixed `wc-analyst-*`) and feature them in framed containers with captions on the new page.
- Use a real product screenshot (`wc-analyst-hero`, the knockout predictor) as the card thumbnail, rather than a generic reused image.
- Carry the project's disclaimer on the case-study page: it is an unofficial hobby project, not affiliated with FIFA, using original styling and no FIFA logos/imagery.

## Capabilities

### New Capabilities
<!-- None: no new capability. This change extends the existing project-showcase capability. -->

### Modified Capabilities
- `project-showcase`: Extends the home-page project-card contract to cover a sixth card and documents the structure, narrative framing, and annotated-screenshot requirements for the new Bracket Analyst case-study page.

## Impact

- **Files added:** `project-wc-bracket-analyst.html` (new case-study page); `images/wc-analyst-*.png` (screenshots copied from the project repo).
- **Files modified:** `index.html` (one new project card appended to the `#projects` grid; existing cards untouched).
- **Assets:** screenshots sourced from `LionelKavit/fifa-wc-fantasy` `docs/images/` (`predictor-hero`, `build-your-bracket-with-ai`, `analyst-bracket`, `group-dashboard`, `team-detail`).
- **No build step, dependencies, or backend** affected — static GitHub Pages site served at `kavitmehta.blog`.
- **Deploy:** change goes live on push to the repo's default branch (GitHub Pages).
