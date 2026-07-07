---
id: n8n-editorial-machine
title: "n8n editorial machine (Nooscope pipeline)"
category: project
status: active
tags: [project, n8n, automation, editorial]
created: "2026-07-07T23:16:40"
updated: "2026-07-07T23:22:42"
---

## compiled_truth

## Goal

Automate collection and drafting for the magazine's editorial pipeline (source gathering, signal candidate extraction, draft card writing) while keeping every publish decision behind human editorial approval. This is the "AI/n8n as editorial laboratory" arm of [[noosphere-concept]] and the primary engine feeding [[nooscope-machine]] signal candidates and `CONTINUUM` source material.

## Current status (2026-07-07)

**This is the current implementation focus of the project** — ahead of the Astro static shell in actual build order, even though the strategy doc's Stage 1 names the static shell first (see root roadmap). In-repo, `n8n/notes/` and `n8n/workflows/` exist as scaffolding but are not yet populated with actual workflows or notes.

Before n8n is wired up (and as the permanent fallback for anything requiring judgment), the same pipeline is walked by hand: NotebookLM → Markdown → Astro.

## Pipeline

```text
RSS / sites / YouTube / Telegram / source databases
→ n8n collectors
→ raw signal inbox
→ junk filtering
→ topic clustering
→ LLM editorial pass
→ signal / source cards
→ human editor (approval gate)
→ Markdown drafts
→ Astro build
→ deploy
```

See root flow for the full sequence diagram.

## What to automate first

- source collection for `CONTINUUM`;
- source card drafts;
- Nooscope signal candidates (draft scores/descriptions, not final);
- Reading Room draft notes;
- a weekly radar scanning for future-issue material.

## What is never fully automated

Hard constraint, shared project-wide via [[editorial-boundaries]]: final editorial voice, issue thesis, fiction selection, the visual system, final texts, and publication itself all require human approval — n8n/LLM output stops at "draft," never reaches "published," without an editor in the loop.


## timeline

- time: 2026-07-07T23:16:40
  kind: decision
  summary: "Created this page: n8n editorial machine (Nooscope pipeline)"
  source: docs/noosphere_strategy.md
  affects: [n8n-editorial-machine]

- time: 2026-07-07T23:16:59
  kind: decision
  summary: "Captured n8n editorial machine goal, pipeline, and automation scope from docs/noosphere_strategy.md; recorded that this pipeline is the current implementation focus as of 2026-07-07, ahead of the Astro static shell, though n8n/ is currently an empty scaffold."
  source: "docs/noosphere_strategy.md + repo state"
  affects: [n8n-editorial-machine]

- time: 2026-07-07T23:22:42
  kind: decision
  summary: "Fixed root-page slug link convention (unwrap [[roadmap]]/[[flow]] to plain slugs)."
  source: brain lint-links cleanup
  affects: [n8n-editorial-machine]
