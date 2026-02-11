# src/ — Frontend & Components

Agent guide for working in `src/`. See root `AGENTS.md` for project overview.

---

## Component Architecture

### Section Wrapper

All content sections use `<Section>` from `Section.astro`:

```astro
<Section id="our-story" title="Our Story" subtitle="How we met" variant="cream">
  <OurStory />
</Section>
```

**Props:** `id`, `title`, `subtitle`, `variant` ("white" | "cream"), `class`

---

## Data Flow

| File | Used By |
|------|---------|
| `data/bridalParty.json` | `BridalParty.astro`, `BridalPartyCard.astro` |
| `data/faq.json` | `FAQ.astro` |

Edit JSON, not component markup, when updating bridal party or FAQ content.

---

## Design Tokens (global.css)

```css
--color-sage / --color-sage-light / --color-sage-dark
--color-cream
--color-charcoal
--color-gray
--font-heading: "Cormorant Garamond"
--font-body: "Inter"
```

Use these classes/vars for consistency. Avoid ad-hoc hex values.

---

## Key Components

| Component | Purpose |
|-----------|---------|
| `Hero` | Full-screen hero, countdown timer, parallax |
| `Section` | Reusable section wrapper with title/subtitle |
| `FloatingNav` | Sticky nav (mobile: bottom sheet) |
| `BridalParty` + `BridalPartyCard` | Bridal party grid |
| `Gallery` | Photo grid (6 images from `public/images/gallery/`) |
| `RSVP` | Embedded Google Form iframe |
| `EventDetails` | Ceremony/reception times |
| `Venue` | Address, map, parking |
| `Registry` | External registry links |
| `FAQ` | Accordion from `faq.json` |
| `Contact` | Contact info |

---

## Patterns

- **Astro components** — `.astro` files; use slots for children.
- **Client scripts** — Use `<script>` in .astro for interactivity (e.g. countdown, parallax).
- **Animations** — `fade-in`, `animate-on-scroll` in global.css; respect `prefers-reduced-motion`.
- **Accessibility** — Semantic HTML, focus styles, alt text on images.

---

## Where to Edit Content

| Content | Edit |
|---------|------|
| Bridal party | `data/bridalParty.json` |
| FAQ | `data/faq.json` |
| Event times | `EventDetails.astro` + `Hero.astro` (wedding date) |
| RSVP URL | `RSVP.astro` |
| Contact | `Contact.astro` |
| Registry links | `Registry.astro` |
| Our Story | `OurStory.astro` |
