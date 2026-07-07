## 1. Review baseline

- [x] 1.1 With the mobile preview running, run the `mobile-design-review` scanner on `index.html` at 375px and 320px; record hero `h1`, `h2`, body sizes, gutters, and cohesion gaps
- [x] 1.2 Confirm the reference pages (fpl/buyside/blog) already pass, to use their scale as the target

## 2. Tune index.html type (fix → re-check loop)

- [x] 2.1 In the `@media (max-width: 768px)` block, reduce hero `h1` (~2.8rem → ~2.2–2.4rem); reload and re-measure words-per-line
- [x] 2.2 Reduce section `h2` (~2rem → ~1.7rem); reload and re-measure
- [x] 2.3 Reduce hero body copy (~1.1rem → ~1.0–1.05rem) and set line-height ~1.6; reload and re-measure
- [x] 2.4 Iterate values until hero `h1` no longer wraps into 4+ stubby lines and all sizes sit in the mobile ranges at both 375px and 320px; add a `@media (max-width: 400px)` step only if 320px still overpowers

## 3. Verify pillars on index

- [x] 3.1 Symmetry: main-column gutters still balanced (≤~4px diff) at 375px and 320px
- [x] 3.2 Cohesion: stat number→label and CTA buttons still read as tight groups
- [x] 3.3 Capture before/after mobile screenshots of the index hero

## 4. Sweep the other pages

- [x] 4.1 Run the scanner across journey, the 7 project pages, and the 4 blog pages; confirm each passes the three pillars
- [x] 4.2 Apply a targeted fix only where the scanner flags a concrete failure; leave already-well-scaled type untouched

## 5. Regression and sign-off

- [x] 5.1 View index (and any other touched page) at desktop width (≥769px); confirm desktop layout unchanged
- [x] 5.2 Confirm all content, links, and images preserved
