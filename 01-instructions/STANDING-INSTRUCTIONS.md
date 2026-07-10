# Standing Instructions — Armenia CBA Refinance Rate Workspace

## 1. What this workspace does
Reusable workspace for researching and preparing reports on the Central Bank of Armenia (CBA) refinance rate — its history, current level, and context. It is built to be run repeatedly, not used once: the kit, template, and registry persist across runs.

## 2. What input forms it accepts
Only real, user-supplied material for the run at hand belongs in `06-inputs/` — CBA rate tables/announcements, source PDFs or links, analyst notes, prior report excerpts. No synthetic, fabricated, or placeholder data goes there. Synthetic data may exist only in `05-kit/examples-public-synthetic/`, and only if explicitly labeled public and synthetic.

## 3. Files and artifacts — what exists, when to read it
- `01-instructions/` — this note. Read once, at the start of every session.
- `02-template/` — the blank report skeleton. Read before drafting output; never overwrite it with a finished report.
- `03-registry/` — index of past runs (date, inputs, template version, output location, status). Check before starting a new run.
- `04-chart-packs/` — rendered charts from past and current runs. Read when a report needs a chart, or before regenerating one.
- `05-kit/skills/`, `rules/`, `agents/` — how-to procedures, standing quality/behavioral constraints, and agent role definitions. Read whichever applies to the task in front of you.
- `06-inputs/` — this run's real source data. Read at the start of the run, before drafting.

## 4. Load order for a new task
1. This note.
2. `03-registry/` — check for a prior run covering the same period or question.
3. `05-kit/rules/` — constraints that apply no matter what.
4. `05-kit/skills/` — the specific skill for the task at hand.
5. `06-inputs/` — this run's real data.
6. `02-template/` — the shape the output must take.
7. `05-kit/agents/` — only if the skill calls for delegating to a defined agent role.

## 5. The one safety standard you must never miss
Never present a refinance-rate figure, date, or decision as real unless it traces to an actual, verifiable source in `06-inputs/` or a cited external source. If a number isn't sourced, label it explicitly as unverified or estimated — never blend example data from `05-kit/examples-public-synthetic/` into a real report.
