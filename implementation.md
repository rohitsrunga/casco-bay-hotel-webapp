# Implementation Plan

## Status
- [x] Layout.astro — mobile CB logo, nav/footer links to /experience

## Files to Modify
1. `src/layouts/Layout.astro` ✅ done
2. `src/pages/index.astro` — in progress
3. `src/pages/experience.astro` — to create

---

## index.astro Changes

### Hero / Booking Widget
- Hide `.hero-logo-wrapper` on mobile via CSS (`display: none` at ≤768px)
- Remove promo `<input>` field and `.promo-section` div entirely
- Change `.booking-details-row` from `1fr 1fr 1fr` to `1fr 1fr` (desktop), and `1fr 1fr` (mobile — rooms + adults side by side, not stacked)
- Strip promo from JS booking URL builder

### Testimonials — move below booking widget
- Delete standalone `#reviews` section (bottom of page)
- Add `.testimonials-carousel` div directly below `.booking-widget-container` inside the hero
- Desktop: horizontal row of 3 cards, full width under widget
- Mobile: auto-rotating carousel (3s interval) with prev/next arrow buttons + dot indicators
- Cards: white bg, serif italic quote, author attribution, stars

### About / Experience section
- Delete entire `<!-- Block 2: Philosophy -->` block (`.experience-block.reverse`)
- Keep Block 1 (About Us) as-is

### Rooms section
- Add a "Rooms" eyebrow/header label above the `.suites-vertical-gallery` section
  - Small section with eyebrow + h2 on the navy bg, padding

### Amenities section
- Replace the 4-column amenity grid with a consolidated single card:
  - Short descriptive paragraph (hot breakfast, free parking, 24hr shuttle, bike rentals, EV charging, WiFi)
  - Aesthetic list of 6 top amenity bullets (icons or dash prefix)
  - Styled link: "See all amenities & guest info →" linking to `/casco-bay-hotel-webapp/experience`
- Keep the photo visual on the left unchanged

### Sections to DELETE
- `<!-- Section 5: Park & Fly -->` — entire section
- `<!-- Section 6: Guest Reviews -->` — entire section (moved to hero area)
- `<!-- Section 8: Good to Know -->` — entire section

### Location section
- Change `reservations@cascobayhotel.com` → `frontdesk@cascobayhotel.com`

---

## experience.astro (new page)

### Layout
- Uses same `Layout.astro`
- Title: "Experience & FAQ | Casco Bay Hotel"
- Page header: large serif "The Experience" with subhead
- **Part 1: Amenities** (full detail)
  - Section header "Amenities"
  - 4-column grid matching existing amenity style: Wellness & Travel, In-Suite Essentials, Coastal Leisure, Modern Convenience
  - Add Park & Fly as a highlighted amenity block within Wellness & Travel
- **Part 2: Good to Know / FAQ**
  - Section header "Good to Know"
  - FAQ accordion or clean list
  - Items from existing Good to Know section, updated:
    - Pets: "We do not allow pets, with the exception of ADA service animals."
    - Park & Fly: full details (moved from homepage)
  - Clean, readable layout — not AI-feeling

### Design Principles
- Consistent with site: Cinzel/Cormorant/Inter fonts, navy/mist/coastal color palette
- Modern editorial layout — not a grid of cards
- Language matches existing site tone (direct, Maine-focused, no fluff)
- Mobile-first responsive
