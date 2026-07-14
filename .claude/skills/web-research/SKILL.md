---
name: web-research
description: Research a question on the open web — frame the user's intent as a brief (RB-NNN), plan queries, crawl and read sources, log each source as RS-NNN with its URL, and write the results into the brief document. Public sources only; every claim cited, gaps declared not guessed. Use when the user asks to research, find, or gather information from the web.
argument-hint: <the research question / user intent, plus any scope — regions, dates, source preferences>
user-invocable: true
---

# Skill: web-research

Owned by **web-researcher**. Turns a research question into a **sourced brief**
(`RB-NNN`): crawl the open web, read the sources, log each as `RS-NNN` with its
URL, and write the results into the brief document — anchored to the user's
original intent, with no unsourced claim. This is the "find the data" half of the
web-research domain; `research-qa` is the quality gate.

## Preflight

1. Read the anchor (`context/analysis-brief.md`) and `web-research/CLAUDE.md`.
2. Read `web-research/_briefs-index.md` (next free `RB` id) and
   `web-research/_sources-index.md` (next free `RS` id).
3. **Capture the user's original intent verbatim.** It is the brief's anchor — the
   research answers *this*, and must not drift into an adjacent question.
4. **Safe-Zone check**: only *public queries* leave the machine — never send
   internal or restricted data to `WebSearch`/`WebFetch` (`.claude/rules/safe-zone.md`).
   A soft reminder fires before each web call.

## Steps

1. **Frame the brief.** Claim the next `RB-NNN`; copy `web-research/TEMPLATE.brief.md`
   to `web-research/briefs/RB-NNN-<slug>.md`. Fill the **Original intent** (the
   question as the user stated it) and the **Scope** (regions, time window, what
   counts as a complete answer). Register the row in `_briefs-index.md`, status
   `in-progress`.
2. **Plan the search.** Decompose the intent into sub-questions and concrete search
   terms. List them in the brief so coverage is auditable.
3. **Crawl & read.** Use `WebSearch` to find candidate sources and `WebFetch` to
   read them. Prefer **primary / authoritative** sources (issuing body, official
   statistics, original publisher) over aggregators and second-hand summaries.
4. **Log every source consulted** as an `RS-NNN` row in `_sources-index.md`: date
   accessed, title · publisher, the resolvable **URL**, and the `RB-NNN` it serves.
   Capture the supporting excerpt/citation under `web-research/evidence/` keyed to
   the `RS-NNN`. **No claim without a source.**
5. **Extract the results.** Pull the facts, figures, and quotes that answer the
   brief, each tied to the `RS-NNN` it came from. If part of the intent can't be
   answered from a credible source, record **"not found — no credible source
   located"** rather than guessing (`.claude/rules/evidence-and-figures.md`).
6. **Write the results into the brief.** Complete the brief document: an
   answer-first summary of what the research found, the findings each cited to an
   `RS-NNN`, coverage against the sub-questions, declared gaps, and a calibrated
   confidence. Set the `_briefs-index.md` status to `answered`.

## QA (run before returning)

Run **`research-qa`** on the brief + its sources: the brief answers the original
intent; every claim cites a resolvable `RS-NNN`; sources are credible and current;
gaps are declared, not guessed; only public queries left the machine. Fix flags;
escalate an unfixable hard failure to Main Claude.

## Output / return

- `web-research/briefs/RB-NNN-*.md` (the brief, with results), and updated
  `_briefs-index.md` / `_sources-index.md` (+ `evidence/` captures).
- A short summary: the answer-first result, the `RS-NNN` sources it rests on, and
  any part of the intent that came back "not found".

## Suggested next step

`research-qa` (if not already run on the brief), or hand the brief to the relevant
downstream specialist if its results feed another task.
