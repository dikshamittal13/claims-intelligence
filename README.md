# Claims Intelligence Workbench

A hands-on learning project: an insurance **claims analytics system** built a little more every day with [Claude Code](https://code.claude.com/docs). Each session adds one real piece, using a Claude feature I haven't used yet.

By March 2027 it will cover synthetic data generation, data-quality checks, forecasting, anomaly detection, document extraction, an MCP server, agents and automation.

> **Synthetic data only.** Everything here is generated. No real customer or company data is ever committed.

## Planned structure

```
claims-intelligence/
├── CLAUDE.md, LEARNING-LOG.md, README.md
├── data/generate.py   synthetic insurance DB (Oracle-style schema)
├── quality/           data-quality checks + tests
├── analytics/         anomalies, forecasting, tests, classification
├── extraction/        claim PDFs/images → validated rows
├── mcp_server/        MCP server: SQL, forecast, anomaly tools
├── agents/            analyst agent, subagents, hooks, approvals
├── evals/             question set + scorer
├── pipeline/          one-command nightly run, scheduled
├── dashboards/        artifacts and generated reports
├── api_ready/         API + Agent SDK versions, tested with mocks
└── .claude/           skills, agents, hooks, settings
```

Folders appear as they are built. Check [LEARNING-LOG.md](LEARNING-LOG.md) for progress.

## Data model (coming next)

A SQLite database with an Oracle-style schema:

| Table      | Holds                                  |
|------------|----------------------------------------|
| `POLICY`   | Insurance policies                     |
| `CUSTOMER` | Policyholders                          |
| `AGENT`    | Agents who sell / manage policies      |
| `CLAIM`    | Claims filed against policies          |
| `PAYMENT`  | Payments made on claims                |

It will contain two years of daily claims with weekly and yearly seasonality, planted spikes, and deliberate data-quality problems (orphans, duplicates, negative amounts) for the checks and detectors to find.

## Ground rules

- **No commit, it didn't happen.** Every session ends with a commit and a line in the learning log.
- **Python does the maths.** A number only counts if code produced it.
- **Secrets stay out.** Keys go in `.env`, which is git-ignored.

## Getting started

```bash
git clone https://github.com/dikshamittal13/claims-intelligence.git
cd claims-intelligence
# setup steps will be added once the data generator exists
```
