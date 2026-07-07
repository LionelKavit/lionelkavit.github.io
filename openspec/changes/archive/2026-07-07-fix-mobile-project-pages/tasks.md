## 1. Preview setup

- [x] 1.1 Ensure the static preview server is running; set the viewport to a mobile preset (375×812) with a 320px pass
- [x] 1.2 Establish a per-page checklist: no horizontal scroll, grids single-column, fixed rows adapted, step flows contained, hero/pills/metrics/CTA legible

## 2. Newer pages (baseline good, verify + patch)

- [x] 2.1 `project-fpl-advisor.html`: verify at 375/320px; collapse `.impact-inner` 2-up if it crowds, adapt `.dec-row`, confirm `.ai-flow` and lightbox behave; fix any overflow
- [x] 2.2 `project-wc-bracket-analyst.html`: verify at 375/320px; fix any grid/pill/overflow issues

## 3. Older pages (audit + fix)

- [x] 3.1 `project-msa-data-agent_3.html`: contain `.pipeline` (stack or scroll), verify grids collapse, fix overflow
- [x] 3.2 `project-buyside-agent_3.html`: adapt `.spec-row` fixed columns, verify grids, fix overflow
- [x] 3.3 `project-wattbot_2.html`: collapse `.eval-grid` 2-up at small widths, verify grids, fix overflow
- [x] 3.4 `project-process-capability_2.html`: verify all content grids collapse, fix overflow
- [x] 3.5 `project-epl-analysis_3_1.html`: adapt `.llm-node-row` and the leaderboard `.lb-row` (reflow or scroll container), collapse `.impact-inner` if it crowds, fix overflow

## 4. Regression and sign-off

- [x] 4.1 Confirm each of the seven pages has zero horizontal overflow at 320–430px in preview
- [x] 4.2 Spot-check one representative page at desktop width (≥769px); confirm desktop layout unchanged
- [x] 4.3 Confirm all content, images, captions, and links remain present on each page
- [x] 4.4 Capture mobile screenshots of each page as proof the distortion is resolved
