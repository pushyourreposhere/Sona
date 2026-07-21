# web-research/ — open-web research workspace

Where an open-web research question becomes a **sourced, verified** answer. Every
task starts from a numbered **brief** (`RB-NNN`), and every source consulted is
logged as `RS-NNN` with its URL — so any claim in a research output traces back to
a real, re-findable page. This folder runs parallel to the analysis pipeline and
is owned by the `web-researcher` agent (skills: `web-research`, `research-qa`).

## Two registries (read before creating an id; update after)

- `_briefs-index.md` — the research **briefs themselves** (`RB-NNN`): the question,
  scope, and status of each research task.
- `_sources-index.md` — every **source** (`RS-NNN`) with its **URL** and access
  date.

## Stable IDs

Never reused, never deleted — mark a superseded entry `Deprecated` with a reason.
Always pair an id with its human name (workspace-wide convention, root `CLAUDE.md`).

- `RB-NNN` — a research brief (the question + scope). File: `briefs/RB-NNN-slug.md`.
- `RS-NNN` — a source consulted on the web. Logged in `_sources-index.md` with URL.

(Distinct from the analysis pipeline's `SRC-NNN`, which registers figures in
`sources/source-registry.md`. `RS-NNN` is this folder's own source namespace.)

## Subfolders

- `briefs/` — one file per brief (`RB-NNN-slug.md`): the question, why it matters,
  scope, success criteria.
- `evidence/` — captured source material and citations, keyed to each `RS-NNN`.
- `findings/` — verified answers distilled from the evidence.
- `reports/` — final research write-ups for a reader.

## Standards for this folder

- **Brief first.** No searching before the task is written as an `RB-NNN` brief and
  registered — the brief is the anchor for the research. Briefs follow
  `TEMPLATE.brief.md`; the `web-research` skill fills the results into it.
- **No unsourced claim.** Every statement in a finding or report traces to an
  `RS-NNN` source in `_sources-index.md` with a resolvable URL
  (`.claude/rules/evidence-and-figures.md`). "Not found" is an acceptable answer.
- **Public queries only.** Only public search queries leave the machine; never send
  internal or restricted data to a web tool (`.claude/rules/safe-zone.md`).

**Primary files**: `_briefs-index.md` (briefs registry) · `_sources-index.md`
(sources registry) · `TEMPLATE.brief.md` (brief shape) · `CLAUDE.md`.
Owned by the `web-researcher` agent · skills `web-research` (find) + `research-qa`
(check).
