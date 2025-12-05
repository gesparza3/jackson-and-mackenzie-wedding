# Task 1.0 Proof Artifacts: Project Setup & Hero Section

**Task:** 1.0 Project Setup & Hero Section  
**Completed:** 2024-12-04  
**Status:** ✅ Complete

---

## CLI: npm run build

```bash
$ npm run build

> jackson-and-mackenzie-website@0.0.1 build
> astro build

20:42:31 [content] Syncing content
20:42:31 [content] Synced content
20:42:31 [types] Generated 93ms
20:42:31 [build] output: "static"
20:42:31 [build] mode: "static"
20:42:31 [build] directory: /Users/grantesparza/repos/jackson-and-mackenzie-website/dist/
20:42:31 [build] Collecting build info...
20:42:31 [build] ✓ Completed in 100ms.
20:42:31 [build] Building static entrypoints...
20:42:32 [vite] ✓ built in 322ms
20:42:32 [build] ✓ Completed in 343ms.

 generating static routes
20:42:32 ▶ src/pages/index.astro
20:42:32   └─ /index.html (+4ms)
20:42:32 ✓ Completed in 11ms.

20:42:32 [build] 1 page(s) built in 459ms
20:42:32 [build] Complete!
```

**Result:** ✅ Build completes without errors

---

## URL: Dev Server

```
http://localhost:4321
```

**Result:** ✅ Dev server runs and serves the site

---

## Hero Section Features Implemented

- [x] Names displayed: "Jackson & Mackenzie"
- [x] Date displayed: "June 13, 2026"
- [x] Countdown timer with days, hours, minutes, seconds
- [x] Real-time countdown updates every second
- [x] Responsive layout (mobile-first)
- [x] Sage green color palette applied
- [x] Google Fonts loaded (Cormorant Garamond, Inter)
- [x] Scroll indicator with animation

---

## Files Created

| File                        | Purpose                                   |
| --------------------------- | ----------------------------------------- |
| `astro.config.mjs`          | Astro config with GitHub Pages settings   |
| `src/styles/global.css`     | Tailwind v4 theme with sage green palette |
| `src/layouts/Layout.astro`  | Base HTML layout with fonts               |
| `src/components/Hero.astro` | Hero section with countdown timer         |
| `src/pages/index.astro`     | Main page entry point                     |

---

## Screenshots

_Note: Screenshots to be captured via browser preview at:_

- Desktop (1440px): Hero section with names, date, countdown
- Mobile (375px): Responsive hero layout
