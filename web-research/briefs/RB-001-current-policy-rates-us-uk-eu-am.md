# RB-001 — Current official policy / refinancing rates: US, UK, EU, Armenia

| Field | Value |
|---|---|
| **Original intent** | "What are the current refinancing / main policy rates for the United States, United Kingdom, EU, and Armenia, per each central bank's official website?" |
| **Scope** | Four issuing central banks — US Federal Reserve (federal funds target range), Bank of England (Bank Rate), European Central Bank (main refinancing operations rate, plus deposit facility rate noted), Central Bank of Armenia (refinancing rate). Current headline rate as of 2026-07-21, from each issuing bank's official website (primary source). Capture exact rate name + effective/as-of date. |
| **Status** | answered |
| **QA** | PASS · rounds run: 2 |
| **Author** | web-researcher · 2026-07-21 |

## Answer first

As of 2026-07-21, the current headline rates from each issuing central bank's most
recent published decision are: **US** — federal funds target range **3-1/2 to 3-3/4
percent (3.50%–3.75%; upper bound 3.75%)**, held at the FOMC meeting of 17 June 2026
[RS-001]; **UK** — Bank Rate **3.75%**, held at the MPC meeting ending 17 June 2026
[RS-002]; **EU** — the ECB main refinancing operations (MRO) rate **2.40%** (with the
deposit facility rate, the ECB's current primary lever, at **2.25%**), effective 17
June 2026 [RS-003]; **Armenia** — CBA refinancing rate **6.50%**, held at the CBA
Board meeting of 16 June 2026 [RS-004]. All four figures are current (most recent
decisions on file; no later decision published as of access). Every figure rests on
a WebSearch result quoting the issuing bank's own page — direct WebFetch to all four
official domains was blocked (HTTP 403) this session.

## Sub-questions searched

1. US Federal Reserve — current federal funds target range (upper bound + range) and effective date, from federalreserve.gov. — **answered** [RS-001]
2. UK Bank of England — current Bank Rate and effective date, from bankofengland.co.uk. — **answered** [RS-002]
3. EU European Central Bank — current main refinancing operations (MRO) rate + deposit facility rate, with effective date, from ecb.europa.eu. — **answered** [RS-003]
4. Armenia Central Bank of Armenia — current refinancing rate and effective date, from cba.am. — **answered** [RS-004]

## Findings

| # | Claim / finding | Source |
|---|---|---|
| 1 | **United States — Federal Reserve.** Rate name: target range for the federal funds rate. Level: **3-1/2 to 3-3/4 percent (3.50%–3.75%)**, upper bound **3.75%**. As-of: maintained at the FOMC meeting ending **17 June 2026** (most recent decision published as of access). | RS-001 |
| 2 | **United Kingdom — Bank of England.** Rate name: Bank Rate. Level: **3.75%**. As-of: maintained (7–2 vote) at the MPC meeting ending **17 June 2026** (most recent published decision). | RS-002 |
| 3 | **EU — European Central Bank.** Rate literally called "refinancing": main refinancing operations (MRO) rate = **2.40%**. ECB's current primary policy lever: deposit facility rate = **2.25%** (marginal lending facility = 2.65%). As-of: **with effect from 17 June 2026** (decision announced 11 June 2026; a +25 bp increase). | RS-003 |
| 4 | **Armenia — Central Bank of Armenia.** Rate name: refinancing rate (the CBA's main policy rate). Level: **6.50%**. As-of: held unchanged at the CBA Board meeting of **16 June 2026** (most recent decision). | RS-004 |

Every row cites an `RS-NNN` that resolves in `web-research/_sources-index.md`.

## Sources consulted

- **RS-001** · "Federal Reserve issues FOMC statement" (June 17, 2026) · Federal Reserve — primary/official (issuing body). Backs Finding 1.
- **RS-002** · "Bank Rate maintained at 3.75% — June 2026 Monetary Policy Summary and Minutes" · Bank of England — primary/official (issuing body). Backs Finding 2.
- **RS-003** · "Monetary policy decisions" (11 June 2026) · European Central Bank — primary/official (issuing body). Backs Finding 3.
- **RS-004** · "Policy rate left unchanged at 6.50%" (2026-06-16) · Central Bank of Armenia — primary/official (issuing body). Backs Finding 4.

Full URLs, access dates, credibility, and verbatim excerpts are in the companion
`evidence/RB-001-current-policy-rates-us-uk-eu-am.sources.md`; each is registered in
`_sources-index.md`.

## Gaps / not found

None — each of the four sub-questions was answered from its issuing central bank's
official page. The only qualification is the access method (see caveats): direct
WebFetch was blocked, so the figures rest on WebSearch quoting the official pages
rather than a direct page fetch.

## Confidence & caveats

**Confidence: high** on all four levels, rate names, and effective dates — every
figure comes from the issuing bank's own most-recent decision page (strongest
credibility tier), and each was corroborated by at least one adjacent
official-domain page in the same search (e.g. prior-month summaries, the ECB
key-rates portal, the CBA publication/MP-instruments pages).

Caveats:
- **Access method (applies to all four).** Direct `WebFetch` to federalreserve.gov,
  bankofengland.co.uk, ecb.europa.eu, and cba.am each returned HTTP 403 this
  session, at both site-root and specific-page URLs; per `/root/.ccr/README.md` a
  403 is not retried or routed around. Each figure therefore rests on a **WebSearch
  result quoting the official page** (the cited URL resolves to the issuing bank's
  own page), **not** a direct fetch. The excerpts are as rendered by WebSearch.
- **Currency.** "Current" means the most recent published decision as of 2026-07-21.
  A July 2026 FOMC decision and the July 2026 BoE MPC minutes had not been published
  as of access; if either meeting has since decided, the US/UK figures would update.
- **EU terminology.** The intent's "refinancing rate" maps to the ECB's **MRO rate
  (2.40%)**; the deposit facility rate (2.25%) is the ECB's operative primary lever
  and is reported alongside per the intent.
- **Armenia terminology.** The CBA press-release headline says "policy rate"; the
  body names it "Refinancing Rate" — these are the same rate (6.50%), corroborated
  by a CBA source stating "the refinancing rate at 6.50% serves as the key policy
  rate."

## QA record (research-qa)

- **Verdict: PASS** · rounds run: 2 (Round 1 compliance + Round 2 integrity).
- Round 1: RB-001 registered; all template sections present and non-empty;
  original intent restated verbatim; every finding cites an `RS-NNN` that resolves
  in `_sources-index.md`; each source row has title·publisher, date accessed,
  resolvable URL, and RB-001; brief is answer-first with scope stated.
- Round 2: no fabricated figures — every rate traces to its issuing-bank source;
  each `RS-NNN` has a verbatim-excerpt evidence block; the four sources are
  primary/official (issuing bodies) — strongest tier, none load-bearing on a weak
  source; Safe-Zone respected (only public queries left the machine); as-of dates
  present with a staleness caveat. Spot-check: the two terminology-sensitive
  figures (ECB MRO 2.40%, Armenia refinancing 6.50%) were independently
  re-confirmed via a second differently-worded search against the official domains
  and matched.
- Hard failures escalated: none. Known qualification carried as a caveat (not a
  failure): direct WebFetch to all four official domains returned HTTP 403, so
  figures rest on WebSearch quoting the official pages rather than a direct fetch.
