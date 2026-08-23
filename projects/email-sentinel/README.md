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
- AI models via the Azure AI Foundry model catalog — provider and model swappable by config, never hard-wired
- Dashboard: Monday.com — flagged items become real work items with owners, statuses, and automations

## Decisions

- **Resolution:** detection + confirm. The system detects a likely resolution (reply sent, doc received) and marks it "probably done," but a human confirms before it fully closes. False "resolved" is how things slip.
- **Privacy:** business-content only. The classifier discards personal/non-business messages immediately — never stored, indexed, or searchable.
- **Backfill:** forward-only for the pilot; backfill history once classification quality is trusted, so AI costs aren't paid on history twice.

## MVP

Pilot on 2–3 real mailboxes: classify + extract, land flagged items on the Monday.com board, and measure catch-rate for a couple of weeks before going org-wide.

## Links

- Repo: n/a yet
- Deployed: n/a
- Related docs: n/a

## Open questions

- Which 2–3 mailboxes get the pilot?
- Monday.com board structure — one board with groups per mailbox/account, or a board per team?
- When backfill happens, how far back — 6 months, 12, everything?
- Does "business-content only" filtering need its own review pass before anything is discarded, or do we trust the classifier?
