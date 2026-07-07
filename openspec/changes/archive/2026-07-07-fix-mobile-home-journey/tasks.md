## 1. Preview setup

- [x] 1.1 Configure `.claude/launch.json` with a static server for the site and start the preview
- [x] 1.2 Open `index.html` at mobile presets (375×812 and a 320px check), capture the baseline distortion

## 2. Homepage hero

- [x] 2.1 In the `@media (max-width: 768px)` block, reset `.hero-content { max-width: 100%; }` and neutralize the absolutely-positioned `.hero-photo` (restack as a block, or hide) so text and photo no longer overlap
- [x] 2.2 Cap or hide the decorative circles `.hero-bg-circle.c1` / `.c2` on mobile so they no longer force horizontal overflow
- [x] 2.3 Re-check the hero at 375px and 320px in preview; confirm single-column stack and no horizontal scroll

## 3. Homepage navigation and sections

- [x] 3.1 Provide a usable mobile navigation affordance (replace the bare `.nav-links { display: none; }`), preferring a CSS-only solution
- [x] 3.2 Verify about, experience, projects grid, blog list, and contact form each collapse to a clean single column at phone widths; add finer breakpoints/resets where a grid still crowds
- [x] 3.3 Confirm no horizontal overflow anywhere on `index.html` at 320–430px

## 4. Journey page

- [x] 4.1 Open `journey_1.html` in mobile preview; identify overflow/distortion in the timeline and background decorations
- [x] 4.2 Ensure the timeline spine, pips, cards, and dual-role rows stack within the viewport; fix any spine/offset overflow
- [x] 4.3 Contain background decorations so they don't cause horizontal scroll; re-verify at 375px and 320px

## 5. Regression and sign-off

- [x] 5.1 View both pages at desktop width (≥769px) in preview; confirm the desktop layout is unchanged
- [x] 5.2 Capture mobile screenshots of both pages as proof the distortion is resolved
