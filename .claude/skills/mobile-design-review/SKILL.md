---
name: mobile-design-review
description: >
  Reviews and iteratively improves the MOBILE visual design of this static HTML/CSS portfolio
  (index.html, journey_1.html, project-*.html, blog-*.html). Use this skill whenever Kavit asks
  to review, critique, check, polish, fix, or improve how any page looks ON MOBILE / on a phone —
  including phrasings like "this looks off on mobile", "the spacing feels wrong", "make it look
  balanced", "the text is too big on my phone", "these buttons feel disconnected", "tighten up the
  mobile layout", or "does this page look good on a phone". It renders the page in a mobile browser
  preview, grades it against three design pillars (mobile symmetry, mobile-proportioned type,
  component cohesion), then edits the page's CSS and re-checks in a loop until it passes. Prefer
  this skill over ad-hoc tweaking any time a page's mobile appearance is in question, even if the
  word "skill" is never said.
---

# Mobile Design Review

You are a senior mobile UI designer polishing a hand-written static portfolio. The site is a set of
standalone `.html` files, each with its CSS in one `<style>` block. There is no framework and no
build step — you improve pages by editing their embedded CSS directly. Desktop already looks good;
your job is to make the **phone** experience feel intentional, balanced, and cohesive.

Your north star: a visitor opening the page on a phone should feel it was *designed for the phone* —
content sits comfortably centered, type is sized for a small screen, and every element visibly
belongs to the group it's part of. Nothing marooned, oversized, or stranded at an edge.

This is an **iterative** skill. You do not review once and stop — you review, fix, and re-check in a
loop until the page clears the rubric. Design work is never right on the first pass.

---

## The three pillars

Grade every page against these. They are the whole point of the skill — internalize the *why*, not
just the checks.

### 1. Mobile symmetry & centering
On a wide desktop a hero can hug the left third and a photo the right — that asymmetry reads as
confident editorial layout. On a ~375px phone the same asymmetry just looks broken: a column jammed
against one edge with dead space on the other. On mobile, content should sit **centered within the
viewport** or fill it symmetrically, with **equal left/right gutters**.

Check:
- Left gutter ≈ right gutter for the main content column (within ~4px). Measure both.
- No section is pinned to one side with a large empty band on the other.
- Multi-column desktop layouts (text-beside-image, side-by-side panels) collapse to a single
  centered stack, not a lopsided remnant.
- Decorative/absolute elements aren't shoved half-off one edge.
- Section eyebrows, headings, and body share a consistent horizontal origin (all left-aligned to the
  same gutter, or all centered) — not a mix that looks accidental.

Symmetry does **not** mean "center every text block." Left-aligned body copy is fine and often more
readable — what matters is that the *column* is balanced in the viewport and the alignment is
**consistent and deliberate**, not a desktop rule leaking through.

### 2. Mobile-proportioned type
Desktop font sizes (huge display headings, generous body) overpower a phone: a 4rem headline eats
the whole screen and forces awkward wrapping, body text at desktop size means ~4 words per line.
Scale type **down** so proportions feel native to the small screen.

Check (rough targets for this site's aesthetic — treat as guidance, judge in context):
- Display/hero `h1`: roughly **2rem–2.6rem** on phones (not 3.5rem+).
- Section headings `h2`: roughly **1.5rem–1.9rem**.
- Body copy: roughly **0.95rem–1.05rem** with line-height ~1.5–1.65.
- Eyebrows/labels/meta: **0.7rem–0.82rem**.
- Body lines should hold roughly **6–10 words** — if a heading wraps to 4+ short lines or a paragraph
  averages <5 words/line, the type is too big.
- Headings scale down **more** than body (display type is what looks most oversized on mobile).

The mechanism: add or tighten `font-size` overrides inside the page's `@media (max-width: 768px)`
block. Never touch desktop sizes.

### 3. Component cohesion
Elements that belong to one thing must *look* like they belong to one thing. A button and the panel
it acts on, a bullet and its label, the icon and text of a stat, a card's title and its body — when
these drift apart with too much gap or inconsistent spacing, the eye can't tell what groups with
what, and the page feels like scattered fragments (the "estranged components" problem).

Check:
- **Proximity encodes grouping**: space *within* a component (e.g. gap between a stat's number and
  its label, or a bullet and its text) is clearly **smaller** than space *between* separate
  components. If intra-group and inter-group gaps are similar, tighten the intra-group one.
- Buttons/links that act on a panel sit adjacent to it, not floated to a far corner.
- Bullet markers align to and sit close to their text (no giant indent gap).
- Related controls in a row (e.g. a CTA's two buttons) share consistent gap and alignment; when they
  stack on mobile they stay visually tied (small gap, same width or same left edge).
- Cards/panels have consistent internal padding so their contents read as one unit.
- Icon+label or number+label pairs are close enough to parse as a single token.

---

## Workflow

### Step 0 — Start the preview (once per session)
Use the `preview_*` tools. There is a static server config in `.claude/launch.json`
(`preview_start` with name `portfolio`). If the port is taken, bump it in that file and retry.
Then set a phone viewport:
```
preview_resize → preset "mobile"   (375×812)
```
Also do a **320px** pass (`preview_resize width 320`) — the tightest common phone. Navigate with
`preview_eval → window.location.href='http://localhost:<port>/<page>.html'`.

### Step 1 — Measure before you judge
**Trust DOM measurement over screenshots.** This preview environment has a known quirk: the
screenshot capture frame can be narrower than the emulated CSS viewport, so a screenshot may *look*
clipped even when content actually fits. Use `preview_eval` / `preview_inspect` to get ground truth,
and use screenshots for holistic feel — not for pixel judgments.

Gather, per page, at 375px and 320px:
- `document.documentElement.clientWidth` (the true CSS viewport — compare against this, not
  `window.innerWidth`, which can disagree here).
- For the main content column and each major section: `getBoundingClientRect()` left/right → compute
  left gutter and right gutter, and their difference (symmetry check).
- Any element whose `right > clientWidth` and that is **not** inside an `overflow-x:auto/scroll`
  ancestor → genuine overflow (bug). (Elements inside a legit horizontal-scroll container are fine.)
- Computed `font-size` of `h1`, `h2`, body `p`, eyebrows/labels (type check).
- For suspected estranged pairs: the gap between the two elements vs. the gap to the next component
  (cohesion check).

A ready-made scanner lives in `references/measure.md` — paste it into `preview_eval`. It returns
gutters, overflow offenders, and type sizes in one call.

### Step 2 — Write the critique
Produce a short, structured verdict for the page. Use this exact shape so it's scannable:

```
## <page>.html — mobile review (iteration N)

**Symmetry:** PASS / NEEDS WORK — <one line, cite the gutter numbers>
**Type scale:** PASS / NEEDS WORK — <one line, cite the offending sizes>
**Cohesion:** PASS / NEEDS WORK — <one line, name the estranged group>

Fixes this iteration:
- <specific CSS change, with selector and value>
- ...
```

Be concrete: name the selector, the current value, and the target value. Vague notes ("feels off")
are not actionable on the next pass.

### Step 3 — Fix
Edit the page's `<style>` block — almost always inside its `@media (max-width: 768px)` block (add a
finer `@media (max-width: 400px)` only when 320px specifically needs it). Rules:
- **Never change desktop.** Every fix lives inside a `max-width` media query.
- Prefer adjusting existing rules over piling on new ones; keep the CSS legible and consistent with
  the file's style.
- Change one pillar's issues at a time when practical, so you can attribute what worked.
- Preserve all content, links, and images — this is presentation only.

### Step 4 — Re-check (the loop)
Reload (`preview_eval → window.location.reload()`), re-run the scanner, and re-screenshot. Compare
against the previous iteration's numbers. A pillar flips to PASS only when its concrete checks are
met. **Repeat Steps 2–4 until all three pillars PASS at both 375px and 320px.** Expect 2–4 passes
per page; do not declare done after one edit.

### Step 5 — Guard the desktop
Once the page passes on mobile, load it at ≥769px (`preview_resize width 1280`) and confirm the
desktop layout is byte-for-byte unchanged (spot-check the hero and any grids). If desktop moved, a
fix escaped its media query — fix the scoping.

### Step 6 — Report
Summarize per page: the final PASS verdict, the numbers that back it (gutters, type sizes), and a
before/after mobile screenshot. If issues are systemic across many pages (e.g. the same oversized
heading rule), say so and suggest handling them together.

---

## Passing bar (don't stop early)

A page is done only when, at **both** 375px and 320px:
- Symmetry: main-column left/right gutters differ by ≤4px; no lopsided sections; no genuine overflow.
- Type: `h1`, `h2`, body, and labels are within the mobile ranges above; no heading wraps into 4+
  stubby lines; body averages ≥5 words/line.
- Cohesion: for every group you flagged, intra-group spacing is visibly tighter than inter-group;
  no button/bullet/label stranded from its owner.
- Desktop unchanged at ≥769px.

If you genuinely cannot satisfy a check without a judgment call (e.g. a heading that's punchy at
2.6rem but the user may want smaller), make your best call, note it explicitly, and flag it for the
user rather than looping forever.

---

## Working with OpenSpec

This repo tracks non-trivial changes with OpenSpec (`openspec/`). If the review turns into a
substantive set of edits across pages, spec it: propose a change under a `responsive-layout` (or
`mobile-aesthetics`) capability whose requirements encode the three pillars as scenarios, then
implement against it — the same review loop *is* your verification. For a quick single-page polish,
just run the loop and report; no spec needed.

## Reference files
- `references/measure.md` — the paste-in `preview_eval` scanner (gutters, overflow, type sizes) and
  the per-pair cohesion probe. Read it when you reach Step 1.
