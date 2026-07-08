---
id: visual-design-system
title: "Visual design system: spreads, covers, plates"
category: concept
status: active
tags: [concept, visual, design, covers, spreads, archive]
created: "2026-07-08T13:25:00"
updated: "2026-07-08T13:25:00"
---

## compiled_truth

## Definition

The visual design system for [[noosphere-concept]] is built around one core rule:

```text
page = magazine spread
issue = sequence of spreads
cover = decoded signal
Nooscope = in-universe instrument
image = plate / visual thesis
author archive = visual matter of the project
```

The public site must not look like a blog, landing page, or generic gallery. It should feel like a static web magazine assembled from editorial spreads: cover, rubric, plate, source note, Nooscope trace, fake ad, and final page.

## General visual position

The visual language combines:

- magazine gloss;
- scientific archive;
- controlled strangeness;
- handmade graphic systems;
- decoded digital signal;
- print texture.

Do:

```text
dark gloss
strict magazine grid
large typography
controlled noise
print texture
strong empty space
instrument details
source notes
plate captions
```

Do not:

```text
neon for neon's sake
VHS filter over everything
generic sci-fi UI
rockets/chrome as a universal answer
Pinterest collage
AI images without a shared system
literal OMNI nostalgia
```

This extends [[visual-system]] and implements the publication layer described in [[astro-publication-layer]].

## Color system: Noosphere Mocha

Catppuccin is useful as a principle — soft dark base, readable accents, stable UI tokens — but Noosphere needs a less cozy and more magazine/laboratory version.

Working name:

```text
NOOSPHERE MOCHA
```

Base CSS tokens:

```css
:root {
  --ns-crust: #050508;
  --ns-mantle: #090a10;
  --ns-base: #101119;
  --ns-surface: #171824;
  --ns-surface-2: #202132;

  --ns-text: #f1eee6;
  --ns-text-soft: #c8c4ba;
  --ns-muted: #8f91a3;
  --ns-line: #303143;

  --ns-cyan: #8ee6ff;
  --ns-red: #ff3448;
  --ns-violet: #4a2c72;
  --ns-amber: #f0b35a;
  --ns-green: #9ad67a;
}
```

Semantic use:

- `crust / mantle` — night, space, deep background, void;
- `base / surface` — pages, panels, cards, instrument surfaces;
- `text` — not pure white, but paper/bone/old gloss;
- `cyan` — technical signal, spectrogram, active link, data;
- `red` — indicator, alarm, device still alive, haunted-house sensor;
- `amber` — archive, lamp, old light, source note, paper;
- `violet` — strangeness, noosphere field, depth, shadow;
- `green` — organic, biosignal, anomalous life, issue-specific accent.

## Issue palettes

The global system stays stable, but each issue gets an **issue climate**.

### Issue 001 / The Future Is a Haunted House

```css
:root[data-issue="001"] {
  --issue-bg: #050508;
  --issue-surface: #11121b;
  --issue-shadow: #170f2a;
  --issue-signal: #ff3448;
  --issue-data: #8ee6ff;
  --issue-archive: #f0b35a;
  --issue-paper: #f1eee6;
}
```

Meaning:

```text
black / graphite  → empty house, night, switched-off space
deep violet       → depth, strangeness, uneasy interior
red sensor        → device still on
cold cyan         → data, room map, voice signal
old amber         → answering machine, archive, dusty lamp
```

## Masthead and mark

The primary identity is a **magazine masthead**, not a startup logo.

Primary form:

```text
НООСФЕРА
```

`NOOSPHERE` may exist as a technical English duplicate, but the public brand should be held by the Cyrillic masthead.

### Masthead

```text
НООСФЕРА
журнал невозможных будущих
```

Character: large, strict, cold, editorial, without cheap sci-fi ornaments.

### Nooscope mark

The Nooscope mark can be derived from the two “О” letters:

```text
◎◎
О—О
НОО
```

Meaning:

- two lenses;
- double objective;
- observation instrument;
- oscilloscope rings;
- twin spheres.

Use it in [[nooscope-machine]], Signal Bank cards, issue covers as a small mark, source-lineage blocks, and eventually favicon/app icons.

### Issue mark

Issue numbers are part of collectability:

```text
001
002
003
```

The number should be almost as important as the title.

## Cover concept

A cover is not a hero section. It is a **poster and decoded signal**.

Series formula:

```text
NOOSPHERE covers are decoded signals.
```

Each cover should feel as if the Nooscope caught a cultural signal and rendered it as an image.

## ASCII covers

ASCII art is a strong cover system because it matches the project at the conceptual level:

```text
image becomes text
signal becomes image
decoding becomes style
computer + print + glitch + archive + poetry
```

ASCII must be a system, not a decorative effect.

### Stable cover grammar

Every cover keeps:

- `НООСФЕРА` masthead;
- issue number;
- fixed cover grid;
- ASCII image field;
- service labels;
- issue palette;
- typography system;
- Nooscope mark.

What changes per issue:

- central image;
- ASCII density;
- accent colors;
- source image type;
- print texture level;
- composition mode.

### Three ASCII modes

**Primitive ASCII** — crude terminal style. Use for Signal Bank, Nooscope, technical pages, microcopy, small headers.

**Complex ANSI ASCII** — dense full-color rendered image. Use for covers, rubric posters, issue landing, large poster images.

**Hybrid ASCII + Matchbox Print** — ASCII image treated as rough print: grain, color misregistration, limited palette, cheap-paper texture. This is the preferred Noosphere cover mode.

## Cover grammar examples

Basic layout:

```text
┌────────────────────────────────────┐
│ НООСФЕРА                           │
│ журнал невозможных будущих         │
├────────────────────────────────────┤
│                                    │
│          ASCII COVER FIELD          │
│                                    │
├────────────────────────────────────┤
│ 001                                │
│ БУДУЩЕЕ — ЭТО ДОМ С ПРИВИДЕНИЯМИ   │
│ The Future Is a Haunted House      │
└────────────────────────────────────┘
```

Poster layout:

```text
НООСФЕРА                                      001

[large ASCII image]

БУДУЩЕЕ — ЭТО ДОМ С ПРИВИДЕНИЯМИ
Voice Without Body / Machine Memory / Room as Interface
```

Masthead rule: the logo itself should not be ASCII. The masthead is a clean typographic anchor; the cover image is the ASCII signal; service elements are monospaced/instrumental.

## Issue 001 cover

Theme: [[issue-001-haunted-house]] — “Будущее — это дом с привидениями” / “The Future Is a Haunted House”.

Central image:

```text
a house is not inhabited, but still switched on
```

Possible motifs:

- dark room;
- black house;
- terminal in an empty kitchen;
- red indicator;
- doorway silhouette;
- faint light inside;
- dusty room map;
- smart speaker as idol;
- house as instrument.

Best first cover direction:

```text
black house / terminal / empty room / one red dot
```

ASCII requires a strong silhouette, high contrast, large masses, and a simple composition. Avoid too many details, low contrast, tiny faces, or complicated backgrounds.

## Cover generation pipeline

Identity must not depend on a specific image model or service. Any generator can be used, but the process must be stable:

```text
1. issue theme
2. one strong simple image
3. source image: AI / author work / collage / photo / 3D
4. cover composition
5. ASCII conversion
6. issue palette limitation
7. print treatment: grain / misregistration / matchbox texture
8. masthead and typography overlay
9. exports: SVG/HTML, PNG fallback, OG image, poster version
```

## Noosphere Visual Archive

The user's existing visual work should be a primary source of the project's visual matter, not an occasional illustration pool.

Working name:

```text
NOOSPHERE VISUAL ARCHIVE
```

Archive directions:

- engravings;
- Polish-poster-inspired works;
- white marker on black paper;
- digital works;
- digital works treated as matchbox print.

Functional mapping:

```text
engravings
→ Future Archaeology / Night Fiction / strange science / archive inserts

Polish poster
→ covers / fake ads / rubric posters / large spreads

white marker on black paper
→ Nooscope / diagrams / signal maps / marginalia / manual schematics

matchbox-print treatment
→ Object pages / small illustrations / fake ads / Signal Bank cards / artifacts

digital / ASCII / print processing
→ covers / Signal Bank / Residual Media / Machine Dreams
```

Rule:

```text
technique ≠ decoration
technique = editorial mode
```

## Images as plates

In Noosphere, images should be treated as **plates**, not generic images.

Vocabulary:

```text
PLATE 001
PLATE 002
SOURCE IMAGE
DETAIL
ARCHIVAL TRACE
NOOSPHERE VISUAL ARCHIVE
```

This makes images part of the scientific/magazine language.

### Plate types

**Hero Plate** — one large illustration for a cover, editorial, big essay, or fiction opener.

**Object Plate** — one object on a dark field: answering machine, terminal, smart speaker, cassette, intercom, sensor, remote.

**Diagrammatic Plate** — scheme/map/instrument/interface: house as sensor map, room as interface, voice as waveform, machine as habit archive.

**Inner Domains Plate** — dust, magnetic tape, plastic, scratches, screen surface, solder, paper. This is where SEM-inspired visuals belong.

**Fake Ad Plate** — advertising spread from an impossible future: EchoHome, Galatea OS, Aftercall, Chronobed.

## Multi-image materials

Classic carousel should not be the primary format because it hides most of the visual material. Use magazine-native formats.

```text
1 image       → Hero Plate / Object Plate
2–4 images    → Plate Grid / Plate Pair / Before-After
5–12 images   → Contact Sheet
image-led     → Image Atlas
wide sequence → Foldout
```

### Contact Sheet

Looks like a lab sheet or photo archive:

```text
┌──────────────┬──────────────┬──────────────┐
│ PLATE 01     │ PLATE 02     │ PLATE 03     │
│ image        │ image        │ image        │
│ caption      │ caption      │ caption      │
├──────────────┼──────────────┼──────────────┤
│ PLATE 04     │ PLATE 05     │ PLATE 06     │
└──────────────┴──────────────┴──────────────┘
```

Lightbox may exist for detail viewing, but the main visual composition must live on the page.

## Spreads as the site unit

Static pages are built as spread scenes.

Desktop:

```text
┌──────────────────────────────────────────────┐
│ НООСФЕРА / ISSUE 001 / RUBRIC                │
├──────────────────────┬───────────────────────┤
│                      │                       │
│  visual field        │  text / article       │
│  object / diagram    │  pull quote           │
│  motion layer        │  source lineage       │
│                      │                       │
├──────────────────────┴───────────────────────┤
│ page number / next room / nooscope trace      │
└──────────────────────────────────────────────┘
```

Mobile:

```text
НООСФЕРА / 001
RUBRIC

[visual field]

[title / lead]

[text]

[source lineage]

[nooscope trace]

[next room]
```

Rule:

```text
desktop = spread as space
mobile = spread as sequence
```

Mobile is not a broken desktop spread; it is the same editorial unit folded into a vertical reading order.

## Spread types

**Cover Spread** — masthead, number, theme, ASCII image, issue nav.

**Editorial Spread** — large phrase, typographic signal, editorial text, source lineage.

**Continuum Spread** — ticker, signal cards, frequencies, dates, source notes.

**Essay Spread** — visual thesis, text, pull quote, plate, source note, Nooscope trace.

**Nooscope Spread** — Domestic Haunting Index, scales, expandable cards, scoring.

**Last Page Spread** — one object, one phrase, one button, blackout.

## CSS logic

Use mobile-first layout; desktop turns the same blocks into spreads.

```css
.magazine-spread {
  display: grid;
  gap: clamp(24px, 4vw, 72px);
  padding: clamp(24px, 5vw, 72px);
}

.spread__visual {
  min-height: 45svh;
}

.spread__text {
  max-width: 72ch;
}

@media (min-width: 900px) {
  .magazine-spread {
    min-height: 100svh;
    align-items: center;
  }

  .spread--split {
    grid-template-columns: 1.1fr 0.9fr;
  }

  .spread--reverse {
    grid-template-columns: 0.9fr 1.1fr;
  }

  .spread__visual {
    min-height: 70svh;
  }
}
```

## Astro implementation components

Needed components:

```text
Masthead.astro
NooscopeMark.astro
MagazineSpread.astro
CoverAscii.astro
IssueNav.astro
PlateFigure.astro
PlateGrid.astro
ContactSheet.astro
ImageAtlas.astro
Foldout.astro
SourceLineage.astro
NooscopeTrace.astro
NooscopePanel.astro
FakeAd.astro
ResidueButton.astro
```

These extend the component list in [[astro-publication-layer]].

## Page frontmatter model

Example:

```yaml
---
title: "The Ghost in the Kitchen"
issue: "001"
rubric: "FIRST WORD"
slug: "signal"
subtitle: "A house that answers is not always occupied."
layout: "spread"
spread_mode: "split"
visual_mode: "typographic-signal"
palette: "haunted-house"
ancestor: "OMNI First Word logic"
source_note: "No archival material reproduced."
final_sentence: "We are building houses to hold our absences."
mvp: true
---
```

## Figure frontmatter model

Example:

```yaml
figures:
  - id: "plate-001"
    src: "/assets/issues/001/plates/terminal-room.jpg"
    caption: "A room that remains operational after presence has left."
    credit: "Noosphere Visual Archive"
    treatment: "ascii-matchbox"
    role: "hero-plate"

  - id: "plate-002"
    src: "/assets/archive/white-marker-001.jpg"
    caption: "Manual diagram for a room that listens."
    credit: "Vadym Antonyuk"
    treatment: "black-paper"
    role: "diagrammatic-plate"
```

## Cover data model

Example:

```yaml
cover:
  mode: "ascii"
  src: "/assets/issues/001/cover-ascii.svg"
  fallback: "/assets/issues/001/cover-og.png"
  source_image: "/assets/issues/001/source/haunted-house-terminal.png"
  palette: "haunted-house"
  treatment: "ascii-matchbox"
  alt: "ASCII image of a dark house-like terminal with a single red indicator light."
```

## Asset naming

Proposed structure:

```text
public/
  assets/
    archive/
      engravings/
      polish-posters/
      black-paper/
      matchbox-print/
      digital/
    issues/
      001/
        cover/
          cover-source.png
          cover-ascii.svg
          cover-og.png
          cover-poster.png
        plates/
          plate-001-terminal-room.jpg
          plate-002-black-paper-diagram.jpg
        ads/
          echohome.jpg
          aftercall.jpg
        ascii/
          haunted-house-cover.html
```

## Author archive integration rule

Every author work used in an issue must have an editorial role, not just visual attractiveness.

Bad:

```text
insert a nice work
```

Good:

```text
this work is Hero Plate / Source-adjacent illustration / Fake Ad base / Nooscope diagram / Object texture / Residual Media insert
```

Minimum archive card:

```yaml
archive_item:
  title: "Untitled black paper drawing"
  year: "2024"
  medium: "white marker on black paper"
  role: "Nooscope diagram base"
  issue: "001"
  treatment: "none / scan cleanup / ascii / matchbox-print"
```

## Fake ads

Fake ads are advertising spreads from impossible futures, not side jokes.

Examples:

```text
ECHOHOME
Дом, который помнит за вас.

GALATEA OS
Забота без присутствия.

AFTERCALL
Сообщения от тех, кто больше не пользуется этим номером.

CHRONOBED
Спите там, где время не обновляется.
```

Visual style: Polish poster + matchbox print + limited palette + large slogan + tiny technical copy + Nooscope mark.

## First implementation milestone

```text
DESIGN SYSTEM v0.1 — SPREADS, NOT PAGES
```

Includes:

1. Noosphere Mocha palette;
2. Issue 001 palette;
3. Masthead / Nooscope mark;
4. MagazineSpread layout;
5. CoverAscii concept component;
6. PlateFigure;
7. PlateGrid;
8. ContactSheet;
9. ImageAtlas;
10. SourceLineage;
11. NooscopeTrace;
12. FakeAd template;
13. mobile stacked spread rules.

## Related pages

- [[noosphere-concept]] — publication identity and editorial position.
- [[visual-system]] — earlier visual language, motion, sound, microcopy rules.
- [[astro-publication-layer]] — static site architecture and component model.
- [[issue-001-haunted-house]] — first issue theme and signals.
- [[nooscope-machine]] — instrument logic that the cover system and Nooscope UI express.

## timeline

- time: 2026-07-08T13:25:00
  kind: decision
  summary: "Captured the expanded visual design system: Noosphere Mocha palette, Cyrillic masthead, Nooscope mark, ASCII cover system, author visual archive, plates/contact sheets/image atlas, spread-based layouts, and mobile stacked-spread rule."
  source: conversation / noosphere_visual_design_system.md
  affects: [visual-design-system, visual-system, astro-publication-layer, issue-001-haunted-house]
