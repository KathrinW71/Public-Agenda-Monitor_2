---
title: "Public Agenda Monitor — Design"
status: draft
created: 2026-09-12
updated: 2026-09-12
sources:
  - '../../../prds/prd-Public Agenda Monitor-2026-09-12/prd.md'
  - '../../../architecture/architecture-Public Agenda Monitor-2026-09-12/ARCHITECTURE-SPINE.md'
  - '../../../../specs/spec-public-agenda-monitor/SPEC.md'
  - 'imports/agenda-reference.jpg'
---

# Public Agenda Monitor — Design Spine

## Brand & Style

A calm, practical newsroom tool for reviewing public events. Information density serves quick comparison, while the interface keeps editorial authority explicit. DESIGN.md and EXPERIENCE.md win over the mockup if they conflict.

## Colors

- **Ink** (#182B33) — primary text.
- **Calm blue** (#1F6075, soft #DCECF0) — events already present in the review list.
- **Subtle orange** (#A85214, soft #FFF0E3) — newly retrieved events.
- **Success green** (#28734F) — successful source health only.
- **Lines** (#D6E1E5) and **background** (#F4F7F8) — quiet structure.

Color never carries status alone: every state is also named in text.

## Typography

Use the system sans-serif stack. Event titles are the strongest row text; compact column labels and supporting facts remain legible. Avoid decorative display type.

## Layout & Spacing

The primary desktop surface is a wide, horizontally ordered table. Date and optional time lead each row. At narrow widths the table scrolls horizontally rather than dropping facts; the first draft prioritizes desktop/laptop use.

Mockup reference: [agenda-design-preview.html](mockups/agenda-design-preview.html).

## Elevation & Depth

Use a single restrained application shell with a soft shadow. Event rows use tonal fills and compact radii instead of stacked cards.

## Shapes

Use 7–14px radii for controls and the application shell. Primary actions are solid blue; no decorative pills beyond concise filters or state labels.

## Components

| Component | Visual rule |
|---|---|
| Role entry | Two equal, clearly labeled choices: Information Specialists and Redaktion. |
| Event row | Blue for previously present entries; orange for new entries. |
| Horizontal event table | Column headers remain visible: date, time, title, overarching topic, type, source, direct link, relevance, status, and—only for specialists—release. |
| Direct source link | Text link with external-link affordance. |
| Release action | Solid-blue final-column button; absent from the Redaktion view. |
| Source health | Text plus a small state dot; never only a colored dot. |

## Do's and Don'ts

| Do | Don't |
|---|---|
| Keep all planning facts scannable in one row | Move essential facts into hidden drawers in the first draft |
| Make the user role and action boundary obvious | Show release actions to Redaktion |
| Use blue/orange alongside explicit labels | Encode newness only by color |
| Preserve table density on desktop | Replace the review queue with dashboard cards |
