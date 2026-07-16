## 1. Build the strip

- [x] 1.1 Add `.scoreboard` strip markup between `<!-- HERO -->` and `<!-- IMPACT BAR -->` in `project-wc-bracket-analyst.html`: label (`LIVE · WORLD CUP 2026` + static live dot), pill row, as-of stamp
- [x] 1.2 Add strip CSS using page tokens: `--pitch` background, hairline `rgba(255,255,255,0.18)` top border, `.label`-style typography; `.score-pill` base + `.hit` / `.miss` / `.pending` state classes
- [x] 1.3 Populate initial pills with decided facts only: `✓ 4/4 semifinalists called`, `✓ Spain over France — called`, `Final pick: Argentina — in play`; stamp "as of July 15, 2026"

## 2. Mobile

- [x] 2.1 In the existing `@media (max-width: 768px)` block: pills wrap centered, label/stamp stack, pill font ~0.72rem, strip padding tightened
- [x] 2.2 Verify at 375px and 320px in preview: no horizontal overflow, centered wrap, intra-pill spacing tighter than pill-to-pill gaps

## 3. Verify

- [x] 3.1 Desktop (≥1280px): hero → strip → impact bar reads as one deliberate dark band; no other section shifted
- [x] 3.2 Screenshot mobile + desktop as proof

## 4. Follow-up edits (after real matches — do when results are known)

- [x] 4.1 After England vs Argentina: flip/add the semifinal pill to ✓ or ✗ and update the as-of stamp
- [ ] 4.2 After the final: set the final pick pill state, switch label to `FINAL RECORD · WORLD CUP 2026`, update stamp
