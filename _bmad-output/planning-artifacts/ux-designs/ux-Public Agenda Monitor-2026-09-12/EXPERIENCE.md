---
title: "Public Agenda Monitor — Experience"
status: draft
created: 2026-09-12
updated: 2026-09-12
sources:
  - '../../../prds/prd-Public Agenda Monitor-2026-09-12/prd.md'
  - '../../../architecture/architecture-Public Agenda Monitor-2026-09-12/ARCHITECTURE-SPINE.md'
  - '../../../../specs/spec-public-agenda-monitor/SPEC.md'
  - 'imports/agenda-reference.jpg'
---

# Public Agenda Monitor — Experience Spine

## Foundation

Responsive browser-based internal hackathon MVP, optimized for desktop/laptop review work. No authentication is needed for the MVP; the landing page makes the working context explicit. DESIGN.md is the visual-identity reference.

## Information Architecture

| Surface | Reached from | Purpose |
|---|---|---|
| Landing page | App open | Choose Information Specialists or Redaktion. |
| Specialist review queue | Specialist entry | Retrieve, inspect, prioritize, and explicitly release or reject Candidate Events. |
| Redaktion agenda | Redaktion entry | Read approved upcoming events for coverage planning; no review controls. |

Both role entries land on the same horizontal-table structure. The specialist heading is “Prüfwarteschlange für Information Specialists”; the editorial heading is “Agenda-Ansicht für die Redaktion”. Only the specialist view includes the final **Freigeben** column.

## Voice and Tone

Use concise, factual German microcopy: “Quellen abrufen”, “Quelle öffnen”, “Prüfung nötig”, “Freigeben”. Avoid celebratory language and ambiguous system jargon.

## Component Patterns

| Component | Behavioral rule |
|---|---|
| Landing role entry | A user selects Information Specialists or Redaktion before entering the corresponding view. |
| Horizontal event row | Shows date; time when provided; title; overarching topic; event type; source; direct source link; relevance; and status. Unknown source facts remain visibly blank, never guessed. |
| New-event state | A Candidate Event is “Neu” until a review action records a Review Entry. |
| Relevance | Shows the transparent suggested 1–5 score; a specialist can later set an editorial score. A score never decides approval automatically. |
| Release | Only specialists can explicitly release an event. Release is the final action in the row. |
| Rejection | Specialist review supports explicit rejection, but the first shown row layout may introduce its control after the approved core table is implemented. |
| Comments | Omitted from the first visual draft; the PRD requirement to retain review comments remains in scope for implementation. |
| Direct source link | Opens the retained official source detail. |

## State Patterns

| State | Treatment |
|---|---|
| New Candidate Event | Orange row plus the text “Neu”. |
| Existing Candidate Event | Blue row. |
| Candidate / approved / rejected | Explicit status text. Only approved events appear for Redaktion. |
| Time unknown | Show an em dash in the time column. |
| Source health failed | Show understandable error and failed-retrieval time; preserve prior events and reviews. |
| Source no longer lists an approved event | Mark “Prüfung nötig”; do not silently remove it. |
| Fixture | Clearly label it as fixture data. |

## Interaction Primitives

- Clicking a role entry changes only the displayed working context and permitted action.
- Specialist queue supports manual priority order by drag-and-drop and an equivalent keyboard action.
- A direct source link is always available from the row.
- Release requires a deliberate button press; no score, sort, or suggestion may release an event automatically.
- No comments appear in the first visual draft.

## Accessibility Floor

- Meet WCAG 2.2 AA contrast; pair every color state with text.
- Use semantic table headers and links; the release action has an accessible label containing the event title.
- Preserve keyboard access to role entry, links, release, filtering, and manual prioritization.
- At narrow widths, keep all fields available via horizontal table scrolling; never discard a factual column solely because of viewport width.

## Responsive & Platform

Desktop/laptop is the primary review surface. On narrow screens, app chrome wraps and the factual table remains horizontally scrollable. Mobile is read-first, not a separate information architecture.

## Key Flows

### Flow 1 — Specialist review (Mara, media documentarian)

1. Mara opens the landing page and selects Information Specialists.
2. She retrieves the approved sources and sees new entries marked with orange plus “Neu”.
3. She checks date, optional time, title, overarching topic, type, source, direct link, relevance, and status in one row.
4. She uses the direct link to verify the original source, orders candidates, and makes her editorial decision.
5. **Climax:** She presses “Freigeben”; the status updates and the event is eligible for the Redaktion agenda.

### Flow 2 — Coverage planning (Lea, editor)

1. Lea opens the landing page and selects Redaktion.
2. She sees the editorial heading and the same factual table without a release column.
3. The agenda contains approved events only in the 14-calendar-day window.
4. She follows the direct source link when more context is needed.
5. **Climax:** Lea can plan coverage from a concise agenda without seeing raw candidates or editorial controls.
