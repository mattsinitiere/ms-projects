# email-sentinel

**Status:** idea
**Code:** n/a — docs only

## What

A company-wide email classifier, extraction, search, and flagging service running over Outlook. It reads every company mailbox via Microsoft Graph (application permissions, admin consent), classifies each message, extracts the things that matter — tasks and requests, documents and attachments, deadlines and dates — and surfaces anything that needs action on a live tracking dashboard. Everything is indexed and searchable.

## Why

To never let a task, request, or document slip through the cracks ever again. Asks arrive buried in threads, attachments get promised and never sent, deadlines age silently in someone's inbox. This makes the whole company's email a tracked, searchable system instead of a pile of individual inboxes.

## What it extracts

- **Tasks & requests** — action items, asks, commitments made ("I'll send that Friday"), questions awaiting an answer
- **Documents & attachments** — detect and index POs, invoices, contracts, drawings; flag docs that were promised but never sent
- **Deadlines & dates** — due dates, follow-up dates, expiration windows, so items age visibly and go overdue loudly

## Stack

- Azure-native: Microsoft Graph webhooks for ingestion, Azure Functions for processing
- Azure AI Search for the search/index layer
- AI model provider and model must be interchangeable — Claude or OpenAI behind an abstraction, not hard-wired to either
- Dashboard: Monday.com, Excel, or Power BI (undecided — see open questions)

## MVP

Pilot on 2–3 real mailboxes: classify + extract, land flagged items on the tracking dashboard, and measure catch-rate for a couple of weeks before going org-wide.

## Links

- Repo: n/a yet
- Deployed: n/a
- Related docs: n/a

## Open questions

- Which dashboard wins — Monday.com, Excel, or Power BI? Needs to feel "live", not a report you remember to open.
- How does the model abstraction work in practice — Azure AI Foundry model catalog, or a thin in-house provider interface?
- What closes a flagged item — human dismissal, a detected reply, or both? False "resolved" is how things slip.
- Privacy/governance: reading every employee's mail needs admin consent and clear ground rules. What's off-limits?
- Backfill: index historical email from day one, or only go forward?
