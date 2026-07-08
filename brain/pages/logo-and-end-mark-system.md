---
id: logo-and-end-mark-system
title: "Logo and end mark system"
category: decision
status: active
tags: [decision, logo, masthead, nooscope, typography, design]
created: "2026-07-08T17:25:00"
updated: "2026-07-08T17:25:00"
---

## compiled_truth

## Decision

The Noosphere masthead is built around a custom typographic idea:

```text
НООСФЕРА
  ^^ 
  custom OO ligature
```

The two Cyrillic `О О` letters are replaced by a custom **unfinished / broken infinity OO ligature**. The ligature must still read as two round O letters, not as a separate inserted infinity symbol.

The final direction is:

```text
bold geometric masthead
round OO ligature
unfinished infinity loop
central dot in each loop
gently rough vector texture allowed
optical kerning between the ligature and С
```

The accepted logo direction is close to the vector sketch currently named `noosphere_logo_vector_optical.svg` in the working files: black geometric masthead on transparent or bone-white background, with the `ОО` area functioning as both lettering and the Nooscope mark.

## Logo logic

The masthead is not a startup icon or generic sci-fi logo. It is a magazine masthead.

Core structure:

```text
masthead → OO ligature
OO ligature → Nooscope mark
Nooscope mark → favicon / interface icon / end mark
end mark → rubric-colored closing stamp
```

The logo system therefore has one visual root, not disconnected decorative signs.

## The OO ligature

The `ОО` ligature must obey these rules:

- it occupies the visual width of two `О` letters plus normal optical spacing;
- it matches the cap height of the masthead;
- it matches stroke weight with the rest of the word;
- it has round, Futura/Avant-Garde-like geometric logic;
- it is bold, not narrow or condensed;
- it hints at unfinished infinity without becoming a generic `∞` icon;
- it contains two central points/dots, one inside each loop;
- the two dots turn the ligature into a legitimate Nooscope symbol: two lenses / two foci.

Negative rule:

```text
Do not set the word as Н + ∞ + СФЕРА.
Do not insert an external infinity icon.
The broken infinity must be built from the two O letters themselves.
```

## Optical kerning

Special attention is required after the OO ligature and before `С`.

Problem: because `С` is open on the left, it can look visually farther away than it actually is.

Decision: use optical kerning to pull `С` slightly closer to the OO ligature.

Rule:

```text
The gap after the ligature must feel like normal masthead tracking, not like a word break.
```

This kerning should be tuned visually, not mechanically.

## Surface quality

The current vector has slightly rough edges / handmade tracing qualities. This is acceptable and may be retained as part of the Noosphere print/handmade character.

Do not over-polish into a sterile software logo unless a clean master is needed for technical reproduction.

Preferred master set:

```text
1. clean vector master
2. slightly rough display vector
3. print-textured version for covers/posters
4. small-size simplified mark
```

## Nooscope mark

The small mark is derived from the OO ligature:

```text
unfinished double loop + two dots
```

Meanings:

```text
two O letters
two lenses
two foci
source and projection
signal and trace
unfinished future loop
```

The mark may appear as:

- favicon;
- UI icon;
- source-lineage divider;
- Nooscope button;
- issue footer mark;
- end mark at the end of articles.

## End mark / Nooscope End Mark

The user has a long-standing magazine/site habit of ending materials with a small colored shape, such as a square or circle. For Noosphere, this becomes a branded typographic device.

Decision:

```text
At the end of full materials, place the Nooscope End Mark:
the small OO/broken-infinity mark with two dots, colored by the rubric.
```

Meaning:

```text
text ended
signal fixed
rubric encoded
Nooscope left a trace
```

Internal names:

```text
EndMark
Nooscope End Mark
нооскопічний слід
Residue Mark
```

Preferred implementation name:

```text
EndMark.astro
```

## End mark placement

Use at the end of:

- full essays;
- rubric pages;
- issue spreads with complete text;
- fiction blocks;
- Nooscope page summaries;
- final article body before next navigation.

Do not use after every tiny block:

- not after every Continuum card;
- not after each caption;
- not after each source note;
- not after every Signal Bank card in a dense grid.

This keeps the mark meaningful.

## Rubric colors

Rubrics may be encoded by color. The end mark inherits the rubric color.

Suggested initial rubric colors:

```css
:root {
  --rubric-first-word: #ff3448;
  --rubric-continuum: #8ee6ff;
  --rubric-machine-dreams: #9a7cff;
  --rubric-future-archaeology: #f0b35a;
  --rubric-residual-media: #f26d4f;
  --rubric-nooscope: #f1eee6;
  --rubric-night-fiction: #7fd6a4;
  --rubric-object: #d6c36a;
  --rubric-residue: #8f91a3;
}
```

Stricter palette mapping:

```text
FIRST WORD            → red
CONTINUUM             → cyan
MACHINE DREAMS        → violet
FUTURE ARCHAEOLOGY    → amber
RESIDUAL MEDIA        → orange/red
NOOSCOPE              → bone white or cyan
NIGHT FICTION         → green
OBJECT FROM TOMORROW  → muted yellow / brass
RESIDUE               → muted grey
```

## Component sketch

Astro usage:

```astro
<EndMark rubric={frontmatter.rubric} />
```

HTML shape:

```html
<div class="end-mark end-mark--machine-dreams" aria-hidden="true">
  <NooscopeMark />
</div>
```

CSS logic:

```css
.end-mark {
  --mark-color: var(--rubric-color, var(--ns-red));
  width: 42px;
  margin: clamp(32px, 6vw, 72px) auto 0;
  color: var(--mark-color);
  opacity: 0.95;
}

.end-mark svg {
  display: block;
  width: 100%;
  height: auto;
  fill: currentColor;
}
```

## Data model

Rubric color can be mapped globally or controlled by frontmatter.

Global map example:

```ts
export const rubricColors = {
  "first-word": "var(--rubric-first-word)",
  "continuum": "var(--rubric-continuum)",
  "machine-dreams": "var(--rubric-machine-dreams)",
  "future-archaeology": "var(--rubric-future-archaeology)",
  "residual-media": "var(--rubric-residual-media)",
  "nooscope": "var(--rubric-nooscope)",
  "night-fiction": "var(--rubric-night-fiction)",
  "object": "var(--rubric-object)",
  "residue": "var(--rubric-residue)",
};
```

Optional frontmatter:

```yaml
rubric: "machine-dreams"
rubric_color: "violet"
end_mark: true
```

## Relationship to covers

The end mark connects the article system to the cover system:

```text
cover masthead uses OO ligature
Nooscope mark is extracted from OO ligature
article ending uses Nooscope mark in rubric color
```

This makes the small colored article-ending device a core brand grammar element, not a decorative habit.

## Related pages

- [[visual-design-system]] — visual system, covers, plates, spreads, archive.
- [[visual-system]] — broader visual language, motion, sound, microcopy.
- [[nooscope-machine]] — conceptual meaning of the Nooscope mark.
- [[astro-publication-layer]] — component architecture where `EndMark.astro` and `NooscopeMark.astro` should live.

## timeline

- time: 2026-07-08T17:25:00
  kind: decision
  summary: "Captured the final masthead direction: custom broken-infinity OO ligature with two dots, optical kerning before С, rough vector texture allowed, Nooscope mark derived from the ligature, and rubric-colored Nooscope End Mark at the end of full materials."
  source: conversation / logo sketching session
  affects: [logo-and-end-mark-system, visual-design-system, visual-system, astro-publication-layer, nooscope-machine]
