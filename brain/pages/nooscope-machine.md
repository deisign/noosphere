---
id: nooscope-machine
title: "Nooscope: editorial signal instrument"
category: concept
status: active
tags: [concept, nooscope, editorial]
created: "2026-07-07T23:15:35"
updated: "2026-07-07T23:15:52"
---

## compiled_truth

## Definition

Nooscope is an in-universe **editorial instrument for reading cultural signals**. It is explicitly **not** statistics, **not** fortune-telling, and **not** a rigorous scientific measuring device — see [[editorial-boundaries]] for why this boundary is enforced project-wide.

Boundary against scope creep: Nooscope is **not a SEM (electron-microscope) gallery**. Micro-aesthetics of objects (dust, circuit boards, tape, solder) belong to the separate rubric `Inner Domains` — see [[noosphere-concept]]. Nooscope looks at cultural signals, not dust or microchips.

## Formation pipeline (per issue)

```text
issue theme
→ source corpus
→ recurring motifs
→ indices
→ editorial scoring
→ explanation cards
→ interactive panel on the site
```

## Scoring rubric

Each index/signal is scored editorially on a 0–100 scale, composed of:

| component | range |
|---|---|
| source presence | 0–25 |
| current relevance | 0–25 |
| cultural persistence | 0–20 |
| issue centrality | 0–20 |
| visual/sound potential | 0–10 |

## Explanation card structure

Every index is revealed as a card containing:

- what the signal means;
- where it shows up;
- which sources/artifacts support it;
- which issue page it connects to;
- the final sentence that fixes/anchors it.

## Issue 001 instrument: Domestic Haunting Index

For [[issue-001-haunted-house]], the base instrument and its scored signals:

| signal | score |
|---|---|
| Voice Without Body | 87 |
| Care Without Presence | 74 |
| Comfort as Surveillance | 69 |
| Obsolete Promise | 91 |
| Machine Memory | 62 |
| Room as Interface | 78 |
| Automation of Loneliness | 83 |

## Implementation notes

- On the Astro site, rendered by the `NooscopePanel` component (the project's signature component) reading static TypeScript data (e.g. `nooscope-001.ts`) — see [[astro-publication-layer]].
- Signal candidates are drafted by the [[n8n-editorial-machine]] pipeline but scored/approved by a human editor before becoming published Nooscope data — same human-approval gate as all other editorial output.


## timeline

- time: 2026-07-07T23:15:35
  kind: decision
  summary: "Created this page: Nooscope: editorial signal instrument"
  source: docs/noosphere_strategy.md
  affects: [nooscope-machine]

- time: 2026-07-07T23:15:52
  kind: decision
  summary: "Captured Nooscope definition, formation pipeline, scoring rubric, card structure, SEM-gallery boundary, and Issue 001's Domestic Haunting Index values from docs/noosphere_strategy.md."
  source: docs/noosphere_strategy.md
  affects: [nooscope-machine]
