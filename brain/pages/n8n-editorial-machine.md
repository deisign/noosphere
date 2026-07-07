---
id: n8n-editorial-machine
title: "n8n editorial machine (Nooscope pipeline)"
category: project
status: active
tags: [project, n8n, automation, editorial]
created: "2026-07-07T23:16:40"
updated: "2026-07-08T01:19:00"
---

## compiled_truth

## Goal

Automate collection and drafting for the magazine's editorial pipeline while keeping every publish decision behind human editorial approval. This is the "AI/n8n as editorial laboratory" arm of [[noosphere-concept]] and the primary engine feeding [[nooscope-machine]] signal candidates, future-issue material, and `CONTINUUM` source material.

## Current status (2026-07-08)

**This is the current implementation focus of the project** — ahead of the Astro static shell in actual build order, even though the strategy doc's Stage 1 names the static shell first.

A working n8n workflow now exists on the hosted n8n instance and is writing Markdown signal cards into the GitHub repository under `signals/<issue-id>/...`. The repo-side `n8n/notes/` and `n8n/workflows/` directories remain scaffolding until the workflow export and setup notes are committed.

The current working machine is no longer only Issue 001-oriented. It builds a **Signal Bank** across multiple future issues: each run collects sources, rejects meta/news noise, routes materials into issue buckets, asks an LLM for editorial analysis, assigns editorial status, saves Markdown, and produces an issue-level readiness report.

Before n8n is wired up for a specific source or when judgment is required, the fallback remains manual: NotebookLM / direct reading → Markdown → Astro.

## Current implemented workflow v0.1

```text
Manual Trigger
→ Sources
→ RSS Read
→ Limit + Normalize
→ Reject News & Meta
→ IF rejected == false
→ Nooscope Scoring
→ Keep Strong Signals
→ Issue Router
→ Build Markdown Signal
→ AI Agent / Mistral Cloud Chat Model
→ Finalize Markdown
→ Editorial Decision
├─ GitHub Create File → signals/<issue>/<slug>.md
└─ Issue Report
```

## Implemented node roles

- **Sources** — currently seeds the first RSS source set, including Public Domain Review and other candidate feeds.
- **RSS Read** — reads feed items.
- **Limit + Normalize** — normalizes RSS output into `title`, `link`, `date`, `content`, `source`, `rubric`.
- **Reject News & Meta** — rejects site meta/noise such as fundraisers, subscriptions, announcements, ticket/sale items.
- **IF** — only passes `rejected: false` items onward.
- **Nooscope Scoring** — adds an initial signal score and matching metadata.
- **Keep Strong Signals** — keeps only candidates worth routing.
- **Issue Router** — assigns `noosphere.primary_issue` and secondary issues across the planned issue map, using keyword routing.
- **Build Markdown Signal** — builds a draft Markdown card with frontmatter, raw note, source, URL, and issue placement.
- **AI Agent** — uses Mistral as the current editor/analyst to produce `NOOSCOPE SIGNAL`, verdict, score, why-now, future ghost, possible article, tags, and URL.
- **Finalize Markdown** — merges the AI analysis back into the Markdown file.
- **Editorial Decision** — parses `Verdict` and `Score`, assigns `main_candidate`, `feature_candidate`, `archive_candidate`, or `storage`, and writes those values into frontmatter.
- **GitHub Create File** — saves final Markdown to `signals/<issue-id>/<slug>.md` in `deisign/noosphere`.
- **Issue Report** — collapses the current run into an issue-readiness report: totals, main/feature/archive counts, power, and readiness.

## Current output model

Signal cards are saved as Markdown files, currently under:

```text
signals/
  001/
  004/
  005/
  011/
  012/
  014/
  015/
  016/
```

Each card carries frontmatter similar to:

```yaml
title: "..."
issue: "016"
issue_title: "Flying Sensors"
source: "Public Domain Review"
url: "..."
date: "..."
status: "main_candidate"
ai_verdict: "FEATURE"
ai_score: 92
```

Then the body contains the raw note plus `## Nooscope Analysis`.

## Issue readiness model

`Issue Report` is a temporary editorial dashboard. It groups the current run by issue and computes:

- `total` — number of signals routed into the issue;
- `main` — `main_candidate` count;
- `feature` — `feature_candidate` count;
- `archive` — `archive_candidate` count;
- `power` — weighted readiness value (`main * 5 + feature * 3 + archive`);
- `readiness` — `seed`, `forming`, or `READY`.

This report is not a publishing decision. It only tells the editor which future issues are accumulating material.

## What to automate next

- Export the current n8n workflow JSON into `n8n/workflows/`.
- Add setup notes and credential assumptions into `n8n/notes/`.
- Add more trusted source feeds.
- Add duplicate detection / novelty detection before GitHub writes.
- Add an update-or-skip step for existing signal files so repeated runs do not fail on duplicate paths.
- Add a stricter LLM prompt: most materials are not features; at least half should remain archive/storage.
- Add an issue catalogue file (`issues/*.md` or `issues.yml`) so issue titles and routing rules are versioned in the repo, not only inside n8n node code.

## What is never fully automated

Hard constraint, shared project-wide via [[editorial-boundaries]]: final editorial voice, issue thesis, fiction selection, the visual system, final texts, and publication itself all require human approval. n8n/LLM output stops at draft/candidate status and may save to the signal bank, but it must not publish finished issue pages without an editor in the loop.


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

- time: 2026-07-08T01:19:00
  kind: decision
  summary: "Updated current status from scaffold to working n8n Signal Bank workflow: RSS intake, meta rejection, issue routing, Mistral editorial pass, Markdown finalization, editorial decision, GitHub file write, and issue readiness report."
  source: "live n8n build session + GitHub signals/ output"
  affects: [n8n-editorial-machine, nooscope-machine]
