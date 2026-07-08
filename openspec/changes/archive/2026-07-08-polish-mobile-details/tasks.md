## 1. index.html — hero photo, stats, About overlay

- [x] 1.1 (Fix 1) In the mobile block, set `.hero-photo img { object-position }` toward the bottom so the subject's face/body show; tune the value in preview at 375px and 320px
- [x] 1.2 (Fix 2) Center-align `.hero-stats` on mobile (centered items + `text-align:center`) and reduce the gap so the group is compact; verify labels stay legible
- [x] 1.3 (Fix 6) Remove the `.about-photo-placeholder::before` placeholder-silhouette rule so the About photo is unobstructed

## 2. Project pages — pill centering (Fix 3)

- [x] 2.1 Add `.hero-pills { justify-content: center; }` to the mobile block of all 7 `project-*.html` pages

## 3. MSA pipeline (Fix 4)

- [x] 3.1 Change the `↔` connector between SharePoint and Copilot Agent to `→` in the markup
- [x] 3.2 In the mobile block, make `.pipeline` a single non-scrolling row: drop node `min-width`, let nodes flex, shrink icon/caption sizes, keep captions centered under icons; hide `.pipe-sub` on mobile if needed to fit
- [x] 3.3 Verify at 375px and 320px: icons on one line, `→` between each, captions centered and unclipped, no horizontal scroll

## 4. Infographic arrows (Fix 5)

- [x] 4.1 In `project-fpl-advisor.html`, fix the mobile `.ai-arrow` so it is a small centered down-arrow (give it `align-self:center` before rotation, or use a centered `↓`) instead of a full-width rotated bar
- [x] 4.2 Apply the same fix to `project-wc-bracket-analyst.html`
- [x] 4.3 Verify the arrows no longer overlap the flow cards at 375px and 320px

## 5. Regression and sign-off

- [x] 5.1 View index, MSA, FPL, and WC at desktop width (≥769px); confirm desktop layout unchanged
- [x] 5.2 Confirm no horizontal overflow and all content/links preserved on the touched pages
- [x] 5.3 Capture mobile screenshots of each fixed area as proof
