## Why

Kavit's read of the trust section: nobody will read it. The pipeline diagram's node copy is
engineer-speak ("fetched and validated with zod into a typed tournament snapshot", "pure math, no
I/O"), and the four guardrail cards (grounded-or-declines, no contradictions, pinned facts, won't
oversell) are more AI-governance detail than a visitor wants. The section's argument is already made
by the prose above the diagram; the supporting visuals should be skimmable by a non-engineer.

## What Changes

- Rewrite the three pipeline node titles/descriptions in plain language (no library names, no
  implementation jargon): real FIFA data in → the engine plays the tournament 50,000 times → the AI
  only explains the numbers, never invents them.
- Remove the four guardrail cards and their connector line, replacing them with a single
  plain-language guardrail sentence that keeps the requirement's guardrail idea (grounded or it says
  so).
- Remove the now-orphaned card CSS (`.arch-grid` / `.arch-card*` rules and the mobile rule
  reference); the shared `code` styling selector is left untouched.

## Capabilities

### New Capabilities
<!-- None. -->

### Modified Capabilities
- `project-showcase`: The "Trust section explains true decision mechanics" requirement's "pipeline
  diagram and guardrail cards remain" clause is replaced: the diagram remains with plain-language
  node copy, and the cards are replaced by a single guardrail line.

## Impact

- File: `project-wc-bracket-analyst.html` (trust section markup + orphaned CSS). Mobile verified at
  375px/320px, desktop at 1280px.
