## 1. Preview setup

- [x] 1.1 Ensure the static preview server is running; set the viewport to a mobile preset (375×812) with a 320px pass
- [x] 1.2 Establish a per-page checklist: no horizontal scroll, content/sidebar stacked, dense grids collapsed, galleries/hero contained, nav links adapt

## 2. Shared nav

- [x] 2.1 Make the blog top-nav `.nav-links` wrap/adapt at narrow widths so they don't overflow at 320px (apply consistently across the four pages)

## 3. Per-page fixes

- [x] 3.1 `blog-atthai.html`: reduce `.days-grid` from four columns to a legible count on mobile; verify hero, gallery, and content stacking; fix overflow
- [x] 3.2 `blog-kalsubai.html`: verify `.photo-mosaic` and `.span-col` at 320px, contain the `50vh` hero image + overlay text + altitude badge; fix overflow
- [x] 3.3 `blog-drama-club.html`: verify content/sidebar stack and `.blog-hero-image` width; fix overflow
- [x] 3.4 `blog-comics-for-change.html`: verify `.blog-photo-gallery`, `.lineup-row`, and gallery image heights; fix overflow

## 4. Regression and sign-off

- [x] 4.1 Confirm each of the four pages has zero horizontal overflow at 320–430px in preview
- [x] 4.2 Spot-check one representative page at desktop width (≥769px); confirm desktop layout unchanged
- [x] 4.3 Confirm all content, images, captions, and links remain present on each page
- [x] 4.4 Capture mobile screenshots of each page as proof the distortion is resolved
