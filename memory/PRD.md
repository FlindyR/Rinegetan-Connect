# PRD — Rinegetan Connect (GMAHK Rinegetan)

## Original Problem Statement
Build Phase 1 of a production-quality digital platform for GMAHK Rinegetan ("Rinegetan Connect"), the official website foundation for a local Seventh-day Adventist church in Indonesia. Visual identity MUST follow the official Adventist Identity Guideline System (adventist.design): Creation Grid (7 columns, 7th = Sabbath column), official Church Symbol used per rules, entity identifier "GMAHK Rinegetan", Advent Sans typography (look-alike approved by user), restrained local color system, authentic Indonesian imagery, full Indonesian-language UI. Pages: /, /tentang-kami, /kegiatan, /media, /pelayanan, /sekolah-sabat, /kontak. Design tokens centralized; mobile-first responsive; accessible; performant; architecture ready for Phase 2 (Connect), Phase 3 (Digital Ministry), Phase 4 (Interactive Sabbath School), Phase 5 (PWA + push).

## User Decisions (2026-09-04)
- Content: structured sample data in frontend (`src/data/content.js`), CMS-ready shapes for Phase 2
- Imagery: curated stock photography, swappable via IMAGES map in content.js
- Typeface: free Advent Sans look-alike (Plus Jakarta Sans; stack named 'Advent Sans' first so licensed files drop in later)
- Contact: realistic placeholders for WITA region (Tondano, Minahasa, Sulawesi Utara)
- Award-worthy motion: framer-motion reveals, kinetic masked headline, editorial marquee, Lenis smooth scroll, hero parallax

## Architecture
- Frontend: React 19 + react-router-dom 7, Tailwind (brand tokens: navy/sabbath/gold/life), framer-motion 11, lenis 1.3, sonner, lucide-react
- Backend: FastAPI template unchanged (not needed for Phase 1; MongoDB available for Phase 2)
- Key modules: `data/content.js` (single source of truth), `components/identity/AdventistSymbol.jsx` (official path, unmodified geometry), `components/layout/CreationGrid.jsx` (7-col + SabbathColumn + GridGuides), sections/*, pages/*

## Personas
- Local member checking Sabbath times and events
- First-time visitor ("Saya Ingin Berkunjung")
- Seeker wanting Bible studies ("Pelajari Alkitab")
- Youth/parents exploring Pathfinder/Adventurer/Sekolah Sabat

## Implemented (2026-09-04, Phase 1)
- 7 routed pages, global nav (identity lockup, 7 links, dual CTA, full-screen mobile menu) + footer (links, contact, social, live Google Maps embed)
- Kinetic hero with masked line-by-line reveal, parallax image, visible Creation Grid guides + amber Sabbath column
- Sabbath marquee, Sabbath section (Sekolah Sabat 08.45 WITA / Ibadah Sabat), welcome, events (6, category filter), 9 departments, media previews, Pelayanan Digital Phase-3 preview cards, visit CTA
- Contact form with validation + toast (FRONTEND-ONLY, not persisted)
- Accessibility: skip link, aria labels/expanded/pressed, role=alert errors, alt text, focus-visible rings

## Backlog
- P0 (Phase 2): Rinegetan Connect member accounts, CMS-backed events/media via FastAPI + MongoDB, persist contact form
- P1 (Phase 3): Digital Ministry — Pelajari Alkitab sign-up, Permohonan Doa submission, first-visit RSVP; real church photography; licensed Advent Sans files
- P2 (Phase 4–5): Interactive Sabbath School lessons; PWA install + push notifications; dark "Sabbath mode"
- Replace placeholder contact details (phone/email/socials/maps pin) with real ones

## Next Tasks
1. Confirm real address, phone, WhatsApp, social URLs, map pin
2. Collect real congregation photos to swap into IMAGES
3. Wire contact form + prayer requests to backend (Phase 2/3 kickoff)
