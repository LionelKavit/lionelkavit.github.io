## Context

`project-wc-bracket-analyst.html` is a static page with embedded CSS. Structure at the insertion
point: `<!-- HERO -->` (dark `var(--pitch)` hero, ends ~line 210) → `<!-- IMPACT BAR -->`
(`.impact-bar { background: var(--pitch-accent) }`, line 213). The strip goes between them.

Design tokens to reuse (from the page's `:root` and existing components):

- Colors: `--pitch: #1A3A1A`, `--pitch-accent: #2D6B2D`, `--pitch-light: #4A9A4A`, `--cream`,
  borders on dark surfaces use `rgba(255,255,255,0.18)`.
- Type: labels are DM Sans, uppercase, letterspaced (see `.label`: 0.7rem / 0.16em tracking);
  numerals/serif accents are Lora. Hero pills already establish the pill idiom
  (`.hero-pills`/`.hero-pill`: rounded, thin light border on dark green).
- Mobile: the page's `@media (max-width: 768px)` block already centers `.hero-pills` and stacks the
  impact bar 2-up.

Tournament state (July 15, 2026): semifinal 1 decided (Spain beat France ✓ as picked); semifinal 2
(England vs Argentina, pick: Argentina) and the final (pick: Argentina champion) undecided.

## Goals / Non-Goals

**Goals:**
- A slim strip that reads in ~2 seconds: label, 3–4 pills with ✓ / ✗ / in-play states, as-of stamp.
- Visually continuous with the hero→impact-bar dark band (not a jarring third color).
- Hand-updatable by editing pill text and a state class; label flips to a permanent-record variant
  post-final without structural change.
- Passes the mobile-aesthetics pillars at 320–430px.

**Non-Goals:**
- No JavaScript, no live data fetch from the app (tournament ends July 19; two manual edits beat a
  new failure mode).
- No provenance claim in the strip (the receipts section owns that).
- No home-page changes (a possible card badge is out of scope here).

## Decisions

- **Placement: its own full-width band between hero and impact bar**, background `var(--pitch)` (same
  as hero) with a `rgba(255,255,255,0.18)` top border to separate it from the hero — so the dark band
  reads as hero → scoreboard → lighter green impact bar, a deliberate stack rather than three clashing
  greens. Alternative (inside the hero) rejected: the hero is already dense, and a distinct band makes
  the post-final "permanent record" version feel at home.
- **Anatomy:** a `LIVE · WORLD CUP 2026` label styled like the page's `.label` idiom (0.7rem, 0.16em
  tracking, uppercase, `--pitch-light` color, with a small pulsing-free "live dot" drawn in CSS as a
  static circle — no animation, to respect the page's calm aesthetic) + a row of pills + a right-aligned
  (desktop) / below (mobile) "as of July 15, 2026" stamp in 0.68rem `rgba(255,255,255,0.5)`.
- **Pill states via modifier classes:** `.score-pill` base (thin `rgba(255,255,255,0.25)` border,
  radius as per `.hero-pill`, 0.78rem DM Sans, white text) with `.hit` (✓ prefix, `--pitch-light`
  border/text tint), `.miss` (✗ prefix, muted `rgba(255,255,255,0.45)` text), `.pending` ("· in play"
  suffix, dashed border). Updating a result = change one class + text.
- **Initial content (only decided facts as ✓):** `✓ 4/4 semifinalists called`, `✓ Spain over France
  — called`, `Final pick: Argentina — in play`. The England–Argentina semi flips the third pill (or
  adds a fourth) when decided; after the final the label swaps to `FINAL RECORD · WORLD CUP 2026`.
- **Mobile (inside the existing 768px block):** pills `flex-wrap: wrap; justify-content: center`
  (matching the page's centered `.hero-pills` mobile pattern); label and stamp stack centered;
  pill font ~0.72rem; strip padding ~1.25rem 1.5rem. Intra-pill spacing tighter than pill-to-pill
  gap (cohesion pillar). Verify no overflow at 320px.

## Risks / Trade-offs

- **Stale strip if not updated after matches** → the as-of stamp makes staleness visible and honest;
  tasks include the two known future edits as explicit follow-ups.
- **Overclaiming** → only decided results get ✓; the pending final stays "in play" until decided.
- **Three stacked green bands could feel heavy** → reuse hero's exact `--pitch` and a hairline
  separator; verify visually in preview and lighten padding if needed.
- **Desktop regression** → strip is new markup; existing selectors untouched. Verify hero/impact bar
  spacing at 1280px.
