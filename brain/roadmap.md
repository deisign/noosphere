---
slug: roadmap
title: Roadmap
role: milestones
updated: "2026-07-07T22:55:29"
---

# Roadmap

## Milestones

**Current status (2026-07-07): actual build order departs from the strategy doc's Stage 1.** The active implementation focus is the [[n8n-editorial-machine]] (Nooscope signal pipeline), not the Astro static shell — the `n8n/` scaffold (`notes/`, `workflows/`) exists in-repo but is not yet populated. [[astro-publication-layer]] remains the publication layer and Stage 1 target, just not the current work.

The strategy doc defines six stages:

```mermaid
gantt
  title Roadmap
  dateFormat YYYY-MM-DD
  section Stage 1 — Static Shell
  Astro project, base layout, Issue 001 landing, 7 MVP pages, IssueNav, NooscopePanel, Residue blackout, responsive :s1, 2026-07-07, 14d
  section Stage 2 — Editorial Content
  Manifesto, issue thesis, FIRST WORD, 6-9 Continuum signals, Machine Dreams, Abandoned Habitats, Residual Media, Nooscope descriptions, Last Page, 3 fake ads :s2, after s1, 14d
  section Stage 3 — Visual Atmosphere
  Original cover, background loops, SVG/spectrogram assets, terminal/red-light/object renders, abandoned habitat imagery, Nooscope UI polish :s3, after s2, 14d
  section Stage 4 — Fiction Layer
  Moxon's Master translation, Crystal Egg object essay, Valdemar Reading Room note, microfiction/service-log artifact :s4, after s3, 14d
  section Stage 5 — Search + Archive
  /issues, /reading-room, /fiction, /objects, Pagefind search, tags/filters, source lineage archive :s5, after s4, 14d
  section Stage 6 — Broadcast
  Video version of the issue, OBS scenes, motion cover, lower thirds, Nooscope animation, audio broadcast :s6, after s5, 14d
```

Stage durations above are placeholders (2-week slices) — the doc gives ordering and scope, not dates.

## First practical action (per strategy doc)

Repo `noosphere`, milestone `NOOSPHERE 001 / STATIC SHELL`:

1. `npm create astro@latest`
2. base structure `src/content/issues/001`
3. `BaseLayout` / `IssueLayout` / `RubricLayout`
4. the 7 MVP pages
5. `global.css` visual system
6. `NooscopePanel` on static data
7. `ResidueButton`
8. test build
9. deploy to GitHub Pages or Cloudflare Pages

Text-writing and placeholder-graphic replacement begin only after this shell exists.

## MVP backlog scope (per strategy doc section 17)

- **Must have**: Astro static site, home, Issue 001 landing, 7 MVP routes, content data model, IssueNav, NooscopePanel, dark glossy CSS system, source lineage blocks, no copyrighted assets, deployed static build.
- **Should have**: fake ads, sound toggle, canvas noise, signal ticker, residue blackout, responsive mobile, basic SEO metadata.
- **Could have**: Pagefind search, visual archive, real audio loops, fiction page, object page, reading room, RSS feed, PDF/zine export.
- **Not now**: CMS, accounts, comments, payments, heavy 3D, complex backend, full automation without editor approval — see [[editorial-boundaries]].
