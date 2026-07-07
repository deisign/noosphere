---
id: visual-system
title: "Visual system: language, motion, sound"
category: concept
status: active
tags: [concept, visual, design]
created: "2026-07-07T23:21:16"
updated: "2026-07-07T23:21:36"
---

## compiled_truth

## Do not

```text
not 80s neon for its own sake
not a VHS filter over everything
not rockets and chrome as a universal answer
not copying OMNI covers
not turning the site into a Pinterest board
```

## Do

```text
dark gloss
deep violet / graphite / black
red indicator
cold white
cyan as a technical accent
large typography
strict magazine grid
slow movement
minimal interface clutter
the feel of an expensive magazine from an abandoned laboratory
```

## Motion

Motion must be **editorial**, not decorative — each page's motion mode expresses what that rubric is doing:

- `/signal` (FIRST WORD): text appears like an incoming signal;
- `/frequencies` (CONTINUUM): ticker and spectrogram;
- `/multitudes` (Machine Dreams): terminal-style internal monologue;
- `/abandoned` (Failed Archaeology): a slow pass through the ruins of the future;
- `/nooscope`: instrument dials and expandable indices;
- `/residue` (Last Page): near-stillness, ending in a full blackout on click (`ResidueButton`).

## Sound

Sound plays only after an explicit `ENABLE SIGNAL` click — **no autoplay**, ever (`SoundToggle` component, see [[astro-publication-layer]]).

Base sound types: low drone, data chirps, filtered synthetic voice, room tone, metallic echo, final chime.

## Microcopy

Short interface texts are treated as editorial voice, not filler: buttons, captions, source-lineage notes, hover hints, transition text, fake ads, interface phrases. Examples from the strategy doc: `ENABLE SIGNAL`, `ARCHIVE TRACE DETECTED`, `RETURN TO ISSUE 001`, `THIS ROOM IS STILL LISTENING`, `SOURCE LINEAGE`, `NOOSCOPE TRACE`.

## Frontmatter vocabulary

Per-page `mood`, `motion`, and `sound` fields (see [[astro-publication-layer]] content model) draw from this system — e.g. `mood: "authoritative, monochrome, nocturnal"`, `motion: "kinetic typography, slow flicker, low-frequency pulse"`, `sound: "dry narrator voice, low room tone"`.

## Relation to other pages

Expresses the editorial position and tone defined in [[noosphere-concept]]; implemented through the components and content model in [[astro-publication-layer]]; the `NooscopePanel`'s "instrument dials" motion mode is specific to [[nooscope-machine]].


## timeline

- time: 2026-07-07T23:21:16
  kind: decision
  summary: "Created this page: Visual system: language, motion, sound"
  source: docs/noosphere_strategy.md
  affects: [visual-system]

- time: 2026-07-07T23:21:36
  kind: decision
  summary: "Captured visual do/don't rules, per-page motion modes, sound rules, and microcopy examples from docs/noosphere_strategy.md section 13."
  source: docs/noosphere_strategy.md
  affects: [visual-system]
