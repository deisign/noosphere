---
id: astro-publication-layer
title: Astro static publication layer
category: project
status: active
tags: [project, astro, site]
created: "2026-07-07T23:17:55"
updated: "2026-07-07T23:22:42"
---

## compiled_truth

## Role

This is the **publication layer** of [[noosphere-concept]] — not the whole project. It renders issues; it does not decide what goes in them. The site must be **static but not static-feeling**: technically static HTML/CSS/JS with no mandatory backend, but editorially interactive (motion layer, click-triggered sound, visual spreads, the Nooscope instrument).

## Why static, why Astro

Why static: simple publishing, high speed, low technical fragility, Git-friendly (each issue is versionable), content lives in Markdown/MDX/JSON, deploys to GitHub Pages/Cloudflare Pages/Netlify/Vercel, and search/automation/CMS/n8n can be layered on later without a rewrite.

Why Astro specifically: content-first; pages assemble from Markdown/MDX; interactive components are mounted point-by-point rather than app-shell-wide; the primary output is fast static HTML; fits a magazine/archive/special-project shape better than a general SPA framework.

## Why not a CMS at the start

Ghost/WordPress/Notion-as-CMS pull the project toward their built-in model (post / date / author / category / image), but the actual content model needed is: issue / rubric / spread / visual mode / Nooscope signal / source lineage / motion mode / sound cue / final sentence. A CMS can be added later, once an issue rhythm is established — see root stack.

## Repo structure

```text
noosphere/
├── package.json
├── astro.config.mjs
├── src/
│   ├── content/issues/001/{index,signal,frequencies,multitudes,abandoned,residual-media,nooscope,night-fiction,object,residue}.md
│   ├── data/{issues.ts, nooscope-001.ts, fake-ads-001.ts}
│   ├── components/{CoverHero, IssueNav, RubricHeader, SignalTicker, NooscopePanel, SourceLineage, FakeAd, SoundToggle, NoiseCanvas, ResidueButton}.astro
│   ├── layouts/{BaseLayout, IssueLayout, RubricLayout}.astro
│   ├── pages/{index.astro, issues.astro, issue/[issue]/{index,[slug]}.astro}
│   └── styles/global.css
└── public/{assets, audio, video}
```

Rationale: `content/issues/001` holds issue text; `data` holds structural data (indices, fake ads, source lineage); `components` form a repeatable magazine system; `pages/issue/[issue]/[slug]` allows new pages without manual routing; `public/assets` holds original images/SVG/loops/sound.

## Site routes

Full sitemap: `/`, `/issues`, `/rubrics`, `/objects`, `/fiction`, `/sound`, `/nooscope`, `/reading-room`, `/broadcast`, `/about`.

Issue 001 full route set: `/issue/001`, plus `/signal`, `/frequencies`, `/multitudes`, `/abandoned`, `/residual-media`, `/nooscope`, `/night-fiction`, `/object`, `/sonic-ghosts`, `/residue`, `/reading-room` (all under `/issue/001/...`).

MVP subset (first technical prototype): `/`, `/issue/001`, `/issue/001/signal`, `/issue/001/frequencies`, `/issue/001/multitudes`, `/issue/001/abandoned`, `/issue/001/residual-media`, `/issue/001/nooscope`, `/issue/001/residue`. `night-fiction`, `object`, `sonic-ghosts`, `reading-room` are added in a second pass — see [[issue-001-haunted-house]] for content mapped to each route.

## Content model

Page frontmatter carries: `title`, `issue`, `rubric`, `slug`, `subtitle`, `ancestor` (OMNI-lineage note, e.g. "OMNI First Word, October 1978"), `mood`, `motion`, `sound`, `final_sentence`, `mvp`.

`data/issues.ts` holds issue metadata (id, title, englishTitle, theme, status, routes[]).

`data/nooscope-001.ts` holds the Domestic Haunting Index array (id, label, value, sourcePresence, currentRelevance, culturalPersistence, issueCentrality, visualSoundPotential, description) — see [[nooscope-machine]] for the scoring definitions this data implements.

## Key components

`CoverHero` (issue cover: number, title, subtitle, current signal, visual background), `IssueNav` (table-of-contents-style nav, not a generic menu), `RubricHeader` (rubric banner: FIRST WORD / CONTINUUM / MACHINE DREAMS / NOOSCOPE), `SignalTicker` (horizontal ticker for CONTINUUM), `NooscopePanel` (main signature component — indices, expandable cards, scoring), `SourceLineage` (shows the OMNI-ancestor or public-domain source behind a piece), `FakeAd` (in-universe pseudo-ad), `SoundToggle` (manual sound enable — no autoplay), `ResidueButton` (final-page click → blackout).


## timeline

- time: 2026-07-07T23:17:55
  kind: decision
  summary: "Created this page: Astro static publication layer"
  source: docs/noosphere_strategy.md
  affects: [astro-publication-layer]

- time: 2026-07-07T23:18:44
  kind: decision
  summary: "Captured Astro publication layer rationale, repo structure, full vs MVP route maps, content model, and key components from docs/noosphere_strategy.md."
  source: docs/noosphere_strategy.md
  affects: [astro-publication-layer]

- time: 2026-07-07T23:22:42
  kind: decision
  summary: "Fixed root-page slug link convention (unwrap [[stack]] to plain 'stack')."
  source: brain lint-links cleanup
  affects: [astro-publication-layer]
