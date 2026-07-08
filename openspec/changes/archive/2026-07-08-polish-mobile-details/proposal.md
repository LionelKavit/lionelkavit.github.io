## Why

With the site now live on mobile, a real-device review (iPhone, kavitmehta.blog) surfaced six concrete
presentation defects — a mix of aesthetic polish and two genuine layout bugs — that make the phone
experience feel unfinished:

1. **Home hero photo is cropped at the bottom**, hiding the subject's face and body (it shows the top
   of the image — sky/ceiling — instead of the person lower in the frame).
2. **Home hero stats** (`3+ Years…`, `2 Years…`, `5+ AI projects…`) are left-aligned and spread across
   far too much vertical space.
3. **Project-page tech-stack pills** are left-aligned, looking ragged on a centered mobile column.
4. **MSA "end-to-end metadata pipeline"** is misaligned on mobile: icons aren't on one line, captions
   are clipped, and the SharePoint→Copilot connector uses an inconsistent `↔` where every other
   connector is `→`.
5. **A tall column of down-arrows overlaps the infographic** on the Pocket Scout and Bracket Analyst
   pages: the horizontal `.ai-arrow` is stretched full-width and then rotated 90°, turning it into a
   ~300px vertical bar that sits on top of the flow cards (a real bug).
6. **A vestigial person-silhouette placeholder icon** is superimposed on the About graduation photo
   (`.about-photo-placeholder::before`), left over from when the box was an empty placeholder.

All fixes are CSS/markup only, mobile-scoped where appropriate, keeping the static HTML approach.

## What Changes

- **Fix 1** — On mobile, change the home hero photo's `object-position` so the subject's face/body are
  visible (crop from the top instead of the bottom).
- **Fix 2** — On mobile, center-align the hero stats and tighten their spacing so they read as a
  compact, balanced group rather than three far-apart full-width rows.
- **Fix 3** — On mobile, center the project-page hero tech-stack pills (`.hero-pills`).
- **Fix 4** — On mobile, lay the MSA pipeline out as a single row: icons on one line, `→` connectors
  between them, and each caption centered below its icon (no clipping). Replace the inconsistent `↔`
  connector with `→` for uniformity.
- **Fix 5** — Fix the `.ai-arrow` on the Pocket Scout and Bracket Analyst pages so on mobile it renders
  as a small centered down-arrow between stacked cards instead of a full-width rotated bar overlapping
  the infographic.
- **Fix 6** — Remove the vestigial `.about-photo-placeholder::before` person-silhouette overlay so the
  real About photo shows unobstructed (all viewports; it's a leftover, not intended anywhere).
- Preserve all content and the desktop layout (≥769px); every layout override stays inside a
  `max-width` media query except the vestigial-overlay removal (which should not show on any viewport).

## Capabilities

### New Capabilities
<!-- None. -->

### Modified Capabilities
- `mobile-aesthetics`: Adds requirements for these specific mobile presentation details (hero photo
  focal point, hero-stat centering, pill centering, pipeline row alignment, infographic-arrow
  rendering, and removal of the placeholder overlay), extending the existing three-pillar standard.

## Impact

- Files: `index.html` (hero photo, hero stats, About overlay), the 7 `project-*.html` pages (pill
  centering), `project-msa-data-agent_3.html` (pipeline), `project-fpl-advisor.html` and
  `project-wc-bracket-analyst.html` (`.ai-arrow`).
- No dependencies, tooling, or JavaScript. Verified in the mobile browser preview at 375px and 320px.
