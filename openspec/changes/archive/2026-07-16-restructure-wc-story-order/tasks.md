## 1. Reorder

- [x] 1.1 Split the demo video `.shot` block out of the bracket-predictor section into its own `reveal` beat with a short label (e.g. `See it work`)
- [x] 1.2 Move THE RECEIPTS block to directly after the demo beat; move REFLECTION after it; move WHY YOU CAN TRUST IT after the reflection; move POOL-WINNING STRATEGY, GROUP STAGE, and ASK THE ANALYST after trust (before the disclaimer/CTA)
- [x] 1.3 Audit dividers across the new order: exactly one `<hr class="divider">` between adjacent sections, none doubled or missing

## 2. Verify

- [x] 2.1 Mobile preview (375px, 320px): every section renders intact in the new order, no overflow, reveals fire
- [x] 2.2 Desktop (≥1280px): section rhythm and spacing preserved; lightbox and video still work
- [x] 2.3 Confirm no copy was altered in the move (structure-only diff)

## 3. Coordination

- [x] 3.1 Update the active `add-wc-receipts` delta placement wording to be order-agnostic (done at spec time)
