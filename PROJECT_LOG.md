# DIVYA JEEVAN SIDDHA ASHRAM — Project Log

## 🕉️ What Is This Project?

A complete, multilingual (English / Hindi / Odia) static website for **Divya Jivan Siddha Ashram**, a sacred spiritual institution located in Borigumma, Horadali, Koraput District, Odisha, India. The ashram preserves the ancient flame of **Brahma Vidya** through the Guru Parampara lineage, transmitting Tantric and Vedic sciences in the Atharvaveda tradition.

The website serves as the digital presence for the ashram — showcasing its practices, courses, events, shop, and providing information for seekers worldwide.

**Tech Stack:** Pure HTML + CSS + vanilla JavaScript. No frameworks, no build tools, no dependencies. Static files only.

**Design Language:** Dark, sacred aesthetic with gold accents on deep void backgrounds. Fonts: Cormorant Garamond (display), Outfit (UI body), Hind (Hindi body). Custom cursor, preloader curtain animation, scroll-reveal animations, and a language switcher (EN / हि / ଓ).

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

### Shared Infrastructure

| File | Description |
|------|-------------|
| `styles.css` | Complete design system — CSS custom properties, responsive grid, all component styles |
| `shared.js` | i18n system (EN/HI/OD), custom cursor, preloader, nav scroll, scroll-reveal, language switcher |

### Internationalization (i18n) — COMPLETE

- **3 languages:** English (EN), Hindi (हि), Odia (ଓ)
- **~900+ translation keys** across all pages in `shared.js`
- **All 18 pages** have `data-i18n` attributes on headings, descriptions, cards, tables, FAQ Q&A, quotes, and key visible text
- Language switcher works on every page — nav links, hero sections, section headings, content, footer

### Footer & Navigation

- Consistent footer across all 18 pages with proper links to:
  - Sadhana, Learn (Books, Courses, About), Join (Diksha, Membership, Volunteer, Events, Donate, Shop)
  - Legal (Privacy, Terms, Tantra Safety, Disclaimer)
- Nav logo links fixed from `#` to `index.html` on all pages
- Active nav state managed by JavaScript

### Animations & Interactions

- Custom cursor with hover states on interactive elements
- Preloader with animated flame SVG and curtain reveal
- Scroll-reveal animations via IntersectionObserver
- Language cycle animation in hero section
- WhatsApp floating button on all pages
- Filterable grids for Sadhana, Events, Courses, Shop

---

## ⏳ What Is Pending / Not Yet Completed

### Content Pages (from `more.txt` / `BOOKS.txt`)

These sections are documented in the project reference files but have **not yet been created as standalone pages**:

| Missing Page | Source | Priority |
|---|---|---|
| Books Library | `BOOKS.txt` — full book descriptions | Medium |
| Guru Parampara (detailed) | `about_content.html` covers basics | Low |
| Brahma Vidya (dedicated) | Referenced in footer/philosophy | Medium |
| Testimonials | Referenced in footer | Low |
| Media & Films | Referenced in footer | Low |
| Digital Temple | Referenced in footer | Low |
| Free eBooks | Referenced in footer | Low |
| Podcasts | Referenced in footer | Low |
| 21 Shakti Sadhanas (detailed) | `sadhana_content.html` covers overview | Medium |
| Nav Durga Practices (detailed) | Referenced in sadhana | Medium |
| Maa Kali Sadhana (detailed) | Referenced in sadhana | Medium |
| Samsan Sadhana (detailed) | Referenced in sadhana | Low |
| Agni Tattva (detailed) | Referenced in sadhana | Low |

### Technical Improvements Needed

- [ ] **Favicon** — no custom favicon.svg or .ico yet
- [ ] **Meta tags** — missing Open Graph / Twitter Card meta for social sharing
- [ ] **Structured data** — no JSON-LD schema for SEO
- [ ] **Accessibility** — ARIA labels on interactive elements, skip-to-content link
- [ ] **Form handling** — forms currently don't submit anywhere (need backend or form service like Formspree/Netlify Forms)
- [ ] **Images** — no actual ashram photographs integrated (design has placeholder patterns)
- [ ] **Performance** — no image optimization, no lazy loading
- [ ] **Analytics** — no tracking (Google Analytics, Plausible, etc.)
- [ ] **PWA / Service Worker** — not implemented
- [ ] **404 page** — not created
- [ ] **sitemap.xml** — not created
- [ ] **robots.txt** — not created

### Content Gaps

- [ ] Bank account details for donations (marked as "[To be added]")
- [ ] UPI ID (marked as "[To be added]")
- [ ] SWIFT/IBAN codes for international donors (marked as "[To be added]")
- [ ] Actual ashram photographs (currently using gradient/pattern placeholders)
- [ ] Guruji's detailed biography and photo
- [ ] Course curriculum details and schedules
- [ ] Membership welcome kit details

### Cleanup Needed

- [ ] Remove temporary patch scripts (`patch_i18n.js`, `patch_i18n_new.js`, `patch_i18n_final.js`, `patch_i18n_answers.js`, `check_i18n.js`, `update_i18n.js`)
- [ ] Remove `extract.js`, `wrap.js` (utility scripts used during development)
- [ ] Some pages have duplicate i18n keys in `shared.js` (harmless but messy)
- [ ] `divya-jivan-home.html` and `template.html` — appear to be development artifacts

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
├── styles.css              # Complete design system
├── shared.js               # i18n system + animations + nav
├── ANTIGRAVITY_MASTER_PROMPT.md  # Master design prompt
├── BOOKS.txt               # Book reference data
├── more.txt                # Additional page content reference
├── PROJECT_LOG.md          # This file
├── [temp scripts]          # patch_i18n*.js, extract.js, wrap.js, etc.
```

---

## 📊 Statistics

| Metric | Count |
|--------|-------|
| Total HTML pages | 24 (18 content + 6 content files) |
| Total CSS | 1 (`styles.css` — comprehensive design system) |
| Total JS | 1 (`shared.js` — i18n + animations) |
| Languages supported | 3 (English, Hindi, Odia) |
| i18n translation keys | ~900+ |
| Footer links | Consistent across all pages |
| Legal pages | 5 (Privacy, Terms, Tantra Safety, Disclaimer, Refund) |
| Forms | 5 (Events registration, Courses enquiry, Diksha application, Contact, Shop enquiry) |

---

## 🔧 Development Notes

- All pages follow the same template structure: loader → curtain → nav → main content → footer → WhatsApp float
- The `applyLang()` function in `shared.js` handles all language switching by replacing `innerHTML` of elements with `data-i18n` attributes
- The design uses CSS custom properties extensively (e.g., `var(--void)`, `var(--forest)`, `var(--gold)`, `var(--paper)`)
- Scroll-reveal uses IntersectionObserver with `data-r` attributes and `.on` class
- All pages are self-contained — no build step required

---

*Last updated: June 3, 2026*
*Project repository: https://github.com/jkeylight/DIVYA-JEEVAN-SIDDHA-ASHRAM*
