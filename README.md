# Yash Kalwani

I build AI systems and agents. I create the tools that ensure they last in production.

CS + BME at Tufts, class of '27. Personal site, with the food and films: [yashkalwani.dev](https://yashkalwani.dev)

## Projects

I build with Claude Code. Each README says how the project was built; the tests, chaos runs and evals are how I check the result.

**[ledger](https://github.com/flashyash/ledger)**: a double-entry ledger in TypeScript and Postgres, with a private fund's books built on top.
- The database enforces the invariants: entries balance at `COMMIT`, and history is append-only.
- Retries are safe through idempotency keys, and 6 of the 43 tests are concurrency tests.
- Load test: ~1,960 posts/s at 26 ms p99, 0 failed requests, 0 drifted balances (one laptop, 20 connections).

**[payments-sim](https://github.com/flashyash/payments-sim)**: a simulated card processor (authorize, capture, void, refund, chargeback, settlement) that keeps its books in the ledger above, built to stay correct when processes die mid-operation.
- A chaos harness kills processes at 22 named steps and runs a 90 s storm of 70 random kills across 4,102 payments: 0 invariant violations, and sabotage runs prove the checker catches double captures and lost webhooks.
- Reconciliation caught 60 of 60 injected settlement mismatches with 0 false positives. 174 tests.

**[biotech-catalysts](https://github.com/flashyash/biotech-catalysts)**: an event study of how biotech stocks moved around 50 FDA decisions (2020–2026), relative to XBI.
- Over the two trading days of the decision, approvals beat rejections by 30.8 points (95% CI +14.6 to +47.6, Holm-adjusted p = 0.015). Rejections hurt more than approvals help.
- Point-in-time data, survivorship bounds for delisted names, a sponsor-cluster bootstrap, and an analysis plan fixed before the results.

**[poker-solver](https://github.com/flashyash/poker-solver)**: counterfactual regret minimization (CFR) for Kuhn, Leduc and a hold'em river spot, checked against exact game values (Kuhn −1/18) and best-response exploitability, with a C++ port of the hot loop.

**[savvy](https://github.com/flashyash/savvy)**: a rare-disease diagnosis aid built at the Harvard Rare Disease Hackathon. It ranks candidate diseases from reported symptoms using Phrank similarity over the Human Phenotype Ontology.

## Work

- **InterSystems, 2026:** an agentic pipeline that turns a client's request into a working product demo, cutting turnaround from days to hours. Adopted by Sales Engineering.
- **InterSystems, 2025:** replaced a 300+ page weekly performance report with three real-time Grafana dashboards and threshold-breach alerts.
- **Tufts Human Interaction Lab, 2025:** plugin architecture for GailBot, an AI transcription platform used by 200+ researchers.
- **Acumen Medical Communications, 2024:** retrieval over a medical document library with Azure AI Search and OpenAI embeddings, for ~40 medical writers.

## Contact

[LinkedIn](https://linkedin.com/in/yashkalwani) · [Email](mailto:yash.kalwani@gmail.com)
