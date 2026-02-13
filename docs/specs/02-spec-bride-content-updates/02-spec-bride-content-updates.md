# 02-spec-bride-content-updates.md

## Introduction/Overview

This feature updates existing wedding website content so the live site reflects the bride-provided information in `edit-and-notes.txt`. The goal is to refresh copy, schedule details, bios, FAQ language, contact details, registry options, and gallery handling without adding a redesign or major new sections. This spec ensures content updates are clear, testable, and easy to verify before publication.

## Goals

- Align all targeted website copy updates with the latest bride-provided content and tone.
- Update event details to the new ceremony/reception schedule and RSVP deadline.
- Refresh bridal party, FAQ, contact, registry, and gallery content in existing site sections.
- Preserve current site structure and repository patterns while allowing future content/image drop-ins.
- Produce clear proof artifacts (screenshots + successful build) that show updates are complete.

## User Stories

- **As a wedding guest**, I want to see the most current event schedule and RSVP expectations so that I arrive on time and respond by the deadline.
- **As a wedding guest**, I want to read updated story and bridal party details so that I better understand the couple and their wedding party.
- **As a wedding guest**, I want clear FAQ and contact guidance so that I know who to message with questions.
- **As the couple**, we want content updates to follow our provided wording and intent so that the site feels accurate and personal.
- **As the site maintainer**, I want image and content placeholders to follow existing patterns so that later updates are simple and low-risk.

## Demoable Units of Work

### Unit 1: Story and Event Content Alignment

**Purpose:** Update the narrative and core schedule details in existing sections so guests see accurate wedding-day information and updated story content.

**Functional Requirements:**
- The system shall update "Our Story" section content so milestone headings and descriptions reflect the latest timeline notes from `edit-and-notes.txt`.
- The system shall update ceremony details to show a start time of 5:30 PM and guidance to arrive by 5:00 PM.
- The system shall update reception details to show a 6:00 PM start and include cocktails, dinner, speeches, and dancing language.
- The system shall update RSVP messaging to state an RSVP deadline of April 25.
- The user shall be able to read these updates in existing sections without requiring navigation to any new page.

**Proof Artifacts:**
- Screenshot: Updated "Our Story" content demonstrates timeline notes are represented as requested.
- Screenshot: Updated event details block demonstrates ceremony/reception timing and arrival guidance.
- Screenshot: Updated RSVP copy demonstrates deadline update is visible.

### Unit 2: Bridal Party, Gallery, and Registry Refresh

**Purpose:** Refresh wedding-party and gift-related content while preserving current structure and enabling easy future image replacement.

**Functional Requirements:**
- The system shall update bridal party bios using provided bride-side content and any available approved copy for existing entries.
- The system shall defer missing groomsmen sentence content to a future update while preserving current display behavior.
- The system shall support placeholder-based gallery updates using existing image patterns and document any still-missing assets.
- The system shall remove or replace deprecated gallery content (including the balloon image) when corresponding updated assets are available.
- The system shall ensure registry options include Target, Crate & Barrel, Honeymoon Fund, and Household Fund in the registry section.

**Proof Artifacts:**
- Screenshot: Bridal party section demonstrates updated bios and preserved structure.
- Screenshot: Gallery section demonstrates placeholder-aware update behavior and removal/replacement of outdated item(s) when available.
- Screenshot: Registry section demonstrates all required registry options are present.

### Unit 3: FAQ and Contact Language Standardization

**Purpose:** Update guest guidance language in FAQ and Contact to match provided wording and tone while keeping the current site voice consistent.

**Functional Requirements:**
- The system shall update FAQ entries (including plus-one, children, arrival guidance, and indoor/outdoor ceremony details) using provided content as source text.
- The system shall preserve the site's overall tone while keeping factual content aligned with bride-provided wording.
- The system shall route guest follow-up guidance to messaging Mackenzie where specified.
- The system shall present the primary text contact number `(916) 953-3076` in the contact section.
- The system shall not add coordinator emergency contact information unless finalized coordinator details are provided.

**Proof Artifacts:**
- Screenshot: FAQ section demonstrates updated entries and revised guest guidance.
- Screenshot: Contact section demonstrates updated primary text contact details.
- Build log: `npm run build` succeeds demonstrates content updates do not break static generation.

## Non-Goals (Out of Scope)

1. [**Major visual redesign**: no full layout overhaul, rebrand, or multi-section visual rework in this spec.]
2. [**New public feature sections**: no net-new public sections (for example, adding a dedicated new timeline section) unless explicitly approved in a later spec.]
3. [**External image editing workflows**: no guaranteed Photoshop-style edits or outsourced image retouching in this update pass.]

## Design Considerations

No specific design requirements identified beyond maintaining the current visual system and section structure. Updated text should fit existing component layouts and maintain readability and tone consistency with the current website.

## Repository Standards

- Follow single-page section architecture in `src/pages/index.astro` using existing `Section` wrappers.
- Prefer data-driven updates where applicable (`src/data/bridalParty.json` and `src/data/faq.json`) rather than hardcoded duplication.
- Apply content updates in current component ownership boundaries (for example: `OurStory.astro`, `EventDetails.astro`, `Registry.astro`, `Contact.astro`, `Gallery.astro`).
- Preserve existing design tokens and style conventions from `src/styles/global.css`.
- Keep static-site constraints and build workflow intact (`npm run build`, GitHub Pages deployment on `main`).
- Treat `edit-and-notes.txt` as content source of truth for these requested updates when differences exist.

## Technical Considerations

- This is a content-focused update on an Astro static site; no backend or API additions are expected.
- Content updates should be backward-compatible with existing component structure and navigation.
- Gallery updates should use existing placeholder and asset naming patterns to simplify future image drop-ins.
- Defer incomplete source content (for example, missing groomsmen sentences or missing final image assets) with clear placeholders or documented follow-up needs.
- Ensure all modified sections continue to render correctly in local preview and production build output.

## Security Considerations

- No specific security considerations identified.
- Do not add sensitive personal data beyond intentionally published wedding contact details.
- Proof artifacts should avoid exposing any private draft links, credentials, or unpublished personal information.

## Success Metrics

1. [**Content alignment**: 100% of scoped section updates reflect bride-approved source content from `edit-and-notes.txt` (or explicitly documented deferrals).]
2. [**Verification completeness**: Screenshot proofs exist for each updated section family (story/event/RSVP, bridal+gallery+registry, FAQ+contact).]
3. [**Build reliability**: `npm run build` completes successfully with no blocking errors after updates.]

## Open Questions

1. Should "Design changes / Content changes / New sections we need" remain internal planning notes only, or should any part be surfaced publicly now?
2. What exact replacement asset filenames/paths should be used for new gallery photos when they are provided?
