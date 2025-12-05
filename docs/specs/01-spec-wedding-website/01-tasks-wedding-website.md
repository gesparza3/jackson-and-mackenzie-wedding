# Task List: Jackson & Mackenzie Wedding Website

**Spec Reference:** `01-spec-wedding-website/spec.md`  
**Created:** 2024-12-04  
**Status:** Planning

---

## Spec Coverage Matrix

| User Story                        | Covered By Task |
| --------------------------------- | --------------- |
| US-1: Guest Views Wedding Details | 1.0, 3.0        |
| US-2: Guest Submits RSVP          | 4.0             |
| US-3: Guest Finds Venue Location  | 3.0             |
| US-4: Guest Views Bridal Party    | 5.0             |
| US-5: Guest Browses Photo Gallery | 5.0             |
| US-6: Guest Accesses Registry     | 6.0             |
| US-7: Guest Reads FAQ             | 6.0             |
| US-8: Guest Contacts Couple       | 6.0             |

| Functional Requirement         | Covered By Task |
| ------------------------------ | --------------- |
| FR-1: Single Page Application  | 2.0             |
| FR-2: Responsive Design        | 1.0, 2.0        |
| FR-3: Section Structure        | 2.0             |
| FR-4: Countdown Timer          | 1.0             |
| FR-5: Google Forms Integration | 4.0             |
| FR-6: Navigation               | 2.0             |
| FR-7: Image Handling           | 5.0             |

---

## Tasks

### [x] 1.0 Project Setup & Hero Section

Initialize the Astro project with Tailwind CSS and create the hero section with countdown timer. This establishes the foundation and provides the first visual demo of the site.

**Covers:** US-1 (partial), FR-2 (foundation), FR-4

#### 1.0 Proof Artifact(s)

- **Screenshot:** Hero section on desktop (1440px) showing names, date, and countdown timer
- **Screenshot:** Hero section on mobile (375px) showing responsive layout
- **CLI:** `npm run build` completes without errors
- **URL:** `http://localhost:4321` serves the dev site

#### 1.0 Tasks

- [x] 1.1 Initialize Astro project with `npm create astro@latest`
- [x] 1.2 Install and configure Tailwind CSS (`@astrojs/tailwind`)
- [x] 1.3 Install Lucide icons (`lucide-astro`)
- [x] 1.4 Configure `astro.config.mjs` for static output and GitHub Pages base path
- [x] 1.5 Set up Tailwind config with custom colors (sage green palette) and fonts
- [x] 1.6 Create `src/styles/global.css` with CSS variables and base styles
- [x] 1.7 Create `src/layouts/Layout.astro` with HTML structure, meta tags, fonts
- [x] 1.8 Create `src/components/Hero.astro` with names, date display
- [x] 1.9 Implement countdown timer component with JS (days, hours, minutes, seconds)
- [x] 1.10 Add responsive hero styling (mobile-first)
- [x] 1.11 Create `src/pages/index.astro` with Layout and Hero
- [x] 1.12 Verify dev server runs and hero displays correctly

---

### [x] 2.0 Navigation & Section Structure

Create the sticky header with navigation, mobile hamburger menu, and scaffold all 11 section containers with smooth scroll behavior.

**Covers:** FR-1, FR-2 (mobile nav), FR-3, FR-6

#### 2.0 Proof Artifact(s)

- **Screenshot:** Desktop navigation showing all section links
- **Screenshot:** Mobile hamburger menu open state
- **GIF/Video:** Smooth scroll navigation between sections
- **Test:** Navigation links scroll to correct section anchors

#### 2.0 Tasks

- [x] 2.1 Create `src/components/Header.astro` with site logo/names
- [x] 2.2 Add navigation links for all sections (Our Story, Details, RSVP, etc.)
- [x] 2.3 Implement sticky header with Tailwind (`sticky top-0`)
- [x] 2.4 Create mobile hamburger menu button with Lucide icon
- [x] 2.5 Implement mobile menu toggle with client-side JS
- [x] 2.6 Add smooth scroll CSS (`scroll-behavior: smooth`) and anchor links
- [x] 2.7 Create section wrapper component or pattern for consistent styling
- [x] 2.8 Add all 11 section containers to `index.astro` with IDs
- [x] 2.9 Style section containers with alternating backgrounds (white/cream)
- [x] 2.10 Test navigation scroll on desktop and mobile
- [x] 2.11 Add active section highlighting (optional, via Intersection Observer)

---

### [x] 3.0 Event Details, Venue & Parking Sections

Build the event schedule display, venue information with map embed, and parking instructions. These are the core informational sections guests need.

**Covers:** US-1 (complete), US-3

#### 3.0 Proof Artifact(s)

- **Screenshot:** Event Details section showing ceremony (4:00 PM) and reception (4:45 PM) times
- **Screenshot:** Venue section with address (2741 Taylor Rd, Penryn, CA 94546) and map
- **Screenshot:** Parking section with instructions
- **Test:** All sections render correctly on mobile

#### 3.0 Tasks

- [x] 3.1 Create `src/components/EventDetails.astro` component
- [x] 3.2 Display ceremony time (4:00 PM) and reception time (4:45 PM)
- [x] 3.3 Add event date (June 13, 2026) and day-of schedule
- [x] 3.4 Style with icons (clock, calendar) from Lucide
- [x] 3.5 Create `src/components/Venue.astro` component
- [x] 3.6 Display venue name (The Justice Residence) and address
- [x] 3.7 Add Google Maps embed iframe or static map image
- [x] 3.8 Add "Get Directions" link (opens Google Maps)
- [x] 3.9 Add nearby hotels section (placeholder text)
- [x] 3.10 Create `src/components/Parking.astro` component
- [x] 3.11 Add parking instructions (placeholder text)
- [x] 3.12 Ensure all three sections are responsive

---

### [~] 4.0 RSVP Section with Google Forms Integration

Implement the RSVP section with embedded Google Form iframe and fallback link. Form collects guest names, attendance count, phone, and comments.

**Covers:** US-2, FR-5

#### 4.0 Proof Artifact(s)

- **Screenshot:** RSVP section with embedded Google Form visible
- **Screenshot:** Mobile view of RSVP section with responsive iframe
- **Screenshot:** Fallback link visible below/beside form
- **Test:** Form submission captured in Google Forms spreadsheet (manual verification)

#### 4.0 Tasks

- [ ] 4.1 Create `src/components/RSVP.astro` component
- [ ] 4.2 Add section heading and intro text
- [ ] 4.3 Embed Google Form via iframe (URL to be provided)
- [ ] 4.4 Style iframe container for responsive sizing
- [ ] 4.5 Add fallback "Open RSVP Form" button/link below iframe
- [ ] 4.6 Style fallback link to open in new tab
- [ ] 4.7 Add RSVP deadline text (if applicable)
- [ ] 4.8 Test iframe display on desktop and mobile
- [ ] 4.9 Create placeholder iframe URL for development

---

### [ ] 5.0 Bridal Party & Photo Gallery Sections

Create the bridal party cards (3 bridesmaids, 3 groomsmen) with photos and bios, plus the photo gallery grid with 6 image slots. Use placeholder images initially.

**Covers:** US-4, US-5, FR-7

#### 5.0 Proof Artifact(s)

- **Screenshot:** Bridal Party section showing 6 cards in responsive grid
- **Screenshot:** Photo Gallery section showing 6 images in grid layout
- **Screenshot:** Mobile view of both sections
- **Test:** Images lazy-load correctly (Network tab shows deferred loading)

#### 5.0 Tasks

- [ ] 5.1 Create `src/data/bridalParty.json` with placeholder data (6 members)
- [ ] 5.2 Add placeholder images to `public/images/bridal-party/`
- [ ] 5.3 Create `src/components/BridalParty.astro` component
- [ ] 5.4 Create individual party member card component
- [ ] 5.5 Display 3 bridesmaids and 3 groomsmen in responsive grid
- [ ] 5.6 Include photo, name, role, and bio for each
- [ ] 5.7 Add placeholder images to `public/images/gallery/`
- [ ] 5.8 Create `src/components/Gallery.astro` component
- [ ] 5.9 Implement 6-image responsive grid layout
- [ ] 5.10 Add lazy loading to gallery images (`loading="lazy"`)
- [ ] 5.11 Style images with hover effects (optional)
- [ ] 5.12 Test both sections on mobile

---

### [ ] 6.0 Our Story, Registry, FAQ, Contact & Footer

Complete the remaining content sections: Our Story narrative, Registry links, expandable FAQ accordion, Contact information, and site footer.

**Covers:** US-6, US-7, US-8

#### 6.0 Proof Artifact(s)

- **Screenshot:** Our Story section with timeline/narrative
- **Screenshot:** Registry section with external links
- **Screenshot:** FAQ section with accordion (one expanded, one collapsed)
- **Screenshot:** Contact section and Footer
- **Test:** FAQ accordion expands/collapses correctly
- **Test:** Registry links open in new tabs

#### 6.0 Tasks

- [ ] 6.1 Create `src/components/OurStory.astro` component
- [ ] 6.2 Add placeholder narrative text (how they met, timeline)
- [ ] 6.3 Style with timeline or card layout
- [ ] 6.4 Create `src/components/Registry.astro` component
- [ ] 6.5 Add placeholder registry links (Amazon, Target, etc.)
- [ ] 6.6 Style as buttons/cards that open in new tabs
- [ ] 6.7 Create `src/data/faq.json` with placeholder Q&A items
- [ ] 6.8 Create `src/components/FAQ.astro` component
- [ ] 6.9 Implement expandable accordion with client-side JS
- [ ] 6.10 Create `src/components/Contact.astro` component
- [ ] 6.11 Add contact email (placeholder) with mailto link
- [ ] 6.12 Create `src/components/Footer.astro` component
- [ ] 6.13 Add footer with couple names and year
- [ ] 6.14 Test all sections and accordion functionality

---

### [ ] 7.0 Polish & GitHub Pages Deployment

Final styling refinements, performance optimization, and deployment to GitHub Pages. Verify all sections work on the live site.

**Covers:** NFR-1, NFR-4, Success Criteria

#### 7.0 Proof Artifact(s)

- **URL:** Live GitHub Pages URL (e.g., `https://[username].github.io/jackson-and-mackenzie-website/`)
- **Screenshot:** Full page on desktop showing all sections
- **Screenshot:** Full page on mobile showing responsive design
- **CLI:** `npm run build` produces static output in `dist/`
- **Test:** RSVP form submission works on live site

#### 7.0 Tasks

- [ ] 7.1 Review all sections for visual consistency
- [ ] 7.2 Add subtle animations/transitions (fade-in on scroll, hover states)
- [ ] 7.3 Optimize images (compress, convert to WebP if needed)
- [ ] 7.4 Run `npm run build` and verify static output
- [ ] 7.5 Test build locally with `npm run preview`
- [ ] 7.6 Create GitHub Actions workflow for deployment (`.github/workflows/deploy.yml`)
- [ ] 7.7 Configure GitHub Pages in repository settings
- [ ] 7.8 Push to main branch and trigger deployment
- [ ] 7.9 Verify live site loads correctly
- [ ] 7.10 Test RSVP form on live site
- [ ] 7.11 Test all navigation and sections on mobile device
- [ ] 7.12 Document any remaining placeholder content to replace

---

## Relevant Files

### Configuration Files

- `package.json` - Dependencies and scripts
- `astro.config.mjs` - Astro configuration with GitHub Pages settings
- `tailwind.config.mjs` - Tailwind theme with sage green palette
- `tsconfig.json` - TypeScript configuration

### Layouts & Pages

- `src/layouts/Layout.astro` - Base HTML layout
- `src/pages/index.astro` - Main single-page entry point

### Components

- `src/components/Header.astro` - Sticky navigation header
- `src/components/Hero.astro` - Hero section with countdown
- `src/components/OurStory.astro` - Relationship narrative
- `src/components/EventDetails.astro` - Ceremony/reception schedule
- `src/components/Venue.astro` - Location and map
- `src/components/Parking.astro` - Parking instructions
- `src/components/RSVP.astro` - Google Form embed
- `src/components/BridalParty.astro` - Wedding party cards
- `src/components/Gallery.astro` - Photo gallery grid
- `src/components/Registry.astro` - Gift registry links
- `src/components/FAQ.astro` - Expandable Q&A
- `src/components/Contact.astro` - Contact information
- `src/components/Footer.astro` - Site footer

### Data Files

- `src/data/bridalParty.json` - Wedding party member data
- `src/data/faq.json` - FAQ questions and answers

### Styles

- `src/styles/global.css` - Global styles and CSS variables

### Static Assets

- `public/images/hero/` - Hero background images
- `public/images/gallery/` - Couple photos (6)
- `public/images/bridal-party/` - Wedding party photos (6)
- `public/favicon.ico` - Site favicon

### Deployment

- `.github/workflows/deploy.yml` - GitHub Actions deployment workflow

---

## Notes

- **Timeline:** Target launch December 5, 2025 (tight timeline)
- **Content:** Placeholder content will be used initially; real content can be swapped in later
- **Google Form:** User needs to create/provide the Google Form URL before Task 4.0
- **Photos:** Placeholder images will be used until real photos are provided
