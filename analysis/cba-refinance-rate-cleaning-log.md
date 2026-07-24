# Cleaning log — CBA refinancing rate (monthly sample)

| Field | Value |
|---|---|
| **Dataset** | DS-002 · `data/cba-refinance-rate.csv` (raw) → `data/cba-refinance-rate-cleaned.csv` |
| **Source** | SRC-001 — shipped **illustrative sample**, tier **P4** (not authoritative) |
| **Class** | public (central-bank policy rate) |
| **Cleaned** | 2026-07-24 · via throwaway scripts (ephemeral-compute), both deleted |
| **Verification** | **PASS** (independent script recomputed the series + metrics from the raw cells) |

## Issues detected and action taken

| # | Issue | Row(s) | Action |
|---|---|---|---|
| 1 | Inconsistent date formats | `01/03/2023` (DD/MM/YYYY), `March 2024` (text), `2024/09/01` (slashes) | Normalised all to ISO `YYYY-MM-01` |
| 2 | Missing value | `2023-08-01`, `2024-05-01` (blank rate) | Left as a **gap** — not fabricated; excluded from the cleaned series |
| 3 | Outlier / decimal typo | `2023-09-01` = `95.0` | Corrected to **9.5** (decimal-point error; consistent with neighbours 10.0 → 9.5). Logged assumption. |
| 4 | Duplicate row | `2024-01-01` = `9.25` listed twice | De-duplicated to one row |
| 5 | Unit string in value | `2024-11-01` = `7.25%` | Stripped `%` → `7.25` |

## Method

An ephemeral Python script (stdlib `csv`/`re`, no install) parsed each row: dates
normalised to ISO by pattern, values stripped of `%`, blank rates dropped as gaps,
any value > 50 treated as a decimal-point typo and divided by 10, and rows keyed by
month to de-duplicate. It wrote `data/cba-refinance-rate-cleaned.csv` (28 rows,
2023-01 → 2025-06) and printed the headline metrics. The script was deleted.

## Independent verification

A **separate** script re-read the raw file with a different date parser
(`datetime.strptime` over candidate formats), rebuilt the expected series, and
`assert`ed it equals the cleaned CSV plus each headline figure. Verdict: **PASS**.
Then deleted. `scratch/` confirmed empty.

## Headline figures (each traces to a cleaned cell)

| Metric | Value | Basis |
|---|---|---|
| Start (2023-01) | 10.75% | first cleaned cell |
| End (2025-06) | 6.50% | last cleaned cell |
| Total change | −4.25 pp (−425 bp) | end − start |
| Relative decline | 39.5% lower | (start − end) / start |
| Range | 10.75% (max) → 6.50% (min) | cleaned cells |
| Direction | monotonically non-increasing (never rose) | full cleaned series |
| Last 3 months (Apr–Jun 2025) | held at 6.50% | cleaned cells |

**Caveat:** SRC-001 is an illustrative P4 sample and the series ends 2025-06 —
refresh from the official CBA source before any published use.
