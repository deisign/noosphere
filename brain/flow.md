---
slug: flow
title: Key flows
role: key flows
updated: "2026-07-07T22:52:15"
---

# Key flows

## End-to-end path: editorial automation (n8n → published issue)

This is the core flow of the [[n8n-editorial-machine]] — the current implementation focus.

```mermaid
sequenceDiagram
  participant Src as Sources (RSS/sites/YouTube/Telegram/DBs)
  participant N8N as n8n collectors
  participant Inbox as Raw signal inbox
  participant LLM as LLM editorial pass
  participant Ed as Human editor
  participant Astro as Astro build

  Src->>N8N: ingest raw material
  N8N->>Inbox: store candidates
  Inbox->>Inbox: filter junk, cluster by theme
  Inbox->>LLM: pass cluster to editorial LLM
  LLM->>Ed: propose signal / source cards
  Ed->>Ed: approve, reject, or rewrite (hard human gate)
  Ed->>Astro: approved Markdown drafts + Nooscope data
  Astro-->>Astro: static build
  Astro-->>Astro: deploy (no server)
```

Nothing crosses from `Ed` to `Astro` without explicit human approval — see [[editorial-boundaries]]. Before n8n is wired up, this same path is walked entirely by hand: NotebookLM → Markdown → Astro.

What n8n automates first (draft stage only): source collection for `CONTINUUM`, source card drafts, Nooscope signal candidates, Reading Room drafts, a weekly radar for future issues.

## Other important flows

### Reader path through an issue

```mermaid
graph LR
  Home[/ manifesto] --> IssueLanding[/issue/001 thesis]
  IssueLanding --> FirstWord[FIRST WORD]
  FirstWord --> Rubrics[CONTINUUM / Machine Dreams / Abandoned Habitats / Residual Media]
  Rubrics --> Nooscope[Nooscope panel: Domestic Haunting Index]
  Nooscope --> Fiction[Night Fiction]
  Fiction --> LastPage[Last Page]
  LastPage --> Blackout[Residue: click to blackout]
```

### Nooscope signal formation

```mermaid
graph TD
  Theme[Issue theme] --> Corpus[Source corpus]
  Corpus --> Motifs[Recurring motifs]
  Motifs --> Indices[Indices]
  Indices --> Scoring[Editorial scoring 0-100]
  Scoring --> Cards[Explanation cards]
  Cards --> Panel[Interactive site panel]
```

See [[nooscope-machine]] for the scoring rubric and card structure.
