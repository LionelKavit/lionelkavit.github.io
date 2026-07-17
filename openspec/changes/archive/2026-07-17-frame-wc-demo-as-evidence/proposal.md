## Why

Frame-by-frame verification of the demo video revealed it is not a staged product walkthrough — it is
the real late-June session behind Kavit's bracket lineage: the pool-size field is set to 50 on
camera, the risk slider sits on Balanced, the bracket completes 31/31 and is locked and exported
(`my-bracket (6).csv` visible in the download shelf), and the in-video Analyst chat states that the
"Argentina, France, Spain, and England deep into the tournament are all well-supported by the model"
— recorded when only two Round-of-32 matches had been played, committed to the public repo on
July 1, and live on this page before the quarterfinals. The page currently captions this footage as a
generic "full walkthrough," wasting its strongest evidence. One verified caveat shapes the copy: the
end-of-video bracket differs from the graded export in a few branches (video QFs show France–Canada
and Argentina–Algeria; the graded CSV is save #7, one save after the on-camera #6), so the video
must be framed as the real session behind the bracket — never as pick-for-pick the graded bracket.

## What Changes

- **Demo beat** (`See it work`): add a short lead-in paragraph presenting the video as the real
  session (balanced risk, pool of 50, opening days of the knockouts) with the Analyst's on-camera
  backbone quote, and update the caption to match.
- **Provenance note** in the graded section: add the public-record timing (in the repo since July 1,
  deployed before the quarterfinals) and disclose the post-recording tweaks (graded export is one
  save later, a few picks changed spanning R32 and R16) — while still making **no pre-tournament
  lock claim** (that stance is unchanged).
- All claims limited to what is verifiable on camera or in the public git/deploy record.

## Capabilities

### New Capabilities
<!-- None. -->

### Modified Capabilities
- `project-showcase`: Adds a requirement that the demo video is presented as the verified real
  session with honest divergence disclosure and public-record timing.

## Impact

- File: `project-wc-bracket-analyst.html` (demo beat + provenance note copy only; no structure, CSS,
  or video changes). Mobile verified at 375px/320px; desktop at 1280px.
