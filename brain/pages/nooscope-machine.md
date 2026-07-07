---
id: nooscope-machine
title: "Nooscope: editorial signal instrument"
category: concept
status: active
tags: [concept, nooscope, editorial]
created: "2026-07-07T23:15:35"
updated: "2026-07-08T01:19:00"
---

## compiled_truth

## Definition

Nooscope is an in-universe **editorial instrument for reading cultural signals**. It is explicitly **not** statistics, **not** fortune-telling, and **not** a rigorous scientific measuring device — see [[editorial-boundaries]] for why this boundary is enforced project-wide.

Boundary against scope creep: Nooscope is **not a SEM (electron-microscope) gallery**. Micro-aesthetics of objects (dust, circuit boards, tape, solder) belong to the separate rubric `Inner Domains` — see [[noosphere-concept]]. Nooscope looks at cultural signals, not dust or microchips.

## Two operating modes

Nooscope now has two related but distinct editorial modes.

### 1. Per-issue instrument

This is the published, in-universe Nooscope panel for a specific issue.

```text
issue theme
→ source corpus
→ recurring motifs
→ indices
→ editorial scoring
→ explanation cards
→ interactive panel on the site
```

### 2. Signal Bank machine

This is the working editorial intake machine built in n8n. It does not only serve Issue 001. It routes incoming cultural artifacts into a bank of future issue candidates.

```text
RSS / archives / sites
→ normalized raw material
→ meta/noise rejection
→ initial Nooscope scoring
→ issue routing
→ LLM editorial draft
→ editorial decision status
→ Markdown signal card
→ GitHub signal bank
→ issue readiness report
```

The Signal Bank is a pre-publication archive. It may contain strong ideas, weak ideas, wrong assignments, and LLM hallucinations. It is raw editorial ore, not finished journalism.

## Current issue router map

The working n8n router uses a planned set of future issue buckets. Current active buckets include:

```text
001 — The Future Is a Haunted House
004 — The Animal That Was a Machine
005 — Cities That Dream of Control
011 — Rituals for Machines
012 — The Body as Interface
014 — Law of the Machine
015 — Plants That Remember
016 — Flying Sensors
```

The wider planned issue map also includes topics such as Synthetic God, Dead Internet Museum, Archive That Started Thinking, Machines for Seeing the Invisible, Future of Death, Lost Media, Night Machine, and others. The issue catalogue should be moved from n8n node code into versioned repo data next.

## Scoring rubric

Each published index/signal is scored editorially on a 0–100 scale, composed of:

| component | range |
|---|---|
| source presence | 0–25 |
| current relevance | 0–25 |
| cultural persistence | 0–20 |
| issue centrality | 0–20 |
| visual/sound potential | 0–10 |

For n8n Signal Bank cards, the LLM score is only a **draft score**. Human review may downgrade, reroute, merge, or reject the card.

## Explanation card structure

Every index is revealed as a card containing:

- what the signal means;
- where it shows up;
- which sources/artifacts support it;
- which issue page it connects to;
- the final sentence that fixes/anchors it.

The n8n draft card currently uses this rough structure:

```text
NOOSCOPE SIGNAL
Title
Verdict
Score
Why now
Future Ghost
Possible Article
Tags
URL
```

## Editorial statuses

The working n8n pipeline assigns:

| status | meaning |
|---|---|
| `main_candidate` | strong candidate for a central article or major signal |
| `feature_candidate` | possible feature / Continuum item / source card |
| `archive_candidate` | useful background, sidebar, or later reference |
| `storage` | low-priority material kept only if useful |

These statuses are not publication states. They are queue states.

## Issue readiness report

The n8n `Issue Report` groups the current run by issue and computes a rough power value:

```text
power = main_candidate * 5 + feature_candidate * 3 + archive_candidate
```

Readiness labels are only editorial hints:

```text
seed → forming → READY
```

An issue becoming `READY` means the bank has enough raw material to start human assembly, not that it should be published automatically.

## Issue 001 instrument: Domestic Haunting Index

For [[issue-001-haunted-house]], the base published instrument and its scored signals:

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

- On the Astro site, the published Nooscope should be rendered by a `NooscopePanel` component reading static TypeScript data (e.g. `nooscope-001.ts`) — see [[astro-publication-layer]].
- Signal candidates are drafted by the [[n8n-editorial-machine]] pipeline but scored/approved by a human editor before becoming published Nooscope data — same human-approval gate as all other editorial output.
- The current Signal Bank output is saved under `signals/<issue-id>/<slug>.md`.
- Before Astro consumes these files, add duplicate handling, stronger fact-check gates, and a source catalogue.


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

- time: 2026-07-08T01:19:00
  kind: decision
  summary: "Added the working Signal Bank mode: Nooscope now includes both a per-issue published instrument and an n8n-powered intake/routing/reporting machine for future issue candidates."
  source: "live n8n build session + GitHub signals/ output"
  affects: [nooscope-machine, n8n-editorial-machine]
