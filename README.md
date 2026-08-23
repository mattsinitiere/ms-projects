# ms-projects

Personal vault for all builds and ideas — docs, logs, architecture, and guides. Code lives in each project's own repo; this repo is the source of truth for *what exists, why, and where it stands*.

## Index

| Project | Status | One-liner | Repo |
|---|---|---|---|
| [nfl-analytics-warehouse](projects/nfl-analytics-warehouse/) | live | Personal NFL analytics data warehouse — full BALLDONTLIE backfill (2002–2026), Azure SQL, embeddings, custom MCP server | _link_ |
| [blackbird](projects/blackbird/) | live | Dart scoring app | _link_ |

## Statuses

`idea → exploring → building → live → paused → archived`

## Rules (for future me)

1. **Capture:** any idea → [`ideas.md`](ideas.md), immediately, unfiltered. 2–3 lines max.
2. **Log:** touched a project meaningfully → one line in its `LOG.md` before closing the laptop.
3. **Promote:** starting a real build → copy `templates/build-readme.md` into `projects/<slug>/README.md`, cut the idea from `ideas.md`, add index row here.
4. **Sweep:** ~monthly, fix stale statuses, move dead things to `archive/`.
5. **Only README.md is mandatory per project.** ARCHITECTURE.md / LOG.md / guides get created when there's something to put in them.
6. **Don't add new top-level folders** until something physically has nowhere to go.
