---
id: editorial-boundaries
title: "Editorial boundaries: human approval and rights"
category: decision
status: active
tags: [decision, editorial, rights]
created: "2026-07-07T23:19:17"
updated: "2026-07-07T23:22:42"
---

## compiled_truth

## Decision

The project draws a hard line between what the [[n8n-editorial-machine]] / LLM pipeline may draft and what may actually reach publication. This line is a project-wide constraint, referenced from root architecture, root roadmap ("Not now: full automation without editor approval"), [[nooscope-machine]], and [[astro-publication-layer]].

## Never fully automate

- final editorial voice;
- issue thesis;
- fiction selection;
- the visual system;
- final texts;
- publication itself — nothing ships without human editor approval.

The n8n/LLM pipeline may produce raw signal inboxes, clustered candidates, and draft signal/source cards. It stops at "draft." A human editor is the only path from draft to published Markdown.

## Rights and assets — not allowed in MVP

- using OMNI scans as primary visuals;
- using film stills without rights;
- using others' music as background;
- publishing translations of copyrighted stories;
- presenting AI-generated images as if they were archival documents.

## Rights and assets — allowed

- original covers and illustrations;
- public-domain texts, after verification;
- original translations of public-domain fiction;
- OMNI as source lineage and object of analysis (never as asset bank);
- AI renders, if explicitly labeled as original visualization (not archival);
- original SVG, canvas, CSS, and generative textures.

## Required source note

Every piece of content that draws on outside material carries a block:

```text
Source Lineage:
Inspired by / derived from editorial research around ...
No archival material reproduced.
Translation / visualisation by НООСФЕРА.
```

Implemented on-site by the `SourceLineage` component — see [[astro-publication-layer]].

## Rationale

Same discipline as the "controlled strangeness" rule in [[noosphere-concept]]: the project can explore fringe topics, OMNI nostalgia, and AI-assisted drafting without becoming legally risky or editorially incoherent, as long as human judgment and verified rights sit between raw material and anything published.


## timeline

- time: 2026-07-07T23:19:17
  kind: decision
  summary: "Created this page: Editorial boundaries: human approval and rights"
  source: docs/noosphere_strategy.md
  affects: [editorial-boundaries]

- time: 2026-07-07T23:21:04
  kind: decision
  summary: Captured the human-approval gate on the editorial pipeline and the assets/rights rules from docs/noosphere_strategy.md sections 14-15.
  source: docs/noosphere_strategy.md
  affects: [editorial-boundaries]

- time: 2026-07-07T23:22:42
  kind: decision
  summary: "Fixed root-page slug link convention (unwrap [[architecture]]/[[roadmap]] to plain slugs)."
  source: brain lint-links cleanup
  affects: [editorial-boundaries]
