# DIVYA JEEVAN SIDDHA ASHRAM — Project Log

## 🕉️ What Is This Project?

A complete, multilingual (English / Hindi / Odia) static website for **Divya Jivan Siddha Ashram**, a sacred spiritual institution located in Borigumma, Horadali, Koraput District, Odisha, India. The ashram preserves the ancient flame of **Brahma Vidya** through the Guru Parampara lineage, transmitting Tantric and Vedic sciences in the Atharvaveda tradition.

The website serves as the digital presence for the ashram — showcasing its practices, courses, events, shop, and providing information for seekers worldwide.

**Tech Stack:** Pure HTML + CSS + vanilla JavaScript. No frameworks, no build tools, no dependencies. Static files only.

**Design Language:** Dark, sacred aesthetic with gold accents on deep void backgrounds. Fonts: Cormorant Garamond (display), Outfit (UI body), Hind (Hindi body), Noto Sans Oriya (Odia body). Custom cursor, preloader curtain animation, scroll-reveal animations, and a language switcher (EN / हि / ଓ).

---

## ✅ What Has Been Accomplished

### Core Pages (8 main pages with content files)

| Page | File | Description |
|------|------|-------------|
| Home | `index.html` | Landing page with hero, stats, sadhana/events/books highlights, CTA |
| About | `about.html` + `about_content.html` | Guruji, Guru Parampara lineage, philosophy, mission, location |
| Sadhana | `sadhana.html` + `sadhana_content.html` | 15 sadhana practices with filterable cards |
| Events | `events.html` + `events_content.html` | Sacred calendar, featured gathering, event list, registration form |
| Courses | `courses.html` + `courses_content.html` | 6 course programmes, featured Sarp Vidya, enquiry form |
| Diksha | `diksha.html` + `diksha_content.html` | What is Diksha, levels, eligibility, code of conduct, application form |
| Shop | `shop.html` + `shop_content.html` | Books, Yantras, Rudraksha, Ritual items with filterable grid |
| Contact | `contact.html` + `contact_content.html` | Ashram details, address, phone, contact form |

### Utility / Legal Pages (10 pages)

| Page | File | Description |
|------|------|-------------|
| Donate | `donate.html` | Payment methods, where donations go, tax exemption (80G) |
| Volunteer | `volunteer.html` | Physical, digital, and professional seva opportunities |
| Membership | `membership.html` | 4-tier membership (Deepam, Jyoti, Agni, Guru Dakshina) + Lifetime |
| FAQ | `faq.html` | General, Learning, Membership, Diksha sections with Q&A |
| Privacy Policy | `privacy.html` | Data collection, usage, security, cookies, rights |
| Terms & Conditions | `terms.html` | Donations, courses, website use, visits, liability |
| Tantra Safety | `tantra-safety.html` | Dangers, signs, myths vs facts, emergency contact |
| Disclaimer | `disclaimer.html` | No medical claims, no guarantees, no liability |
| Refund Policy | `refund.html` | Donations, courses, books refund rules |
| Shipping Policy | `shipping.html` | Domestic/international shipping rates, processing times |

### Special Pages

| Page | File | Description |
|------|------|-------------|
| 404 Error | `404.html` | Custom 404 page matching site design with i18n support |
| Thank You | `thank-you.html` | Form submission confirmation page (NEW) |

### Shared Infrastructure

| File | Description |
|------|-------------|
| `styles.css` | Complete design system — CSS custom properties, responsive grid, all component styles, `.lang-od` Odia font rules |
| `shared.js` | i18n system (EN/HI/OD), custom cursor, preloader, nav scroll, scroll-reveal, language switcher, localStorage persistence, scanI18n utility |
| `favicon.svg` | SVG flame logo favicon matching the site's sacred branding |

### SEO & Discoverability

| File | Description |
|------|-------------|
| `robots.txt` | Standard robots.txt allowing all crawlers, pointing to sitemap |
| `sitemap.xml` | XML sitemap with all pages listed |

**All HTML pages** include:
- Open Graph meta tags (og:title, og:description, og:type, og:url)
- Twitter Card meta tags
- Canonical URLs
- Proper page titles and meta descriptions
- `<link rel="icon" type="image/svg+xml" href="favicon.svg">`

### Accessibility

**All HTML pages** include:
- Skip-to-content link (`.skip-link`) — visible on keyboard focus
- ARIA labels on `<nav>` (\"Primary navigation\") and `<footer>` (\"Site footer\")
- `role=\"main\"` and `aria-label=\"Main content\"` on main content area
- `lang=\"en\"` attribute on `<html>` element
- Skip-nav i18n keys in all 3 languages (EN: \"Skip to content\", HI: \"मुख्य सामग्री पर जाएं\", OD: \"ମୁଖ୍ୟ ବିଷୟବସ୍ତୁକୁ ଯାନ୍ତୁ\")

### Internationalization (i18n) — COMPLETE ✅

**Last updated: June 4, 2026 — Full i18n system now operational across all pages.**

- **3 languages:** English (EN), Hindi (हि), Odia (ଓ)
- **1,150+ translation keys** across all pages in `shared.js`
- **All 19+ pages** have `data-i18n` attributes on headings, descriptions, cards, tables, FAQ Q&A, quotes, form labels, and key visible text
- Language switcher works on every page — nav links, hero sections, section headings, content, footer
- **Language persistence:** Selected language saved to `localStorage` (`djsa-lang`) and restored on page load via `DOMContentLoaded`
- **Odia font rendering:** `body.lang-od` class toggled when Odia is selected, applying `Noto Sans Oriya` font via Google Fonts
- **Dynamic content scanning:** `scanI18n(container)` utility available for re-translating dynamically loaded content
- **Hero language cycle:** Respects saved language — starts cycling from the user's chosen language

#### i18n Architecture

```
shared.js
├── i18n.en { ... }    — English translations
├── i18n.hi { ... }    — Hindi translations  
├── i18n.od { ... }    — Odia translations
├── applyLang(lang, root) — Translates all [data-i18n] elements
│   ├── Saves to localStorage
│   ├── Toggles body.lang-od class
│   ├── Updates HTML lang attribute
│   └── Scans root container (default: document)
├── scanI18n(container) — Utility wrapper for dynamic content
└── DOMContentLoaded   — Restores saved language on page load
```

### Footer & Navigation

- Consistent footer across all pages with proper links to:
  - Sadhana, Learn (Books, Courses, About), Join (Diksha, Membership, Volunteer, Events, Donate, Shop)
  - Legal (Privacy, Terms, Tantra Safety, Disclaimer)
- Nav logo links fixed from `#` to `index.html` on all pages
- Active nav state managed by JavaScript
- **Duplicate data-i18n attributes cleaned up** across all HTML files

### Animations & Interactions

- Custom cursor with hover states on interactive elements
- Preloader with animated flame SVG and curtain reveal
- Scroll-reveal animations via IntersectionObserver
- Language cycle animation in hero section (respects saved language)
- WhatsApp floating button on all pages
- Filterable grids for Sadhana, Events, Courses, Shop

### Form Backends — Formspree Integration ✅

**Last updated: June 4, 2026 — All 4 forms connected to Formspree.**

| Form | File | Formspree ID Field |
|------|------|-------------------|
| Event Registration | `events_content.html` | `event-registration` |
| Course Enquiry | `courses_content.html` | `course-enquiry` |
| Diksha Application | `diksha_content.html` | `diksha-application` |
| Contact Message | `contact_content.html` | `contact-message` |

Each form includes:
- `action` attribute pointing to Formspree endpoint
- `method="POST"` 
- Hidden `_subject` field with descriptive email subject
- Hidden `_next` field redirecting to `thank-you.html`
- Hidden `_form` field for form identification in Formspree dashboard
- JavaScript handler with loading state, success animation, and error handling
- **⚠️ ACTION REQUIRED:** Replace `YOUR_FORM_ID_HERE` with your actual Formspree form ID in all 4 content files. Get your ID at https://formspree.io/forms

### Browser-Tested Features

- ✅ Language switching (EN → HI → OD → EN) works correctly on `index.html`
- ✅ Language persistence across page refreshes
- ✅ No JavaScript console errors
- ✅ All `data-i18n` attributes applied correctly
- ✅ `shared.js` validates as correct JavaScript

---

## ⏳ What Is Pending / Not Yet Completed

### Content Pages (from `more.txt` / `BOOKS.txt`)

These sections are documented in the project reference files but have **not yet been created as standalone pages**:

| Missing Page | Source | Priority |
|---|---|---|
| Books Library | `BOOKS.txt` — full book descriptions | Medium |
| Brahma Vidya (dedicated) | Referenced in footer/philosophy | Medium |
| Testimonials | Referenced in footer | Low |
| Media & Films | Referenced in footer | Low |
| Digital Temple | Referenced in footer | Low |
| Free eBooks | Referenced in footer | Low |
| Podcasts | Referenced in footer | Low |
| 21 Shakti Sadhanas (detailed) | `sadhana_content.html` covers overview | Medium |
| Nav Durga Practices (detailed) | Referenced in sadhana | Medium |
| Maa Kali Sadhana (detailed) | Referenced in sadhana | Medium |

### Technical Improvements Needed

- [ ] **Replace Formspree placeholder** — change `YOUR_FORM_ID_HERE` to actual form ID in all 4 content files
- [ ] **Images** — no actual ashram photographs integrated (design has placeholder patterns)
- [ ] **Performance** — no image optimization, no lazy loading beyond basic
- [ ] **Analytics** — no tracking (Google Analytics, Plausible, etc.)
- [ ] **Structured data** — no JSON-LD schema for SEO
- [ ] **PWA / Service Worker** — not implemented

### Content Gaps

- [ ] Bank account details for donations (marked as \"[To be added]\")
- [ ] UPI ID (marked as \"[To be added]\")
- [ ] SWIFT/IBAN codes for international donors (marked as \"[To be added]\")
- [ ] Actual ashram photographs (currently using gradient/pattern placeholders)
- [ ] Guruji's detailed biography and photo
- [ ] Course curriculum details and schedules
- [ ] Membership welcome kit details

---

## 📁 Project File Structure

```
├── index.html              # Home page
├── about.html              # About page
├── about_content.html      # About content (included by about.html)
├── sadhana.html            # Sadhana practices page
├── sadhana_content.html    # Sadhana content
├── events.html             # Events & calendar page
├── events_content.html     # Events content
├── courses.html            # Courses page
├── courses_content.html    # Courses content
├── diksha.html             # Diksha/initiation page
├── diksha_content.html     # Diksha content
├── shop.html               # Sacred store page
├── shop_content.html       # Shop content
├── contact.html            # Contact page
├── contact_content.html    # Contact content
├── donate.html             # Donation page
├── volunteer.html          # Volunteer page
├── membership.html         # Membership page
├── faq.html                # FAQ page
├── privacy.html            # Privacy Policy
├── terms.html              # Terms & Conditions
├── tantra-safety.html      # Tantra Safety page
├── disclaimer.html         # Disclaimer
├── refund.html             # Refund Policy
├── shipping.html           # Shipping Policy
├── 404.html                # Custom 404 error page
├── thank-you.html          # Form submission confirmation (NEW)
├── favicon.svg             # SVG flame logo favicon
├── styles.css              # Complete design system
├── shared.js               # i18n system + animations + nav + Formspree handler
├── robots.txt              # Search engine crawler instructions
├── sitemap.xml             # XML sitemap for SEO
├── ANTIGRAVITY_MASTER_PROMPT.md  # Master design prompt
├── BOOKS.txt               # Book reference data
├── more.txt                # Additional page content reference
├── PROJECT_LOG.md          # This file
```

---

## 📊 Statistics

| Metric | Count |
|--------|-------|
| Total HTML pages | 26 (19 content + 7 content files) |
| Total CSS | 1 (`styles.css` — comprehensive design system) |
| Total JS | 1 (`shared.js` — i18n + animations + form handling) |
| Languages supported | 3 (English, Hindi, Odia) |
| i18n translation keys | 1,150+ |
| Footer links | Consistent across all pages |
| Legal pages | 5 (Privacy, Terms, Tantra Safety, Disclaimer, Refund) |
| Forms with backends | 4 (Events, Courses, Diksha, Contact — via Formspree) |
| Forms without backends | 1 (Shop — WhatsApp enquiry only) |
| Accessibility features | Skip-to-content, ARIA labels, lang attribute, roles |

---

## 🔧 Development Notes

- All pages follow the same template structure: loader → curtain → nav → main content → footer → WhatsApp float
- The `applyLang(lang, root)` function in `shared.js` handles all language switching by replacing `innerHTML` of elements with `data-i18n` attributes. The optional `root` parameter allows scanning specific containers for dynamically loaded content.
- The design uses CSS custom properties extensively (e.g., `var(--void)`, `var(--forest)`, `var(--gold)`, `var(--paper)`)
- Scroll-reveal uses IntersectionObserver with `data-r` attributes and `.on` class
- All pages are self-contained — no build step required
- **Formspree forms** use `fetch()` API with error handling and redirect to `thank-you.html` on success
- **Language persistence** uses `localStorage` key `djsa-lang` with values `en`, `hi`, or `od`
- **Odia font** loaded via Google Fonts: `Noto Sans Oriya` (weights 300–600)
- Hero language cycle starts from the user's saved language and rotates every 4 seconds

### Git Commits (Recent)

| Commit | Date | Description |
|--------|------|-------------|
| `5553602` | June 4, 2026 | feat: add Formspree form backends and thank-you page |
| `9e7dfd8` | June 4, 2026 | feat: complete multilingual i18n - localStorage, Odia font, 200+ keys, hero cycle fix |
| `6422a9f` | June 3, 2026 | Add accessibility, SEO, favicon, 404 page, and i18n completion |

---

*Last updated: June 4, 2026*
*Project repository: https://github.com/jkeylight/DIVYA-JEEVAN-SIDDHA-ASHRAM*
