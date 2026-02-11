# 02 Implementation Notes - Bride Content Updates

## Section Mapping Checklist

- [x] `Our Story` -> `src/components/OurStory.astro` timeline entries and intro/closing copy.
- [x] `Event Details` -> `src/components/EventDetails.astro` ceremony/reception times and arrival guidance.
- [x] `RSVP` -> `src/components/RSVP.astro` RSVP deadline copy.
- [x] `Bridal Party` -> `src/data/bridalParty.json` (rendered by `src/components/BridalParty.astro`).
- [x] `Gallery` -> `src/components/Gallery.astro` image list and ordering/removal handling.
- [x] `Registry` -> `src/components/Registry.astro` registry options and links.
- [x] `FAQ` -> `src/data/faq.json` (rendered by `src/components/FAQ.astro`).
- [x] `Contact` -> `src/components/Contact.astro` primary text contact language.

## Scope Classification

- **In Scope**
  - Our Story timeline narrative refresh from `edit-and-notes.txt`.
  - Event time updates to 5:30 PM ceremony, arrive by 5:00 PM, 6:00 PM reception.
  - RSVP deadline update to April 25.
  - Bridesmaid names/bios update to provided content.
  - Registry options include Target, Crate & Barrel, Honeymoon Fund, Household Fund.
  - FAQ updates for plus-one, children, arrival guidance, indoor/outdoor ceremony.
  - Contact text set to `(916) 953-3076`.
- **Deferred**
  - Final groomsmen sentence copy (source currently says "sentence" placeholders only).
  - Final replacement gallery asset list/filenames from couple beyond existing `photo-*.jpg` files.
- **Pending Asset/Copy**
  - Optional photo editing request for bridesmaid image ("photoshop blue dress") not handled in repo.
  - Coordinator urgent-contact details unresolved, so coordinator language is neutralized.

## Boundary Verification

- No new public sections are introduced.
- All implementation changes remain inside existing content owners in `src/components/*` and `src/data/*`.
- Existing single-page section structure in `src/pages/index.astro` remains unchanged.

## Unresolved Items for Future Pass

1. Replace deferred groomsmen placeholder bios when finalized wording is provided.
2. Replace gallery placeholders with finalized couple-provided images/filenames.
3. Add coordinator emergency details only after finalized coordinator contact is approved.

## Gallery Asset Alignment Check

- Current gallery references in `src/components/Gallery.astro`: `photo-1.jpg`, `photo-2.jpg`, `photo-4.jpg`, `photo-5.jpg`, `photo-6.jpg`.
- Current files in `public/images/gallery/` match all active references.
- Deprecated balloon image reference was removed from the active gallery list.
- Still required from couple: finalized replacement image set and filenames for future gallery updates.
