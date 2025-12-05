# Specification: Jackson & Mackenzie Wedding Website

**Spec ID:** 01-spec-wedding-website  
**Created:** 2024-12-04  
**Status:** Draft  
**Target Launch:** December 5, 2025  
**Wedding Date:** June 13, 2026

---

## 1. Overview

### 1.1 Problem Statement

Jackson and Mackenzie need a wedding website to share event details, collect RSVPs, and provide guests with all necessary information for their June 2026 wedding. The site must be accessible on both desktop and mobile devices and deployable without a backend server.

### 1.2 Solution Summary

A modern, responsive single-page wedding website built with Astro, deployed to GitHub Pages. The site features a sage green, white, and black color palette with a modern/minimalist aesthetic. RSVP collection is handled via embedded Google Forms.

### 1.3 Success Criteria

- Site is live and accessible via GitHub Pages URL
- All 11 sections render correctly on desktop and mobile
- RSVP form submissions are successfully captured in Google Forms
- Page loads quickly with no server-side dependencies

---

## 2. User Stories

### US-1: Guest Views Wedding Details

**As a** wedding guest  
**I want to** view the ceremony and reception details  
**So that** I know when and where to arrive

**Acceptance Criteria:**

- Date (June 13, 2026) is prominently displayed
- Venue name and address are clearly shown
- Ceremony time (4:00 PM) and reception time (4:45 PM) are listed
- Countdown timer shows days until the wedding

### US-2: Guest Submits RSVP

**As a** wedding guest  
**I want to** submit my RSVP online  
**So that** the couple knows if I'm attending

**Acceptance Criteria:**

- Google Form is embedded on the page
- Fallback link opens form in new tab if embed fails
- Form collects: guest name(s), number attending, phone (optional), comments (optional)
- Submission confirmation is visible to user

### US-3: Guest Finds Venue Location

**As a** wedding guest  
**I want to** see the venue location and travel information  
**So that** I can plan my trip

**Acceptance Criteria:**

- Venue address displayed: 2741 Taylor Rd, Penryn, CA 94546
- Interactive or static map showing location
- Nearby hotel recommendations (if provided)
- Parking information section

### US-4: Guest Views Bridal Party

**As a** wedding guest  
**I want to** see who is in the wedding party  
**So that** I know the important people in the ceremony

**Acceptance Criteria:**

- 3 bridesmaids displayed with photos, names, and bios
- 3 groomsmen displayed with photos, names, and bios
- Placeholder images work until real photos are added

### US-5: Guest Browses Photo Gallery

**As a** wedding guest  
**I want to** view photos of the couple  
**So that** I can celebrate their relationship

**Acceptance Criteria:**

- Gallery displays up to 6 photos
- Images are responsive and load efficiently
- Placeholder images work until real photos are added

### US-6: Guest Accesses Registry

**As a** wedding guest  
**I want to** find gift registry links  
**So that** I can purchase a gift

**Acceptance Criteria:**

- Registry section with links to external registry sites
- Links open in new tabs

### US-7: Guest Reads FAQ

**As a** wedding guest  
**I want to** find answers to common questions  
**So that** I'm prepared for the event

**Acceptance Criteria:**

- FAQ section with expandable/collapsible questions
- Covers: dress code, parking, plus-ones, etc.

### US-8: Guest Contacts Couple

**As a** wedding guest  
**I want to** contact the couple with questions  
**So that** I can get help if needed

**Acceptance Criteria:**

- Contact information or method displayed
- Email link or contact form available

---

## 3. Functional Requirements

### FR-1: Single Page Application

- All content on one scrollable page
- Smooth scroll navigation between sections
- Fixed or sticky navigation header

### FR-2: Responsive Design

- Mobile-first approach
- Breakpoints for mobile (<768px), tablet (768-1024px), desktop (>1024px)
- Touch-friendly navigation on mobile
- Hamburger menu for mobile navigation

### FR-3: Section Structure

The page includes these sections in order:

| #   | Section       | Description                              |
| --- | ------------- | ---------------------------------------- |
| 1   | Hero/Landing  | Names, date, countdown timer, hero image |
| 2   | Our Story     | Relationship timeline/narrative          |
| 3   | Event Details | Ceremony & reception schedule            |
| 4   | Venue/Travel  | Address, map, travel tips                |
| 5   | Parking       | Parking instructions                     |
| 6   | RSVP          | Embedded Google Form with fallback link  |
| 7   | Bridal Party  | 6 wedding party members (3+3)            |
| 8   | Photo Gallery | 6 couple photos                          |
| 9   | Registry      | External registry links                  |
| 10  | FAQ           | Expandable Q&A                           |
| 11  | Contact       | Contact information                      |

### FR-4: Countdown Timer

- JavaScript countdown to June 13, 2026, 4:00 PM PT
- Displays days, hours, minutes, seconds
- Updates in real-time
- Shows "Today's the day!" on wedding date

### FR-5: Google Forms Integration

- Embedded iframe for Google Form
- Responsive iframe sizing
- Fallback button/link if iframe blocked
- Form fields: Guest name(s), Number attending, Phone (optional), Comments (optional)

### FR-6: Navigation

- Sticky header with section links
- Smooth scroll to sections on click
- Active section highlighting
- Mobile hamburger menu

### FR-7: Image Handling

- Lazy loading for performance
- Responsive images with srcset
- Placeholder images for development
- WebP format with fallbacks

---

## 4. Non-Functional Requirements

### NFR-1: Performance

- First Contentful Paint < 1.5s
- Largest Contentful Paint < 2.5s
- Total page weight < 3MB (excluding photos)
- Images optimized and lazy-loaded

### NFR-2: Accessibility

- WCAG 2.1 AA compliance target
- Semantic HTML structure
- Keyboard navigation support
- Sufficient color contrast (sage green on white)
- Alt text for all images

### NFR-3: Browser Support

- Chrome (last 2 versions)
- Firefox (last 2 versions)
- Safari (last 2 versions)
- Edge (last 2 versions)
- Mobile Safari and Chrome

### NFR-4: Deployment

- Static site generation via Astro
- GitHub Pages hosting
- No server-side runtime required
- Automated builds via GitHub Actions (optional)

---

## 5. Technical Considerations

### 5.1 Technology Stack

| Layer     | Technology              |
| --------- | ----------------------- |
| Framework | Astro                   |
| Styling   | Tailwind CSS            |
| Language  | TypeScript              |
| Icons     | Lucide Icons            |
| Hosting   | GitHub Pages            |
| Forms     | Google Forms (external) |

### 5.2 Project Structure

```
jackson-and-mackenzie-website/
├── src/
│   ├── components/
│   │   ├── Header.astro
│   │   ├── Hero.astro
│   │   ├── OurStory.astro
│   │   ├── EventDetails.astro
│   │   ├── Venue.astro
│   │   ├── Parking.astro
│   │   ├── RSVP.astro
│   │   ├── BridalParty.astro
│   │   ├── Gallery.astro
│   │   ├── Registry.astro
│   │   ├── FAQ.astro
│   │   ├── Contact.astro
│   │   └── Footer.astro
│   ├── layouts/
│   │   └── Layout.astro
│   ├── pages/
│   │   └── index.astro
│   ├── styles/
│   │   └── global.css
│   └── data/
│       ├── bridalParty.json
│       ├── faq.json
│       └── timeline.json
├── public/
│   ├── images/
│   │   ├── hero/
│   │   ├── gallery/
│   │   └── bridal-party/
│   └── favicon.ico
├── astro.config.mjs
├── tailwind.config.mjs
├── tsconfig.json
├── package.json
└── README.md
```

### 5.3 Design Tokens

```css
/* Color Palette */
--color-sage: #9caf88; /* Primary - Sage Green */
--color-sage-light: #b8c9a9; /* Sage Light */
--color-sage-dark: #7a8f6a; /* Sage Dark */
--color-white: #ffffff; /* Background */
--color-cream: #faf9f6; /* Off-white sections */
--color-black: #1a1a1a; /* Text */
--color-gray: #6b7280; /* Secondary text */

/* Typography */
--font-heading: "Inter", sans-serif;
--font-body: "Inter", sans-serif;

/* Spacing */
--section-padding: 5rem;
--container-max: 1200px;
```

### 5.4 Dependencies

```json
{
  "dependencies": {
    "astro": "^4.x",
    "@astrojs/tailwind": "^5.x",
    "tailwindcss": "^3.x",
    "lucide-astro": "^0.x"
  }
}
```

---

## 6. Content Requirements

### 6.1 Content to be Provided by Couple

| Content                 | Status  | Notes                      |
| ----------------------- | ------- | -------------------------- |
| Couple photos (6)       | Pending | For gallery section        |
| Bridal party photos (6) | Pending | 3 bridesmaids, 3 groomsmen |
| Bridal party bios       | Pending | Name, role, short bio      |
| "Our Story" narrative   | Pending | How they met, timeline     |
| FAQ answers             | Pending | Dress code, parking, etc.  |
| Registry links          | Pending | External URLs              |
| Contact email           | Pending | For contact section        |
| Google Form URL         | Pending | RSVP form embed URL        |
| Nearby hotels           | Pending | Optional travel info       |

### 6.2 Placeholder Content

Development will use placeholder content:

- Stock couple silhouette images
- Lorem ipsum for story text
- Sample FAQ questions
- Placeholder bridal party cards

---

## 7. Demoable Units

Each unit represents an independently testable and demonstrable feature:

### DU-1: Project Setup & Hero Section

- Astro project initialized with Tailwind
- Hero section with names, date, countdown timer
- Responsive layout foundation
- **Proof:** Screenshot of hero on desktop and mobile

### DU-2: Navigation & Section Structure

- Sticky header with navigation links
- All 11 section containers in place
- Smooth scroll between sections
- Mobile hamburger menu
- **Proof:** Video/GIF of navigation working

### DU-3: Event Details & Venue Sections

- Event schedule displayed
- Venue address and map
- Parking information
- **Proof:** Screenshot showing complete info

### DU-4: RSVP Integration

- Google Form embedded
- Fallback link working
- Responsive iframe
- **Proof:** Test submission captured in Google Forms

### DU-5: Bridal Party & Gallery

- 6 bridal party cards with placeholders
- Photo gallery with 6 image slots
- Responsive grid layouts
- **Proof:** Screenshot of both sections

### DU-6: Registry, FAQ, Contact & Footer

- Registry links section
- Expandable FAQ accordion
- Contact section
- Footer with credits
- **Proof:** Screenshot of completed sections

### DU-7: Polish & Deployment

- Final styling and animations
- Performance optimization
- GitHub Pages deployment
- **Proof:** Live GitHub Pages URL

---

## 8. Out of Scope

The following are explicitly **not** included in this spec:

- Backend server or database
- User authentication or password protection
- Custom RSVP form (using Google Forms instead)
- Guest list management
- Email notifications
- Multi-language support
- Blog or updates section
- Guestbook/comments feature
- Music/audio autoplay
- Custom domain setup (can be added later)
- SEO optimization beyond basics
- Analytics integration

---

## 9. Risks & Mitigations

| Risk                             | Impact | Mitigation                                          |
| -------------------------------- | ------ | --------------------------------------------------- |
| Photos not ready by launch       | Medium | Use high-quality placeholders; design for easy swap |
| Google Form embed blocked        | Low    | Fallback link always visible                        |
| Content not provided in time     | Medium | Launch with placeholders; iterate                   |
| Tight timeline (1 day to launch) | High   | Prioritize core sections; defer polish              |

---

## 10. Open Questions

1. **Our Story content** - Will you provide the narrative, or should I draft placeholder text?
2. **FAQ specifics** - What questions should be included? (dress code, kids, plus-ones, gifts, etc.)
3. **Registry links** - Which registries will you use?
4. **Contact method** - Email address, or prefer a contact form?
5. **Google Form** - Do you have the form created, or need help setting it up?
6. **Hero image** - Do you have a specific image, or should we use a pattern/gradient?

---

## Appendix A: Wireframe Reference

```
┌─────────────────────────────────────────┐
│  [Logo]    Nav: Story | Details | RSVP  │  ← Sticky Header
├─────────────────────────────────────────┤
│                                         │
│         JACKSON & MACKENZIE             │  ← Hero
│           June 13, 2026                 │
│        [Countdown: XX days]             │
│                                         │
├─────────────────────────────────────────┤
│           OUR STORY                     │  ← Our Story
│    [Timeline or narrative text]         │
├─────────────────────────────────────────┤
│          EVENT DETAILS                  │  ← Event Details
│   Ceremony: 4:00 PM | Reception: 4:45   │
├─────────────────────────────────────────┤
│         VENUE & TRAVEL                  │  ← Venue
│   [Map]  Address  Hotels                │
├─────────────────────────────────────────┤
│            PARKING                      │  ← Parking
│      [Parking instructions]             │
├─────────────────────────────────────────┤
│             RSVP                        │  ← RSVP
│      [Embedded Google Form]             │
├─────────────────────────────────────────┤
│         BRIDAL PARTY                    │  ← Bridal Party
│   [Card] [Card] [Card] [Card] [Card]    │
├─────────────────────────────────────────┤
│           GALLERY                       │  ← Gallery
│   [Photo grid - 6 images]               │
├─────────────────────────────────────────┤
│           REGISTRY                      │  ← Registry
│   [Registry links/buttons]              │
├─────────────────────────────────────────┤
│             FAQ                         │  ← FAQ
│   [Expandable questions]                │
├─────────────────────────────────────────┤
│           CONTACT                       │  ← Contact
│      [Contact information]              │
├─────────────────────────────────────────┤
│            Footer                       │  ← Footer
└─────────────────────────────────────────┘
```

---

## Approval

- [ ] Spec reviewed by stakeholder
- [ ] Open questions resolved
- [ ] Ready for task generation

**Next Step:** Run `/generate-task-list-from-spec` to create implementation tasks.
