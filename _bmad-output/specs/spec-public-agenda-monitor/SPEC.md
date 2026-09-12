---
id: SPEC-public-agenda-monitor
companions:
  - '../../planning-artifacts/prds/prd-Public Agenda Monitor-2026-09-12/prd.md'
  - '../../planning-artifacts/architecture/architecture-Public Agenda Monitor-2026-09-12/ARCHITECTURE-SPINE.md'
sources:
  - '../../planning-artifacts/briefs/brief-Public Agenda Monitor-2026-09-12/brief.md'
---

> **Canonical contract.** This SPEC and its companions are the complete contract for building and validating the Public Agenda Monitor MVP.

# Public Agenda Monitor MVP

## Why

Documentary researchers currently search public sources and maintain a Word agenda manually. The internal hackathon MVP replaces that repeated work with a clear, forward-looking agenda while retaining human editorial responsibility for what reaches editors and journalists.

## Capabilities

- **CAP-1 — Retrieve approved sources**
  - **intent:** A Documentary Researcher can manually retrieve qualifying upcoming events from the three approved Sources.
  - **success:** The Federal President, Federal Constitutional Court, and UN Women each yield Candidate Events or an explicitly labelled Fixture during the demo.

- **CAP-2 — Review and decide Candidate Events**
  - **intent:** A Documentary Researcher can assess, prioritise, comment on, score, approve, or reject a Candidate Event.
  - **success:** A researcher can change a Suggested Score, add a comment, and approve or reject an event; the full Review Entry remains available after another Retrieval.

- **CAP-3 — Present the Editor Agenda**
  - **intent:** An Editor or Journalist can plan coverage from an agenda of approved upcoming events.
  - **success:** The agenda shows only Approved Events whose start date is today through the following 13 calendar days, with the required event facts and direct source link.

- **CAP-4 — Make source failure safe and visible**
  - **intent:** A Documentary Researcher can recognize a failed source retrieval without losing prior research.
  - **success:** A failed retrieval shows Source Health, preserves earlier events and Review Entries, and may use visibly labelled Fixture data for the demo.

## Constraints

- One-time, internal, browser-based hackathon demo; no authentication, scheduled scanning, background jobs, public release, or autonomous editorial decision-making.
- Exactly three Sources: Federal President, Federal Constitutional Court, and UN Women. UN Women is one Source with News and Publications Channels.
- Retrieval is manual. Federal President uses its Terminkalender page first and official appointment RSS fallback second. UN Women uses its official News and Publications pages first and their supplied RSS fallbacks second.
- Editorial approval is the only path into the Editor Agenda; transparent 1–5 suggestions may help ordering but never decide an event.
- A repeat Retrieval must avoid duplicates, preserve editorial work, and retain the original Source text needed for verification.
- The full behavioural and data contract is in the adopted PRD and Architecture Spine companions.

## Non-goals

- Generic crawling, login-protected or social-media sources, subscription content, or additional Sources.
- A trained or opaque relevance model, user management, production operation, or automated withdrawal confirmation.

## Success signal

In the hackathon demo, the three Sources produce reviewable Candidate Events (or clearly labelled Fixtures); a researcher reviews one; and an approved event appears in the 14-calendar-day Editor Agenda. Repeating a retrieval does not create a duplicate, and a source failure remains visible without removing prior data.
