## Why

Two of the showcased projects are now deployed and publicly usable:

- **Pocket Scout — Fantasy Premier League Advisor** → `https://fantasy-premier-league-advisor.vercel.app/`
- **The Bracket Analyst — FIFA World Cup 2026** → `https://fifa-wc-bracket.vercel.app/`

Today a visitor can only read the case study or view the source on GitHub — there's no way to actually *try* the working app. A live link is the single strongest thing a portfolio can offer: it turns "read about it" into "go use it." Both case-study pages already lean on screenshots and a demo video to prove the app is real; a live link lets the visitor confirm it themselves.

## What Changes

- Add a **live-app link** to the closing call-to-action of each of the two case-study pages (`project-fpl-advisor.html`, `project-wc-bracket-analyst.html`), presented as the **primary** action, alongside the existing "View on GitHub" and "Get in touch" links (which stay).
- Add a **"Live app" link** to each of the two projects' home-page cards in the `#projects` grid on `index.html`, next to the existing "Read case study" link (which stays).
- Only the two projects with a deployed app get links. The other four project cards (MSA data agent, Buy-side analyst agent, Process capability, WattBot) are untouched.
- Every live-app link opens in a new tab with `rel="noopener noreferrer"`.

## Capabilities

### New Capabilities
<!-- None: this extends the existing project-showcase capability. -->

### Modified Capabilities
- `project-showcase`: Adds a live-app link contract — the two deployed projects surface a link to their live app from both the home card and the case-study page CTA — and threads it into the home-card contract and the two case-study page-structure requirements.

## Impact

- **Files modified:** `index.html` (two project cards gain a live-app link, plus a small style tweak to lay out two card actions); `project-fpl-advisor.html` and `project-wc-bracket-analyst.html` (closing CTA gains the live-app link as the primary action).
- **No new assets, dependencies, or backend** — static GitHub Pages site served at `kavitmehta.blog`; the live apps are hosted separately on Vercel.
- **External dependency:** the two Vercel URLs must stay live for the links to resolve; if an app is taken down, its links should be removed in a follow-up.
- **Deploy:** goes live on push to the repo's default branch (GitHub Pages).
