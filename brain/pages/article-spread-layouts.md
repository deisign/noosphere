---
id: article-spread-layouts
title: "Article spread layouts and editorial apparatus"
category: decision
status: active
tags: [decision, layout, spreads, articles, og, editorial-apparatus, design]
created: "2026-07-08T18:55:00"
updated: "2026-07-08T18:55:00"
---

## compiled_truth

## Decision

Noosphere articles are not generic blog posts. Each full material is a **journal object** built from a spread system:

```text
SPREAD = rubric + title + lead + visual field + body + editorial apparatus + source/credit + end mark
```

A spread is an editorial scene. On desktop it opens like a magazine spread; on mobile it folds into a vertical reading sequence.

Related design logic is defined in [[visual-design-system]] and the logo/end mark system in [[logo-and-end-mark-system]].

## Base material hierarchy

Each article should support this editorial order:

```text
1. Issue context
   НООСФЕРА / 001

2. Rubric
   MACHINE DREAMS
   Машинні сни

3. Title
   large article title

4. Dek / subtitle
   short explanatory line, 1–2 lines

5. Hero visual / plate
   main illustration, ASCII, diagram, object, or source image

6. Lead
   first editorial paragraph

7. Body
   main text

8. Editorial apparatus
   quotes, notes, playlist, sources, image atlas, object cards

9. Credits / source lineage
   source, image credit, public-domain and rights notes

10. EndMark
   rubric-colored Nooscope End Mark
```

## Rubric labels

Rubrics should be shown as English editorial codes with smaller Ukrainian translations.

Example:

```text
MACHINE DREAMS
Машинні сни
```

or:

```text
FUTURE ARCHAEOLOGY
Археологія майбутнього
```

Reasoning:

- English labels act as stable in-universe magazine section codes;
- Ukrainian remains the primary editorial language;
- the bilingual rubric lockup helps future `/en/` architecture without making English the main edition.

Suggested CSS:

```css
.rubric-en {
  font-size: clamp(12px, 1.1vw, 15px);
  letter-spacing: 0.18em;
  text-transform: uppercase;
  font-family: var(--font-mono);
}

.rubric-uk {
  margin-top: 0.35rem;
  font-size: clamp(11px, 0.9vw, 13px);
  color: var(--ns-muted);
  letter-spacing: 0.08em;
}
```

## Desktop spread structure

Base desktop material opener:

```text
┌────────────────────────────────────────────────────────────┐
│ НООСФЕРА / ISSUE 001                         MACHINE DREAMS │
│                                                Машинні сни  │
├──────────────────────────────┬─────────────────────────────┤
│                              │                             │
│        HERO PLATE            │   TITLE                     │
│        image / diagram       │   великий заголовок          │
│        caption               │                             │
│                              │   dek / subtitle             │
│                              │                             │
│                              │   lead paragraph             │
│                              │                             │
├──────────────────────────────┴─────────────────────────────┤
│ body text / pull quote / playlist / source lineage          │
└────────────────────────────────────────────────────────────┘
```

The first screen should read as a magazine spread. The article can continue beyond it, but the opening scene must be editorially composed.

## Mobile spread structure

Mobile is not a broken desktop spread. It is the same spread folded vertically:

```text
НООСФЕРА / 001

MACHINE DREAMS
Машинні сни

[ HERO PLATE ]

TITLE

dek

lead

body

pull quote

playlist

image grid

source lineage

[end mark]
```

On mobile, the rubric should appear before the title and not be hidden in side rails.

## Typography hierarchy

### Masthead

```text
НООСФЕРА
```

Uses the approved masthead from [[logo-and-end-mark-system]].

### Issue marker

```css
.issue-number {
  font-size: clamp(14px, 1.5vw, 22px);
  font-family: var(--font-mono);
  letter-spacing: 0.08em;
}
```

### Title

```css
.article-title {
  font-size: clamp(42px, 8vw, 128px);
  line-height: 0.88;
  letter-spacing: -0.04em;
  font-weight: 850;
}
```

The title should be large and poster-like, especially in the opener.

### Dek / subtitle

```css
.article-dek {
  font-size: clamp(18px, 2vw, 28px);
  line-height: 1.15;
  color: var(--ns-text-soft);
  max-width: 42ch;
}
```

### Lead

```css
.article-lead {
  font-size: clamp(20px, 2.1vw, 30px);
  line-height: 1.35;
  max-width: 44ch;
}
```

### Body

```css
.article-body {
  font-size: clamp(18px, 1.2vw, 21px);
  line-height: 1.65;
  max-width: 68ch;
}
```

Do not make text tiny for gloss. Noosphere is a web magazine and must be readable.

### Captions and source notes

```css
.caption,
.source-note {
  font-size: 12px;
  line-height: 1.45;
  font-family: var(--font-mono);
  color: var(--ns-muted);
}
```

## Visual material as plates

Images should be treated as plates, not generic images. This extends [[visual-design-system]].

### Hero Plate

Main image of the material. Use for:

- main illustration;
- author work;
- ASCII visual;
- original material image;
- diagram;
- object photograph/plate.

### Inline Plate

Image inside the article body, with plate number, caption, and credit.

### Plate Grid

For 2–4 images: pairs, before/after, object/signal, visual comparisons.

### Contact Sheet

For material with many original images, e.g. a tyrannosaur article with several illustrations:

```text
PLATE 01 / reconstruction
PLATE 02 / skeleton
PLATE 03 / older illustration
PLATE 04 / modern reconstruction
PLATE 05 / detail
PLATE 06 / archival context
```

The contact sheet should feel like a lab sheet or photo archive, not a social-media gallery.

### Image Atlas

Use when images lead the material. Text becomes short blocks and captions; images form the reading sequence.

## Editorial apparatus modules

Articles should support optional modules without becoming cluttered.

### Pull Quote

Large quote extracted from the article.

```css
.pull-quote {
  font-size: clamp(28px, 4vw, 64px);
  line-height: 0.95;
  letter-spacing: -0.03em;
  border-left: 4px solid var(--rubric-color);
  padding-left: 1rem;
}
```

### Signal Note

Small editorial note:

```text
SIGNAL NOTE
Цей мотив повторюється в рекламі smart home з 2010-х...
```

### Source Lineage

Source and rights block:

```text
SOURCE LINEAGE
Public-domain image. No archival material reproduced.
```

### Nooscope Trace

Connection to issue indices:

```text
NOOSCOPE TRACE
Obsolete Promise / 91
Machine Memory / 62
```

### Object Card

Small in-article object card:

```text
OBJECT
1978 answering machine
status: domestic ghost technology
```

## Sonic appendix / playlists

Most articles should be able to carry a playlist or at least a relevant music link.

Preferred module names:

```text
SONIC APPENDIX
Звуковий додаток
```

or:

```text
LISTENING ROOM
Кімната прослуховування
```

`SONIC APPENDIX` is preferred for article-level music context; `SONIC GHOSTS` remains a rubric name.

Example for an article about tyrannosaurs:

```text
SONIC APPENDIX
T. Rex / Marc Bolan
A glam-rock fossil attached to the dinosaur imaginary.

[Open Spotify]
```

A broader dinosaur-themed playlist may be used when available:

```text
DINOSAUR SONGS
playlist / field recording of extinct pop
```

Playlist is not a random sidebar link. It is an editorial artifact that extends the article.

Astro sketch:

```astro
<PlaylistCard
  title="T. Rex / Marc Bolan"
  subtitle="Sonic appendix to the article"
  platform="Spotify"
  url="https://open.spotify.com/..."
  note="Glam-rock fossil attached to the dinosaur imaginary."
/>
```

CSS sketch:

```css
.playlist-card {
  border: 1px solid color-mix(in srgb, var(--rubric-color), transparent 60%);
  background: linear-gradient(
    135deg,
    color-mix(in srgb, var(--rubric-color), transparent 88%),
    transparent
  );
  padding: clamp(18px, 3vw, 32px);
}

.playlist-card__label {
  font-family: var(--font-mono);
  letter-spacing: 0.16em;
  text-transform: uppercase;
  color: var(--rubric-color);
}
```

## Apparatus map

Each article may define optional apparatus in frontmatter:

```yaml
apparatus:
  playlist: true
  source_lineage: true
  nooscope_trace: true
  image_atlas: true
  object_card: false
  fake_ad: false
  reading_room: true
```

Possible modules:

```text
PlaylistCard
SourceLineage
NooscopeTrace
PullQuote
SignalNote
ObjectCard
PlateGrid
ContactSheet
ReadingRoomCard
FakeAd
RelatedSignal
EndMark
```

Example tyrannosaur article apparatus:

```text
Hero Plate
Contact Sheet with original illustrations
Pull Quote
Signal Note about the cultural image of T. rex
PlaylistCard: T. Rex / Marc Bolan
Reading Room: fossil / monster / pop culture
Source Lineage
EndMark in rubric color
```

## Main layout families

### A. Essay Spread

For major texts:

```text
visual left / text right
then readable body column
apparatus inside the text flow
```

### B. Visual Article Spread

For materials with many images:

```text
title + lead
image atlas
short text blocks
playlist/source/nooscope in apparatus modules
```

### C. Apparatus-heavy Spread

For materials where editorial machine matters:

```text
main text
many side cards
source lineage
playlist
reading room
nooscope trace
```

The tyrannosaur article is likely type B or C.

## Main editorial grid

Use a modular grid where materials can be enriched without becoming cluttered.

Desktop:

```text
┌───────────────┬───────────────────────┬───────────────┐
│ visual        │ main text              │ apparatus     │
│ plates        │ article                │ playlist      │
│ captions      │ quotes                 │ nooscope      │
│               │                       │ sources       │
└───────────────┴───────────────────────┴───────────────┘
```

Mobile:

```text
rubric
title
hero
lead
text
plate
quote
playlist
source
end mark
```

## Permalinks

Every full material should have its own permalink.

Rule:

```text
Each full material = own URL + own metadata + own OG card + own visual trace + own end mark.
```

Preferred MVP route style:

```text
/issue/001/                 issue landing
/issue/001/signal/          editorial
/issue/001/frequencies/     continuum
/issue/001/tyrannosaurus/   article
/issue/001/nooscope/        issue Nooscope
```

Avoid overly deep routes at MVP stage such as `/issue/001/future-archaeology/tyrannosaurus/` unless needed later. Use rubric metadata instead.

## Open Graph cards

Every material with a permalink should have its own Open Graph card generated from the material, not a generic issue card.

Rule:

```text
Issue landing has its own OG card.
Each material has its own OG card.
Each rubric page may have its own OG card.
Signal Bank cards are optional at first.
```

Examples:

```text
/issue/001
→ OG: issue cover

/issue/001/tyrannosaurus
→ OG: tyrannosaur + rubric + title

/issue/001/nooscope
→ OG: Domestic Haunting Index / instrument

/issue/001/residue
→ OG: final page / end signal
```

OG size:

```text
1200 × 630
```

Material OG structure:

```text
┌────────────────────────────────────────────┐
│ НООСФЕРА                         ISSUE 001 │
│ FUTURE ARCHAEOLOGY                         │
│ Археологія майбутнього                     │
│                                            │
│ [hero plate / crop / ASCII / illustration] │
│                                            │
│ ТИРАНОЗАВР ЯК МАШИНА ЧАСУ                  │
│                                            │
│ nooscope mark / rubric color               │
└────────────────────────────────────────────┘
```

OG should be a mini-poster, not a screenshot of the page.

## OG modes

### `article-plate`

For materials with strong images:

```text
hero image + title + rubric + НООСФЕРА
```

### `ascii-title`

For conceptual materials without a concrete image:

```text
ASCII texture / signal field + title
```

### `apparatus-card`

For Nooscope, Reading Room, source-heavy pages:

```text
instrument panel / index / scales / title
```

## OG frontmatter

Example:

```yaml
og:
  title: "Тиранозавр як машина часу"
  description: "Як викопна тварина стала поп-культурним привидом майбутнього."
  image: "/assets/issues/001/og/tyrannosaurus.png"
  mode: "article-plate"
  plate: "/assets/issues/001/plates/trex-hero.jpg"
```

Layout head sketch:

```astro
const {
  title,
  subtitle,
  og,
} = Astro.props.frontmatter;

const ogImage = og?.image ?? "/assets/og/default.png";
```

```html
<meta property="og:title" content={og.title ?? title} />
<meta property="og:description" content={og.description ?? subtitle} />
<meta property="og:image" content={new URL(ogImage, Astro.site)} />
<meta property="og:type" content="article" />

<meta name="twitter:card" content="summary_large_image" />
<meta name="twitter:title" content={og.title ?? title} />
<meta name="twitter:description" content={og.description ?? subtitle} />
<meta name="twitter:image" content={new URL(ogImage, Astro.site)} />
```

## Full article frontmatter example

```yaml
---
title: "Тиранозавр як машина часу"
subtitle: "Як викопна тварина стала поп-культурним привидом майбутнього."
slug: "tyrannosaurus"
permalink: "/issue/001/tyrannosaurus/"
issue: "001"
rubric: "future-archaeology"
rubric_label:
  en: "FUTURE ARCHAEOLOGY"
  uk: "Археологія майбутнього"
layout: "spread"
spread_mode: "hero-left"
lang: "uk"

hero:
  type: "plate"
  src: "/assets/issues/001/plates/trex-hero.jpg"
  caption: "PLATE 01 / Tyrannosaurus as a reconstructed cultural machine."
  credit: "Noosphere Visual Archive"
  alt: "Tyrannosaurus reconstruction as a cultural machine"

figures:
  mode: "contact-sheet"
  items:
    - src: "/assets/issues/001/plates/trex-01.jpg"
      caption: "Early reconstruction"
      credit: "Public domain / source pending"
    - src: "/assets/issues/001/plates/trex-02.jpg"
      caption: "Museum skeleton"
      credit: "Source pending"

apparatus:
  pull_quotes:
    - "Динозавр — це не минуле. Це машина, яка виробляє майбутні страхи."
  playlist:
    title: "T. Rex / Marc Bolan"
    platform: "Spotify"
    url: "https://open.spotify.com/..."
    note: "Glam-rock fossil attached to the dinosaur imaginary."
  nooscope_trace:
    - label: "Obsolete Monster"
      score: 82
    - label: "Future Archaeology"
      score: 91
  reading_room:
    - title: "The cultural afterlife of dinosaurs"
      url: ""
      note: "Source pending"

source_lineage:
  - "Original illustrations credited individually."
  - "No archival material reproduced without rights/public-domain check."

og:
  title: "Тиранозавр як машина часу"
  description: "Як викопна тварина стала поп-культурним привидом майбутнього."
  image: "/assets/issues/001/og/tyrannosaurus.png"
  mode: "article-plate"
  plate: "/assets/issues/001/plates/trex-hero.jpg"

end_mark: true
---
```

## Base Astro component sketch

```astro
<ArticleSpread
  issue={issue}
  rubric={rubric}
  title={title}
  subtitle={subtitle}
  hero={hero}
>
  <ArticleBody />
  <ArticleApparatus />
  <EndMark rubric={rubric} />
</ArticleSpread>
```

Internal component stack:

```text
ArticleHeader
RubricLabel
HeroPlate
ArticleLead
ArticleBody
PullQuote
PlateGrid / ContactSheet / ImageAtlas
PlaylistCard
SourceLineage
NooscopeTrace
EndMark
NextRoom
```

## Final formula

```text
Noosphere article spread =
cover-like typography
+ plate / visual thesis
+ Ukrainian text
+ English rubric-code
+ editorial apparatus
+ sonic appendix
+ source lineage
+ Nooscope trace
+ colored end mark
+ permalink
+ material-specific OG card
```

## Related pages

- [[visual-design-system]] — spread, plate, cover, and visual archive logic.
- [[logo-and-end-mark-system]] — masthead, Nooscope mark, rubric-colored end mark.
- [[astro-publication-layer]] — Astro content and component architecture.
- [[language-architecture]] — Ukrainian primary and English rubric-code/translation logic.
- [[issue-001-haunted-house]] — first issue route/content structure.

## timeline

- time: 2026-07-08T18:55:00
  kind: decision
  summary: "Captured the article spread layout system: bilingual rubric labels, desktop/mobile spread structure, type hierarchy, plates/contact sheets/image atlas, editorial apparatus modules, Sonic Appendix playlists, three layout families, per-material permalinks, and material-specific OG cards generated from article data."
  source: conversation
  affects: [article-spread-layouts, visual-design-system, astro-publication-layer, logo-and-end-mark-system, language-architecture]
