## 1. Implement

- [x] 1.1 Add the muted brick red (target ≈ #A63A2E, tuned in preview) and update receipts CSS: hit rows green (mark + text tint), `.miss` rows red (mark + text tint, replacing the current dimming), `.pending` rows `--text-dark`
- [x] 1.2 Confirm no markup/content changes needed (classes already encode outcomes)

## 2. Verify

- [x] 2.1 Spot-check the three cases: `England over Brazil` green, `Netherlands over Canada` red, final row black
- [x] 2.2 Mobile (375px/320px): three colors distinguishable and readable at 0.75rem on --warm-white; desktop check
- [x] 2.3 Contrast check for the red and dark treatments (~4.5:1 on #FFF9F3)

## 3. Follow-up (post-final)

- [ ] 3.1 Flip the final/champion row from black to green or red per the result (class swap only)
