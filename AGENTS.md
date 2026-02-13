# Jackson & Mackenzie Wedding Website — Agent Guide

AI agents working on this project: read this file first for context and conventions.

## Project Overview

A static, single-page wedding website for Jackson and Mackenzie's wedding on **June 13, 2026**. Built with Astro and Tailwind CSS, deployed to GitHub Pages. Live site: `https://jacksonandmackenzie.com`

---

## Quick Start

```bash
npm install
npm run dev      # Dev server at http://localhost:4321
npm run build    # Output to ./dist
npm run preview  # Preview production build locally
```

---

## Tech Stack

| Layer    | Technology            |
| -------- | --------------------- |
| Framework| Astro 5.x             |
| Styling  | Tailwind CSS v4       |
| Icons    | lucide-astro          |
| Hosting  | GitHub Pages          |
| Forms    | Embedded Google Form  |

---

## Project Structure

```
├── src/
│   ├── components/     # Astro components (see src/AGENTS.md)
│   ├── data/           # JSON content (bridalParty.json, faq.json)
│   ├── layouts/        # Layout.astro
│   ├── pages/          # index.astro (single page)
│   └── styles/         # global.css (Tailwind + theme)
├── public/             # Static assets (see public/AGENTS.md)
├── docs/specs/         # Specs & task proofs (see docs/AGENTS.md)
├── edit-and-notes.txt  # Content source of truth from the couple
└── .github/workflows/  # deploy.yml → GitHub Pages on push to main
```

---

## Content Source of Truth

**`edit-and-notes.txt`** — Contains couple-provided content: ceremony times (5:30 PM, arrive by 5), RSVP deadline (April 25), bridal party bios, FAQ updates, registry links, contact info, and design notes. Use this when updating copy, bios, or event details.

---

## Key Conventions

- **Single page** — All sections live in `src/pages/index.astro`, wrapped in `<Section>` components.
- **Design tokens** — Colors and fonts in `src/styles/global.css` via `@theme` (sage green, charcoal, cream).
- **Data-driven** — Bridal party and FAQ content come from `src/data/*.json`; avoid hardcoding.
- **No backend** — Static site; RSVP via embedded Google Form.

---

## Section Order (index.astro)

1. Hero 
2. Event Details 
3. RSVP 
4. Venue 
5. Our Story 
6. Bridal Party 
7. Gallery 
8. Registry 
9. FAQ 
10. Contact

---

## Deployment

- **Trigger:** Push to `main`
- **Workflow:** `.github/workflows/deploy.yml`
- **Config:** `astro.config.mjs` — `site: "https://jacksonandmackenzie.com"`, `base: "/"`, `output: "static"`

---

## Nested Guides

- **`src/AGENTS.md`** — Component patterns, data flow, styling
- **`docs/AGENTS.md`** — Spec structure, task proofs, how to extend specs
- **`public/AGENTS.md`** — Image layout, naming, asset conventions
