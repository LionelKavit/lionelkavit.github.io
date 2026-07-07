## 1. Case-study page CTAs

- [x] 1.1 In `project-fpl-advisor.html`, add a live-app link to `https://fantasy-premier-league-advisor.vercel.app/` in the closing `.cta` as the `.btn-primary` action, demote "Get in touch" to `.btn-ghost`, keep "View on GitHub", and reword the `.cta-text` prompt to invite trying it live. Link uses `target="_blank"` + `rel="noopener noreferrer"`.
- [x] 1.2 In `project-wc-bracket-analyst.html`, add a live-app link to `https://fifa-wc-bracket.vercel.app/` in the closing `.cta` as the `.btn-primary` action, demote "Get in touch" to `.btn-ghost`, keep "View on GitHub", and reword the `.cta-text` prompt. Link uses `target="_blank"` + `rel="noopener noreferrer"`.

## 2. Home-page cards

- [x] 2.1 Add a small `.project-links` style to `index.html` that lays out two card actions in a row, and a live-app link variant with an external `↗` affordance.
- [x] 2.2 In the Pocket Scout card, add a "Live app" link to `https://fantasy-premier-league-advisor.vercel.app/` next to "Read case study" (new tab, `rel="noopener noreferrer"`); keep "Read case study" pointing to `project-fpl-advisor.html`.
- [x] 2.3 In the Bracket Analyst card, add a "Live app" link to `https://fifa-wc-bracket.vercel.app/` next to "Read case study" (new tab, `rel="noopener noreferrer"`); keep "Read case study" pointing to `project-wc-bracket-analyst.html`.
- [x] 2.4 Confirm the four cards without a live app (MSA data agent, Buy-side analyst agent, Process capability, WattBot) are unchanged — still a single "Read case study" link.

## 3. Verify

- [x] 3.1 Preview all three pages; confirm every live-app link resolves to the correct Vercel URL, opens in a new tab, and the CTA row / card footers lay out cleanly (including narrow widths).
- [x] 3.2 Run `openspec validate add-live-app-links --strict`.
