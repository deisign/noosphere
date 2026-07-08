# NOOSPHERE Editorial Packet v0.1

The Signal Bank card is not a finished article. It is an editorial packet.

## Model roles

### Mistral — Archivist / primary editor

Mistral creates the clean editorial brief:

- signal summary
- issue and rubric
- proposed angle
- search queries for quotes and media
- first ranking of retrieved candidates

### Grok — Mad associative editor

Grok creates controlled madness:

- strange cultural parallels
- speculative angle
- occult / pop / media archaeology reading
- "what if" hypotheses

Grok must not invent facts, quotes, images, books or licenses.

### DeepSeek — Skeptic / fact-checker

DeepSeek checks the packet:

- unsupported claims
- weak historical assertions
- quote provenance
- media license risk
- what cannot be claimed

## Source discipline

LLMs do not create quote or media candidates from memory.

Correct flow:

```text
LLM generates search queries
→ API/search nodes retrieve real candidates
→ LLM ranks and explains candidates
→ DeepSeek checks provenance/license
→ Final Editor writes the packet
Readiness statuses
seed
→ scored
→ brief_ready
→ essay_ready
→ publish_candidate
Markdown structure
---
title: ""
issue: ""
issue_title: ""
rubric: ""
status: ""
ai_verdict: ""
ai_score: 0
source: ""
url: ""
date: ""
text_readiness: "seed"
---

# Title

## Raw Signal

## Editorial Brief

## Proposed Angle

## Grok Angle

## Quote Candidates

## Media Candidates

## DeepSeek Factcheck

## Text Readiness

