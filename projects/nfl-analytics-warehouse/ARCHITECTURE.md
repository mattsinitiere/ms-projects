# Architecture — nfl-analytics-warehouse

## Stack

| Layer | Choice |
|---|---|
| Source data | BALLDONTLIE API (2002–2026 backfill) |
| Data | Azure SQL |
| AI | Azure OpenAI embeddings |
| Serve layer | Custom MCP server |
| Infra | Azure — Finishes Labs subscription (fully separate from work infra) |

## Data flow

BALLDONTLIE API → backfill/ingest → Azure SQL → embeddings (Azure OpenAI) → MCP server → clients (Claude, etc.)

_TODO: fill in ingest mechanics — one-shot backfill vs. ongoing refresh, and how embeddings are generated/stored._

## Key decisions

| Decision | Why | Date |
|---|---|---|
| Separate subscription from all work infra | Clean personal/work boundary | — |
| _TODO: backfill remaining decisions from memory_ | | |

## Known limitations / debt

- _TODO_
