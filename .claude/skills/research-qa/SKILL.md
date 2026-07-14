---
name: research-qa
description: Two-round QA for a research brief (RB-NNN) and its sources — checks the brief answers the user's original intent, every claim cites a resolvable RS-NNN source, the sources found are credible and current, and gaps are declared not guessed. Called by web-researcher after web-research; also user-invocable.
argument-hint: <RB-NNN / a brief file>
user-invocable: true
---

# Skill: research-qa

Checks a research brief and the sources behind it against `.claude/rules/qa.md`,
`evidence-and-figures.md`, and `safe-zone.md`. Returns **PASS** or **NEEDS-REWORK**
with an itemized list. It is the quality gate for the web-research domain: it
verifies the brief answers the intent **and** that the data found is actually good.
Run it on your own output before returning (web-researcher), or standalone.

## Round 1 — Compliance

1. **(hard)** The brief has an `RB-NNN` row in `_briefs-index.md` and follows
   `web-research/TEMPLATE.brief.md` — every section present and non-empty,
   including the **Original intent** restated as the user gave it.
2. **(hard)** Every claim, figure, or quote in the brief cites an `RS-NNN` that
   resolves to a row in `_sources-index.md`.
3. **(hard)** Each cited source row has: title · publisher, a **date accessed**, a
   **resolvable URL**, and the `RB-NNN` it supports.
4. **(soft)** The brief is **answer-first** and its scope (regions, window) is
   stated; the answer is on the intent, not an adjacent question.

## Round 2 — Integrity

5. **(hard)** **No fabricated content** — every statement traces to a cited source;
   nothing "recalled" or invented (`evidence-and-figures.md` Rule 0). Parts of the
   intent with no credible source are declared **"not found"**, not filled with a
   plausible guess.
6. **(hard) Sources support the claims.** Spot-check: open at least one cited URL
   and confirm it actually says what the brief attributes to it. A claim the source
   does not support is a hard failure.
7. **(hard) The data found is good.** Sources are credible for the claim they back —
   prefer primary / authoritative over aggregators, blogs, or forums. A load-bearing
   claim resting **only** on a weak or undated source is a hard failure; a
   corroboration-only weak source is a soft flag with lowered confidence.
8. **(hard)** Safe-Zone respected — only public queries left the machine; no
   internal/restricted data was sent to a web tool.
9. **(soft) Currency.** Time-sensitive facts carry an as-of date; a stale source
   used for a "current" question is flagged.
10. **(soft) Coverage.** The brief addresses each sub-question of the original
    intent, or explicitly notes what remains unanswered.

## Verdict

Fix what you can in place. Any unfixed **hard** check ⇒ **NEEDS-REWORK** (and, if
the producer can't fix it, a blocker to escalate). All hard checks pass ⇒
**PASS**. Record on/near the brief: rounds run + verdict.
