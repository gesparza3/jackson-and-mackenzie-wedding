## Relevant Files

- `edit-and-notes.txt` - Source-of-truth content for timeline, schedule, RSVP, bios, FAQ, registry, and contact updates.
- `src/components/OurStory.astro` - Contains milestone timeline array and timeline section copy to align with bride-provided story content.
- `src/components/EventDetails.astro` - Owns ceremony/reception times and arrival guidance text.
- `src/components/RSVP.astro` - Owns RSVP deadline text and RSVP section messaging around the embedded form.
- `src/data/bridalParty.json` - Data source for bridesmaids and groomsmen names, bios, and image paths.
- `src/components/BridalParty.astro` - Renders bridal party data; verify updated content appears correctly in existing layout.
- `src/components/Gallery.astro` - Defines gallery image list and lightbox behavior; update ordering/placeholders and remove deprecated balloon image reference.
- `public/images/gallery/` - Stores gallery assets that should match filenames used in `Gallery.astro`.
- `src/components/Registry.astro` - Owns registry list, labels, descriptions, and destination links.
- `src/data/faq.json` - Data source for FAQ question and answer text updates.
- `src/components/FAQ.astro` - Renders FAQ data; verify tone/wording updates display correctly and accordion still works.
- `src/components/Contact.astro` - Owns contact method text and urgent contact language.
- `docs/specs/02-spec-bride-content-updates/02-spec-bride-content-updates.md` - Approved source spec to validate scope and deferrals while implementing.

### Notes

- Unit tests are not currently established for these content components; use the repository validation flow (`npm run build`) plus local preview checks.
- Keep updates within existing sections and components; do not add new public sections in this task set.
- For missing source content/assets, preserve placeholder behavior and document deferrals rather than inventing final copy.

## Tasks

### [x] 1.0 Establish content source mapping and update boundaries

#### 1.0 Proof Artifact(s)

- Diff: `docs/specs/02-spec-bride-content-updates/02-tasks-bride-content-updates.md` and implementation diffs show explicit mapping of `edit-and-notes.txt` content to existing site sections demonstrates source-of-truth alignment.
- Screenshot: Existing site section list (Our Story, Event Details, RSVP, Bridal Party, Gallery, Registry, FAQ, Contact) with update checklist demonstrates scope is limited to existing sections.
- Note: Deferred-items list (missing groomsmen sentences and missing final gallery assets) demonstrates out-of-scope deferrals are documented.

#### 1.0 Tasks

- [x] 1.1 Create a section-by-section mapping checklist from `edit-and-notes.txt` to existing site sections (Our Story, Event Details, RSVP, Bridal Party, Gallery, Registry, FAQ, Contact).
- [x] 1.2 Mark each requested update as in-scope, deferred, or pending asset/copy (including missing groomsmen sentence content and missing final gallery assets).
- [x] 1.3 Confirm no new public sections are introduced and that all changes stay inside existing content owners (`src/components/*` and `src/data/*`).
- [x] 1.4 Record unresolved items in an implementation note so future passes can complete deferred copy/assets without re-discovery.

### [x] 2.0 Update story, schedule, and RSVP content in existing sections

#### 2.0 Proof Artifact(s)

- Screenshot: Updated "Our Story" section with milestone headings/descriptions from `edit-and-notes.txt` demonstrates narrative alignment.
- Screenshot: Updated event details showing ceremony at 5:30 PM, arrival by 5:00 PM, and reception at 6:00 PM demonstrates schedule accuracy.
- Screenshot: Updated RSVP section text with April 25 deadline demonstrates RSVP requirement update.

#### 2.0 Tasks

- [x] 2.1 Update the timeline entries in `src/components/OurStory.astro` so milestone titles/descriptions reflect the latest bride-provided narrative.
- [x] 2.2 Update ceremony and reception details in `src/components/EventDetails.astro` to 5:30 PM ceremony, arrive by 5:00 PM, and 6:00 PM reception with cocktails/dinner/speeches/dancing wording.
- [x] 2.3 Update RSVP deadline text in `src/components/RSVP.astro` to April 25 and confirm surrounding section copy remains consistent with site tone.
- [x] 2.4 Run local preview and verify these three sections render without layout regressions on standard desktop/mobile widths.

### [x] 3.0 Refresh bridal party, gallery handling, and registry options

#### 3.0 Proof Artifact(s)

- Screenshot: Bridal party section with updated bride-side bios and unchanged/deferred groomsmen gaps clearly represented demonstrates scoped content update behavior.
- Screenshot: Gallery section demonstrating placeholder-compatible structure and removal/replacement handling for outdated balloon image demonstrates asset workflow compliance.
- Screenshot: Registry section includes Target, Crate & Barrel, Honeymoon Fund, and Household Fund demonstrates required registry coverage.

#### 3.0 Tasks

- [x] 3.1 Update `src/data/bridalParty.json` bridesmaid entries to match provided names/bios and keep groomsmen content in current/deferred state where final text is not yet provided.
- [x] 3.2 Verify `src/components/BridalParty.astro` displays updated data cleanly with current card layout and placeholder behavior.
- [x] 3.3 Update `src/components/Gallery.astro` image references to remove deprecated balloon image usage and keep placeholder-compatible structure for future photo drop-ins.
- [x] 3.4 Ensure `src/components/Registry.astro` includes Target, Crate & Barrel, Honeymoon Fund, and Household Fund with valid placeholder/final URLs as available.
- [x] 3.5 Confirm `public/images/gallery/` asset filenames align with gallery references and document any missing files still required from the couple.

### [x] 4.0 Standardize FAQ and contact language to bride-provided guidance

#### 4.0 Proof Artifact(s)

- Screenshot: FAQ entries for plus-one, children, arrival guidance, and indoor/outdoor ceremony reflect bride-provided facts with site-consistent tone demonstrates content standardization.
- Screenshot: Contact section shows `(916) 953-3076` as primary messaging contact demonstrates contact requirement implementation.
- Diff: `src/data/faq.json` and `src/components/Contact.astro` (or equivalent content owner files) demonstrates updates were applied in repository-standard locations.

#### 4.0 Tasks

- [x] 4.1 Update `src/data/faq.json` answers for plus-one, children, arrival timing, and indoor/outdoor ceremony details using bride-provided facts with site-consistent phrasing.
- [x] 4.2 Verify FAQ rendering and accordion interaction in `src/components/FAQ.astro` still works after content length/wording changes.
- [x] 4.3 Update `src/components/Contact.astro` to make `(916) 953-3076` the primary text contact method.
- [x] 4.4 Remove or neutralize coordinator emergency language unless finalized coordinator details are provided in source content.
- [x] 4.5 Validate FAQ and Contact copy for consistency with the rest of the website tone.

### [x] 5.0 Validate build and capture completion evidence

#### 5.0 Proof Artifact(s)

- CLI: `npm run build` completes successfully demonstrates static generation integrity after content updates.
- Screenshot set: Updated sections on local preview demonstrates end-to-end visible completion across all scoped areas.
- Checklist artifact: Completion checklist mapped to tasks 1.0-4.0 demonstrates traceability to spec units and success metrics.

#### 5.0 Tasks

- [x] 5.1 Run `npm run build` and resolve any content-related build failures or warnings introduced by updates.
- [x] 5.2 Start local preview and capture screenshots for each scoped section group: (a) Story/Event/RSVP, (b) Bridal/Gallery/Registry, (c) FAQ/Contact.
- [x] 5.3 Compile a completion checklist that maps each proof artifact to parent tasks 1.0-4.0 and to corresponding spec success metrics.
- [x] 5.4 Perform a final pass to verify no out-of-scope design or structural changes were introduced.
