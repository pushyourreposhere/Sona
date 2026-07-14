---
name: report-style
description: Neutral, answer-first, cause→effect tone and structure for management-facing outputs. Scoped to the presentations folder and .pptx decks only.
globs:
  - "presentations/**"
  - "**/*.pptx"
alwaysApply: false
---

# Rule: Report Style

**Applies to** prose in the `presentations/` folder and any `.pptx` files — the
management-facing outputs only (the `globs` in this file's frontmatter are the
authoritative path scope). It is referenced by the presentation skills and the
presenter agent — read it before turning numbers into words. It does **not** govern
`analysis/` findings; those follow the evidence, QA, and ephemeral-compute rules but
are not held to this presentation tone/structure standard.

How numbers become words a decision-maker can act on. Applies to the
`presentations/` outputs (HTML presentations and `.pptx` decks).

## Core rule

Write in a **neutral, official tone**, answer-first, with every claim tied to a
figure that appears (with its source) in the same document. Turn numbers into a
**cause → effect → implication** chain — never a bare list of stats, never
persuasion.

## Executive-summary structure

Every presentation's summary (and a finding's "What it means") follows this order:

1. **Situation** — what was measured, over what window, for whom.
2. **Key findings** — the 1–3 numbers that matter, stated plainly.
3. **Cause → effect** — *why* the numbers are what they are, tied to the data
   ("CBA holds a +X pp spread **because** it held at Y% while peers cut").
4. **Implication** — what it means for the decision.
5. **Recommendation** — specific, evidence-tied, in official tone.

## Requirements

| Requirement | Standard | Fail condition |
|---|---|---|
| Answer first | The main number/answer is in the first 2–4 sentences | The reader must hunt for the point |
| Every claim sourced | Each figure in prose also appears in a table/chart with its `SRC-NNN`/`FND-NNN` | A number asserted in text but nowhere traceable |
| Cause stated, not implied | Causal claims name the mechanism and the figures behind them | "Rates are great" with no why |
| Neutral tone | Descriptive, measured, no hype, no first-person salesmanship | Marketing/pathos language (see blocklist) |
| Honest uncertainty | Caveats and single-source figures are flagged, not smoothed over | Confident phrasing over shaky evidence |

## Marketing-pathos blocklist (do not use in outputs)

`game-changer` · `seamless` · `revolutionary` · `unlock` · `delight` ·
`frictionless` · `10x` · `best-in-class` · `cutting-edge` · `supercharge` ·
`effortless` · `world-class` · `next-level` · `transformative` (as filler).

Prefer plain, specific verbs and the actual number. "The refinancing rate fell 75
bp over six months" beats "rates have dramatically improved."

## Cause→effect phrasing — good vs bad

- ✅ "The CBA rate sits 1.25 pp above the peer median because it has held at 9.50%
  since March while four of five peers cut, implying comparatively tighter local
  policy."
- ❌ "Armenia's world-class monetary policy keeps rates strong."
