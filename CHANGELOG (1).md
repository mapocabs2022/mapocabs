# mapocabs Website — Changelog

Keep this file for your own reference. Every time Claude updates index.html
or admin.html, a new entry gets added here so you always know what changed
and when — useful for checking "did my upload actually work?" (compare the
version number here to the one shown in your site's footer).

---

## v1.12 — 24 Aug 2026
- "Book on WhatsApp" now opens a confirmation form first, requiring name,
  mobile number, travel date, and travel time before the WhatsApp message
  is generated — cuts down on low-effort fake taps and means every real
  booking now includes exactly when the customer wants to travel.
- Added crm.html — a self-contained follow-up tracker (works entirely in
  the browser, no Google Sheets needed) for logging quotes given over
  phone/WhatsApp/in-person and tracking who needs a follow-up call, with
  overdue/today/upcoming sorting and a backup export/import.

## v1.11 — 24 Aug 2026
- Simplified the offer banner to work with GitHub only, no Google Sheets
  needed. It's now controlled by two lines near the top of the code:
  OFFER_ENABLED (true/false) and OFFER_BANNER_TEXT — edit, save, upload
  to GitHub, done. The Google Sheets version still works as an optional
  future upgrade, but isn't required.
- Coupon changed from MAPOGANESH to MAPOBAPPA, discount changed from 10%
  to a flat 12% off.

## v1.10 — 24 Aug 2026
- Added a Live Offer Banner — a dismissible banner at the top of the site
  that you can turn on/off and edit the text for directly from a new
  "Settings" tab in your Google Sheet, no code or re-upload needed.
- The active coupon code and discount % are now also controlled from
  that same Settings tab, so you can change promos on the fly.
- Coupon changed from MAPOTRIP to MAPOGANESH (Ganesh Chaturthi offer) —
  editable any time from the Sheet without touching the website files.
- Extended the Apps Script with a getSettings() function that
  auto-creates the Settings tab with sensible defaults on first run.

## v1.9 — 23 Aug 2026
- Added bookings.html — a Bookings Dashboard to view every enquiry and
  piece of feedback that comes in, with tabs (Enquiries / Feedback),
  status filtering (New/Confirmed/Completed/Cancelled), one-tap Call and
  WhatsApp buttons per booking, and a simple PIN lock.
- Extended the Google Apps Script (doGet + status-update action) so the
  dashboard can read bookings back out of the Sheet and update their
  status — requires redeploying the script as a new version.

## v1.8 — 23 Aug 2026
- Added an "About mapocabs" section with your founder photo, the full
  brand story you provided, and a Read more / Show less toggle so the
  page stays short until someone wants the full story.

## v1.7 — 16 Aug 2026
- Fixed search: typing "Vapi", "Daman", or "Silvassa" now returns ALL 11
  packages, including Short Rides (which previously didn't show up since
  their titles are just distance ranges with no city name).
- Added visible version number + last-updated date to the site footer.

## v1.6 — 08 Aug 2026
- Reconnected Google Sheets logging with a fresh Apps Script deployment.
- Added automatic email notifications to mapocabs@gmail.com for every new
  enquiry and every new feedback submission.

## v1.5 — 08 Aug 2026
- Updated prices from latest rate sheets:
  - Local Package: ₹1599/1999/2999 → ₹1999/2199/3199
  - Mumbai Airport one-way: → ₹2999/3999/4999
  - Mumbai Airport round trip: → ₹4799/5499/6499
  - Surat Airport one-way: → ₹2799/3799/4999
  - Surat Airport round trip: → ₹4299/5299/6299
  - Extra per-km rate: mapo ₹11→₹12/km, mapo XL ₹13→₹14/km
- Added coupon system — code MAPOTRIP shows 10% off with strikethrough
  pricing, applied consistently across search results, the carousel, the
  WhatsApp booking message, and the Google Sheets log.

## v1.4 — 07 Aug 2026
- Added "Send us an Enquiry" form (name, phone, trip, message) for
  customers without WhatsApp.
- Added floating ★ Feedback button with a star-rating popup.
- Wired both, plus every "Book on WhatsApp" click, to log into Google
  Sheets via a free Apps Script Web App (initial version).
- Provided google-apps-script.gs.txt — the code to paste into Google
  Apps Script.

## v1.3 — 06 Aug 2026
- Fixed logo not displaying — embedded it directly into index.html as a
  base64 image instead of relying on a separate logo-icon.png file, so it
  can never go missing regardless of what's uploaded alongside it.

## v1.2 — 05 Aug 2026
- Redesigned the homepage: search bar up top, "Hot Selling" quick-access
  pills (Mapo Quick Trip, Airport Transfer), and a swipeable "Trips We Do"
  carousel (ad-style cards for Statue of Unity, Trimbakeshwar, airports,
  Local Package).

## v1.1 — 04 Aug 2026
- Rebuilt the whole data model around mapocabs' real packages (read from
  uploaded spreadsheets) instead of generic point-to-point search:
  - Outstation Trips (Statue of Unity, Trimbakeshwar)
  - Local Package (8hr/80km)
  - Airport Transfer (Mumbai + Surat, one-way and round trip)
  - Short Rides (0-10/11-20/21-30/31-40 km slabs)
  - Extra per-km / per-hour overage rates
- Added brand name "mapocabs", logo, WhatsApp number, and social links.
- Rebuilt admin.html (Trip Manager) to match the new category structure.

## v1.0 — 03 Aug 2026
- Initial site: static HTML/CSS/JS, no backend, no paid APIs.
- Simple From/To search against a hardcoded trip list.
- "Book on WhatsApp" button with pre-filled message.
- admin.html — a no-code form-based tool to add/edit/delete trips and
  export the generated code to paste into index.html.
- Guidance for free hosting via GitHub Pages with a custom domain.

---

**How to read this:** the site footer always shows the current version
(e.g. "Site v1.7"). If you upload index.html to GitHub and the footer on
mapocabs.com doesn't match the latest version here, the upload didn't
take — try again.
