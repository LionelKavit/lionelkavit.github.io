## Why

The portfolio's homepage (`index.html`) and journey page (`journey_1.html`) render distorted on mobile. Both carry a `viewport` meta tag and a `@media (max-width: 768px)` block, but those blocks are incomplete: desktop-only layout rules survive into the mobile view. On the homepage the hero keeps its two-column `58% text / 42% absolutely-positioned photo` split and its fixed `600px`/`300px` decorative circles, so on a phone the headline is crammed beside an overlapping photo and content bleeds off-screen. The journey timeline's absolute spine and dual-role rows are only partially adapted. These are the first pages a visitor lands on, so the distortion is the most damaging.

This is a CSS-completeness problem, not an architecture problem — the fix is to finish the responsive rules, keeping the current static HTML/CSS. No framework or language change.

## What Changes

- Complete the mobile responsive CSS for `index.html`:
  - Collapse the hero to a single stacked column (reset `.hero-content` `max-width` and neutralize the `42%` absolutely-positioned `.hero-photo`, or restack it above/below the copy).
  - Constrain the fixed-size decorative circles (`.hero-bg-circle.c1/.c2`) so they no longer force horizontal overflow.
  - Verify and, where needed, fix the remaining sections (about, experience, projects grid, blog list, contact form) at true phone widths (~375px), not only at the 768px breakpoint.
  - Provide a working navigation affordance on mobile (currently `.nav-links { display: none; }` leaves no menu).
- Complete the mobile responsive CSS for `journey_1.html`:
  - Ensure the timeline spine, pips, cards, and dual-role rows stack cleanly and stay within the viewport at phone widths.
  - Confirm background decorations don't cause horizontal scroll.
- No horizontal overflow on either page at 320–430px; text remains legible; tap targets are usable.
- Verify every fix in a live mobile browser preview (iterate until each distortion is gone).

## Capabilities

### New Capabilities
- `responsive-layout`: Defines the mobile responsiveness contract for the site's pages — no horizontal overflow, single-column stacking of desktop multi-column layouts, and legible content across phone widths. This change introduces the capability and its requirement for the homepage and journey pages.

### Modified Capabilities
<!-- None. Existing project-showcase requirements (content, structure, links) are unchanged; only presentation/layout at mobile widths is added. -->

## Impact

- Affected files: `index.html`, `journey_1.html` (embedded `<style>` blocks only; no HTML content/copy changes beyond any markup needed to restack the hero).
- No dependencies, build tooling, or JavaScript added. Shared design system (palette, fonts, nav) preserved.
- Verification requires running the static site in a local mobile preview.
