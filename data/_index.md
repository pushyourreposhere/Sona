# Dataset Registry (DS-NNN)

Every dataset that enters this workspace is registered here **before** it is used
— local file or planned web pull. This is where `intake` records the Safe-Zone
classification and provenance. Read this before importing (to find the next free
`DS` id and avoid duplicates); update it after importing.

IDs are never reused and never deleted — mark a superseded dataset `Deprecated`
with a reason and point to the id that replaced it.

| ID | Name | File | Class | Source(s) | Status | Notes |
|---|---|---|---|---|---|---|
| DS-001 | Peer central-bank policy rates (US, UK) | data/peer-rates.csv | public | SRC-002, SRC-003 | raw | Published policy rates from issuing central banks (P0); public by nature. This round covers US (Fed) and UK (BoE) only — other default peers (ECB, Bank of Russia, Bank of Georgia) not yet fetched. |
| DS-002 | CBA refinancing rate (monthly) | data/cba-refinance-rate.csv | public | SRC-001 | cleaned | Shipped **illustrative sample** (P4, not authoritative). Cleaned → `data/cba-refinance-rate-cleaned.csv` (28 rows, 2023-01…2025-06); see `analysis/cba-refinance-rate-cleaning-log.md`. Refresh from official CBA before published use. |

<!--
Row template:
| DS-001 | CBA refinancing rate (monthly) | data/cba-refinance-rate.csv | public | SRC-001 | raw | dirty: missing/dup/outlier/date issues to clean |
Class ∈ {public, internal, restricted} — see .claude/rules/safe-zone.md
Status ∈ {raw, cleaned, deprecated}
-->
