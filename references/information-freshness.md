# Information Freshness and Event Integration

Mandatory for current initiations, earnings updates and price refreshes. Historical requests use only the user's cutoff information set. Newly released results and credible material news belong in the current analysis, even before a full quarterly filing or signed transaction exists.

**Inputs:** Exact security/class, research date/timezone, trading session, prior model/cutoff, IR/regulatory sources, timely news, and timestamped quotes.

## Pass 1 — Establish the information set

1. Record financial period, event/release time, quote time and retrieval time separately, with user/market timezones. Crawl dates and search labels are not event timestamps.
2. Check IR results/news, regulatory filings, guidance, presentations and call remarks against the reporting calendar and contemporaneous coverage. Use the newest earnings release and tables immediately; identify missing footnotes rather than reverting to an older complete filing. Distinguish **not retrieved** from **not published**: failed search proves only the former; an official filing feed supports absence from that feed at the observed time.
3. Review material developments since the last results/model: transactions, financing, customers, products, regulation and supply as relevant. Examine the latest 24–72 hours closely around major events, extending the window to cover older unmodeled developments.
4. Read underlying disclosures/articles. Company/regulator confirmation supports signed or completed actions; credible reporting supports reported discussions, not undisclosed terms. For inaccessible sources, try legitimate syndication, official mirrors or another reliable source and disclose remaining gaps.
5. Obtain a quote for the exact security with regular/after-hours/premarket/last-close status and provider delay. If indexed pages are stale or unreadable, try a legitimate public exchange/data interface or another provider. Preserve the observation/payload and access time; do not average asynchronous quotes to hide differences. After material news, use a verifiable post-event quote, disclose session/liquidity limits and retain the previous close for comparison. If only a pre-event quote is available, provide conditional valuation/entry thresholds, not a current post-event recommendation.
6. Check whether consensus/analyst targets incorporate the release. Preserve genuinely pre-release snapshots for surprise analysis; a newly accessed page may still contain old estimates.

## Material events

Maintain a compact ledger with **event and publication time; verification time; direct source and evidence status; economic channel; model/scenario treatment; rating consequence; unresolved conditions**. Explain no-change decisions economically.

For reported M&A, separate existing-business value from transaction-contingent effects. Analyze financing, dilution and integration now. Label and justify hypothetical purchase prices, funding and synergies as stress assumptions; do not invent reported terms, closing probabilities or dates. A rumor alone does not make the existing business unvalueable. Confirmed terms enter the applicable model; consequential unknowns constrain the final rating under V05.

## Pass 2 — Refresh and freeze

1. After drafting and modeling, recheck IR/regulatory releases and material news, then refresh the quote. Log sources, actual times and changes since Pass 1, including no-change checks.
2. Incorporate material changes into affected forecasts, funding/shares, scenarios, valuation, confidence or rating. Recalculate returns and price thresholds and reconcile the headline, body and model. A risk-list footnote is insufficient when the judgment changes.
3. After material revisions, recheck targeted sources and freeze the actual evidence/quote snapshot. Judge quote age by session, volatility, events and provider delay; access time does not refresh an old quote. Do not imply continuous coverage, zero latency or a universal freshness interval.
4. If critical current inputs remain unverifiable after reasonable available-source attempts, state whether the gap affects price, an event scenario or the whole valuation and restrict that conclusion. Continue unaffected work without silently backdating the task.

## Outputs and acceptance

- **Header:** information cutoff, latest results/release, quote timestamp/session/provider delay and target horizon; material post-quote information treatment when relevant.
- **Linked workpaper:** event ledger, two-pass log with actual retrieval times and remaining gaps; surface consequential gaps in the affected report sections.
- **Model and decision:** new material information substantively incorporated and affected calculations refreshed.

Fail the current-information requirement if known newer results are ignored, a material post-filing event is deferred without analysis, an old quote is relabeled current, or changed assumptions fail to reach the investment conclusion.
