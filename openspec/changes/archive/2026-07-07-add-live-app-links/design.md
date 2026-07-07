## Context

The portfolio is a static, hand-authored HTML site on GitHub Pages. Each of the two relevant case-study pages ends with a `.cta` block containing a prompt line and a `.cta-actions` row with a `.btn-ghost` "View on GitHub" link and a `.btn-primary` "Get in touch" link. Each home-page card in the `#projects` grid ends with a single `.project-link` "Read case study" anchor. Both live apps are deployed on Vercel at stable URLs. This change only adds links; there is no new component, asset, or dependency.

## Goals / Non-Goals

**Goals:**
- Make the live app reachable in one click from both the home card and the case-study page, for the two deployed projects.
- Present the live app as the strongest call-to-action on the case-study page without deleting the existing GitHub / contact links.
- Keep the four non-deployed projects' cards untouched.

**Non-Goals:**
- No live embed/iframe of either app.
- No change to the other four project cards or any other page.
- No automated uptime check — if a Vercel app goes down, removing its links is a manual follow-up.

## Decisions

**1. Live link is the primary CTA on the case-study page; GitHub and contact stay.**
Rationale: for someone evaluating the work, "use the actual app" beats "read the code" or "email me." Implement by making the live-app link the `.btn-primary` and demoting "Get in touch" to a `.btn-ghost`, so the row reads **Try the live app** (primary) · **View on GitHub** (ghost) · **Get in touch** (ghost). The `.cta-text` prompt is reworded to invite trying it (e.g. "See it live — or dig into the build."). Alternative considered: adding the live link without re-ranking the buttons — rejected, it buries the strongest action.

**2. Home card gets a second action link, not a replacement.**
Rationale: "Read case study" and "Live app" serve different intents (learn vs. use). Lay them out as two links in the card footer. A small style addition wraps the two in a flex row (`.project-links`) with a gap; the live-app link reuses the `.project-link` look with an external-arrow affordance (`↗`) instead of the internal `→`, signalling it leaves the site. The four cards without a live app keep their single "Read case study" link unchanged.

**3. External-link hygiene.**
Every live-app link uses `target="_blank"` and `rel="noopener noreferrer"`, matching the existing "View on GitHub" links.

**4. Optional hero affordance is out of scope for now.**
A "Launch app" link near the hero or the lead demo video would add prominence, but the CTA (primary) plus the card link already make the app reachable from the top of the funnel (card) and the bottom (CTA). A hero link can be a later enhancement; this change keeps the surface area small.

## Risks / Trade-offs

- **Link rot:** if a Vercel deployment is removed or renamed, the links 404. Mitigation: the URLs are called out here and in tasks for a pre-publish check; removal is a trivial follow-up change.
- **Three actions in one CTA row** could crowd on narrow screens. Mitigation: the existing `.cta` already wraps its actions (`flex-wrap`), and the mobile rule stacks the CTA; verify the three-item row wraps cleanly.

## Migration Plan

1. Update the two case-study page CTAs (add primary live link, demote "Get in touch", reword prompt).
2. Update the two home cards (add the live-app link + the small `.project-links` style).
3. Verify every new link resolves to the correct Vercel URL and opens in a new tab; preview locally.
4. Publish via push (GitHub Pages auto-deploys). Rollback = `git revert`.
