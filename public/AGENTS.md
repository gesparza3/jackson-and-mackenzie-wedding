# public/ — Static Assets

Agent guide for working in `public/`. See root `AGENTS.md` for project overview.

---

## Directory Layout

```
public/
├── CNAME              # Custom domain (jacksonandmackenzie.com)
├── favicon.svg
└── images/
    ├── hero/          # hero-desktop.jpg, hero-mobile.jpg
    ├── gallery/       # photo-1.jpg … photo-6.jpg
    ├── bridal-party/  # Per-member images
    └── ourstory/      # college.png, etc.
```

---

## Image Conventions

| Asset | Location | Notes |
|-------|----------|-------|
| Hero | `hero/hero-desktop.jpg`, `hero-mobile.jpg` | Responsive swap |
| Gallery | `gallery/photo-1.jpg` … `photo-6.jpg` | Replace in place |
| Bridal party | `bridal-party/` | Named by person (e.g. kelsey.jpg, grant.png) |

---

## Referencing

- Paths are root-relative: `/images/gallery/photo-1.jpg`
- Use in Astro: `src="/images/..."` or `srcset` for responsive images

---

## bridalParty.json Mapping

`data/bridalParty.json` links to images via `image`:

- `/images/bridal-party/kelsey.jpg`
- `/images/bridal-party/grant.png`
- etc.

When adding new bridal party photos, place in `bridal-party/` and update the JSON.

---

## CNAME

- Used for GitHub Pages custom domain
- Do not remove unless changing hosting setup
