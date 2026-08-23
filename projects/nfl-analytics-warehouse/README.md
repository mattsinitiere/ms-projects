# nfl-analytics-warehouse

**Status:** live
**Code:** _link to repo_

## What

Personal NFL analytics data warehouse. Full BALLDONTLIE historical backfill (2002–2026) loaded into Azure SQL, enriched with Azure OpenAI embeddings, served through a custom MCP server. Deployed.

## Why

Personal project — completely separate from all Finishes work infrastructure. Runs on its own Finishes Labs subscription.

## Stack

- BALLDONTLIE API (source data, 2002–2026 backfill)
- Azure SQL (warehouse)
- Azure OpenAI (embeddings)
- Custom MCP server (query/serve layer)

## Links

- Repo: _TODO_
- MCP endpoint: _TODO_
- Related docs: [ARCHITECTURE.md](ARCHITECTURE.md), [LOG.md](LOG.md)

## Open questions

- _TODO — backfill from memory: what's undecided or next?_
