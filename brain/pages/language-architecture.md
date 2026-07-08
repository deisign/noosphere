---
id: language-architecture
title: "Language architecture: Ukrainian primary, English transmission layer"
category: decision
status: active
tags: [decision, language, i18n, architecture, editorial]
created: "2026-07-08T13:35:00"
updated: "2026-07-08T13:35:00"
---

## compiled_truth

## Decision

The main Noosphere magazine is Ukrainian-first.

English should be supported architecturally from the beginning, but the project should not launch as a fully mirrored bilingual magazine.

Core formula:

```text
Ukrainian is the native edition.
English is the transmission layer.
```

Ukrainian is the editorial center of gravity. English exists to make the project legible internationally: for links, search, portfolio use, collaborations, source lineage, public-domain fiction context, and international readers interested in speculative culture.

## Why English is needed

Noosphere naturally has international source tissue:

- OMNI lineage;
- public-domain fiction;
- retrofuturism;
- science fiction;
- visual culture;
- strange science;
- Public Domain Review-like sources;
- AI / media / design / technology discourse.

English helps with:

```text
international sharing
search discovery
portfolio / project presentation
future collaborations
explaining the project outside Ukrainian context
future zine / PDF / broadcast layers
```

But English must not become the default voice or erase the Ukrainian editorial position.

## Why not full bilingual at launch

A complete mirrored bilingual edition would double the workload:

- every article;
- every caption;
- every fake ad;
- every source note;
- every Nooscope card;
- every cover text;
- every SEO/meta field.

It may also weaken the voice: Noosphere needs a strong Ukrainian editorial tone, not the feeling of text that was mechanically translated.

## Staged bilingual strategy

### Stage 1 — Ukrainian primary

Launch the magazine in Ukrainian:

```text
/                  Ukrainian home
/issue/001         Ukrainian issue landing
/issue/001/signal
/issue/001/frequencies
/issue/001/multitudes
/issue/001/abandoned
/issue/001/residual-media
/issue/001/nooscope
/issue/001/residue
```

UI, microcopy, captions, issue text, and editorial framing are Ukrainian.

### Stage 2 — English access layer

Add an English layer that explains and opens the project, but does not need to translate everything:

```text
/en/
/en/about
/en/issue/001
/en/issue/001/nooscope
/en/reading-room
```

First English layer should include:

- English manifesto;
- English About;
- English Issue 001 landing;
- English issue thesis;
- English Nooscope explanation;
- English Domestic Haunting Index;
- English summaries of major materials;
- English Reading Room / source lineage.

### Stage 3 — selected full translations

Translate only the strongest or most internationally useful materials:

- FIRST WORD;
- main essay;
- Nooscope;
- Night Fiction / public-domain translation notes;
- Object From Tomorrow;
- key visual essays.

Do not require every Signal Bank note or Continuum card to exist in English.

## Route policy

Preferred route structure:

```text
/                         Ukrainian home
/en/                      English home

/issue/001/               Ukrainian issue
/en/issue/001/            English issue

/issue/001/nooscope       Ukrainian Nooscope
/en/issue/001/nooscope    English Nooscope
```

Reasoning:

- the project is Ukrainian by default;
- root should be the native edition;
- `/en/` is an explicit transmission layer;
- this avoids making Ukrainian look like a secondary locale.

Alternative fully symmetric structure:

```text
/uk/
/en/
```

This is technically clean but editorially weaker. Prefer root = Ukrainian.

## Slug policy

Keep slugs as stable English/technical rubric codes even for Ukrainian pages:

```text
/issue/001/signal
/issue/001/frequencies
/issue/001/multitudes
/issue/001/abandoned
/issue/001/residual-media
/issue/001/nooscope
/issue/001/residue
```

Reasons:

- short;
- already part of project architecture;
- function as room/rubric codes;
- stable across languages;
- do not need translation when content language changes.

The page text is Ukrainian; the URL is an editorial code.

## Content structure

Recommended structure:

```text
src/content/issues/
  001/
    uk/
      index.md
      signal.md
      frequencies.md
      multitudes.md
      abandoned.md
      residual-media.md
      nooscope.md
      residue.md

    en/
      index.md
      signal.md
      nooscope.md
      reading-room.md
```

The English folder may be partial. Do not require parity between `uk` and `en` at launch.

## Translation metadata

For Ukrainian source pages:

```yaml
lang: "uk"
translation_status: "source"
translations:
  en: "/en/issue/001/signal"
```

For English pages:

```yaml
lang: "en"
translation_status: "adapted"
translation_of: "/issue/001/signal"
```

Use `adapted`, not merely `translated`, when English text is re-edited for voice and context.

## UI strings

Keep UI strings outside page content:

```text
src/i18n/ui.ts
```

Example:

```ts
export const ui = {
  uk: {
    issue: "Випуск",
    sourceLineage: "Родовід джерел",
    nooscopeTrace: "Нооскопічний слід",
    nextRoom: "Наступна кімната",
    enableSignal: "Увімкнути сигнал",
  },
  en: {
    issue: "Issue",
    sourceLineage: "Source Lineage",
    nooscopeTrace: "Nooscope Trace",
    nextRoom: "Next Room",
    enableSignal: "Enable Signal",
  },
};
```

This keeps the design system unified while letting language switch per route.

## Covers and language

Cover imagery should be separate from cover text:

```text
cover-ascii.svg  — clean ASCII image field
cover-uk.png     — Ukrainian poster export if needed
cover-en.png     — English poster export if needed
```

In the web build, prefer:

```text
ASCII image field + localized text overlay from issue data
```

Example:

```yaml
title:
  uk: "Майбутнє — це дім із привидами"
  en: "The Future Is a Haunted House"
```

This lets one cover image work across languages.

## What must be translated first

Minimum English layer:

1. Home manifesto;
2. About;
3. Issue 001 thesis;
4. Nooscope explanation;
5. Domestic Haunting Index;
6. Reading Room;
7. Source notes;
8. captions for key visuals.

May remain Ukrainian-only at first:

- Continuum cards;
- internal Signal Bank notes;
- some fake ads;
- small rubric items;
- drafts;
- experimental pages.

## Editorial rule

English must act as an international entrance into the Ukrainian magazine, not as the main edition.

Ukrainian formulation:

```text
Українська версія — оригінал.
Англійська версія — сигнал назовні.
```

## Architecture summary

```text
now:
build the Ukrainian magazine

from the start:
make the architecture i18n-ready

first English layer:
home / about / issue landing / nooscope / summaries

later:
selected full translations
```

This gives Noosphere international reach without turning the first issue into an endless translation project.

## Related pages

- [[noosphere-concept]] — Ukrainian editorial identity and magazine concept.
- [[astro-publication-layer]] — routing/content architecture to be extended for language support.
- [[visual-design-system]] — cover system and localized text overlay implications.
- [[issue-001-haunted-house]] — first issue that should get the initial English access layer.

## timeline

- time: 2026-07-08T13:35:00
  kind: decision
  summary: "Captured language architecture decision: Ukrainian is the native edition, English is an international transmission layer; use root for Ukrainian, /en for English, stable English slugs, partial English content folders, UI string tables, localized cover text overlays, and staged translation strategy."
  source: conversation
  affects: [language-architecture, astro-publication-layer, noosphere-concept, visual-design-system, issue-001-haunted-house]
