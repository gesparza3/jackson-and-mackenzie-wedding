# Task 6.0 Proof Artifacts: Our Story, Registry, FAQ, Contact & Footer

**Task:** 6.0 Our Story, Registry, FAQ, Contact & Footer  
**Completed:** 2024-12-04  
**Status:** ✅ Complete

---

## CLI: npm run build

```bash
$ npm run build

> jackson-and-mackenzie-website@0.0.1 build
> astro build

20:52:41 [build] output: "static"
20:52:41 [build] mode: "static"
20:52:43 [vite] ✓ built in 1.73s
20:52:43 [build] ✓ Completed in 1.76s.

 generating static routes
20:52:43 ▶ src/pages/index.astro
20:52:43   └─ /index.html (+7ms)
20:52:43 ✓ Completed in 13ms.

20:52:43 [build] 1 page(s) built in 1.81s
20:52:43 [build] Complete!
```

**Result:** ✅ Build completes without errors

---

## Our Story Section

- [x] Timeline layout with 4 milestones
- [x] Lucide icons for each milestone (Heart, Calendar, MapPin, Sparkles)
- [x] Alternating left/right layout on desktop
- [x] Responsive mobile layout
- [x] Intro and closing text

### Timeline Events

1. Summer 2019 - First Meeting
2. Fall 2019 - First Date
3. 2020-2024 - Building Our Life Together
4. December 2024 - The Proposal

---

## Registry Section

- [x] 3 registry cards (Amazon, Target, Crate & Barrel)
- [x] External links open in new tabs
- [x] Hover effects on cards
- [x] Gift icon and intro text

---

## FAQ Section

- [x] 8 FAQ items with accordion behavior
- [x] Click to expand/collapse
- [x] Only one item open at a time
- [x] Chevron rotation animation
- [x] Accessible aria-expanded attributes

### FAQ Topics

1. Dress code
2. Plus ones
3. Children policy
4. Arrival time
5. Indoor/outdoor ceremony
6. Parking
7. Food and drinks
8. Photography policy

---

## Contact Section

- [x] Email contact with mailto link
- [x] Response time indicator
- [x] Lucide icons (Mail, MessageCircle)
- [x] Note about wedding day contact

---

## Footer

- [x] Couple names with styled ampersand
- [x] Wedding date
- [x] Heart icon
- [x] Thank you message
- [x] Copyright with dynamic year

---

## Files Created

| File                            | Purpose                   |
| ------------------------------- | ------------------------- |
| `src/components/OurStory.astro` | Timeline narrative        |
| `src/components/Registry.astro` | Gift registry links       |
| `src/data/faq.json`             | FAQ questions and answers |
| `src/components/FAQ.astro`      | Expandable accordion      |
| `src/components/Contact.astro`  | Contact information       |
| `src/components/Footer.astro`   | Site footer               |
