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

## 🔄 Updates To Be Done — Comprehensive Checklist

> **Status Legend:** 🔴 Must Fix (blocks launch) · 🟡 Should Fix (improves quality) · 🟢 Nice to Have (future enhancement)

---

### 🔴 MUST FIX — Before Website Launch

#### 1. Formspree Form ID Replacement (CRITICAL)

All 4 forms currently use a placeholder Formspree endpoint. **Forms will not work until this is fixed.**

| File | Search & Replace | New Value |
|------|-----------------|-----------|
| `events_content.html` | `YOUR_FORM_ID_HERE` | Your actual Formspree form ID |
| `courses_content.html` | `YOUR_FORM_ID_HERE` | Your actual Formspree form ID |
| `diksha_content.html` | `YOUR_FORM_ID_HERE` | Your actual Formspree form ID |
| `contact_content.html` | `YOUR_FORM_ID_HERE` | Your actual Formspree form ID |

**How to get your Formspree ID:**
1. Go to https://formspree.io/forms
2. Create a new form for each purpose (or one form for all)
3. Copy the form ID from the URL (e.g., `https://formspree.io/f/xyzabcde`)
4. Replace `YOUR_FORM_ID_HERE` in all 4 files
5. Test each form by submitting a test entry

#### 2. Payment / Donation Details (CRITICAL)

The `donate.html` page has placeholder text `[To be added]` for all payment methods. Seekers cannot donate without real details.

**Bank Transfer (India) — in `donate.html`:**
- [ ] Add Account Number
- [ ] Add IFSC Code
- [ ] Add Bank Name
- [ ] Confirm Branch: Borigumma, Odisha

**UPI / GPay / PhonePe — in `donate.html`:**
- [ ] Add UPI ID
- [ ] Add QR code image (optional)

**International Donors — in `donate.html`:**
- [ ] Add SWIFT Code
- [ ] Add IBAN (if applicable)
- [ ] Add correspondent bank details (if needed)

#### 3. 80G Tax Exemption Certificate

The `donate.html` page mentions Section 80G tax exemption but does not include:
- [ ] 80G registration number
- [ ] Trust PAN number
- [ ] Certificate copy for download (optional)

---

### 🟡 SHOULD FIX — Improve Quality & Experience

#### 4. Real Ashram Photographs

Currently all pages use CSS gradient/pattern placeholders. Replace with actual photos:

| Location | Placeholder | What Photo Needed |
|----------|-------------|-------------------|
| `index.html` hero | SVG rays pattern | Ashram entrance or diya close-up |
| `index.html` about section | Arch SVG illustration | Guruji portrait or ashram building |
| `about_content.html` | Portrait placeholder | Guruji photo (with permission) |
| `about_content.html` | Map placeholder | Google Maps embed for location |
| `courses_content.html` | Sarp Vidya hero | Course/seminar photograph |
| `contact_content.html` | Map placeholder | Google Maps embed for Borigumma |
| `diksha_content.html` | Fire image (base64) | Yagna fire photograph |
| `shop_content.html` | Book placeholder SVGs | Actual product photos |

**Image optimization checklist:**
- [ ] Resize all photos to max 1920px wide
- [ ] Compress to WebP with JPG fallback
- [ ] Add proper `alt` text in all 3 languages
- [ ] Add `loading="lazy"` to below-fold images
- [ ] Create `images/` directory and organize assets

#### 5. i18n Coverage Gaps

Some text elements on certain pages still lack `data-i18n` attributes:

| Page | Gap | Priority |
|------|-----|----------|
| `volunteer.html` | Footer tagline, location details not translated | Medium |
| `membership.html` | Price amounts, percentage labels | Low (currency is universal) |
| `donate.html` | Bank detail labels, percentage table | Medium |
| `faq.html` | Section category headings | Low |
| `privacy.html` | Legal body text (long paragraphs) | Low |
| `terms.html` | Legal body text (long paragraphs) | Low |
| `tantra-safety.html` | Danger descriptions, myth answers | Medium |
| `disclaimer.html` | Legal body text | Low |
| `refund.html` | Table cell values (refundable/non-refundable) | Low |
| `shipping.html` | Table cell values (prices, timeframes) | Low |
| All `_content.html` | Many paragraph-level texts lack `data-i18n` | Medium |

**Note:** Legal pages (Privacy, Terms, Disclaimer) have lengthy legal text. Full Hindi/Odia translation is optional — key headings and summary sentences should be translated.

#### 6. Footer Translation Gaps

Footer link text is NOT translated in Hindi/Odia on several pages. The footer uses `data-i18n` on section titles but link text like "Das Mahavidya", "Nav Durga", "Guru Parampara" etc. remain in English even when Hindi/Odia is selected.

- [ ] Add `data-i18n` to all footer link `<a>` tags
- [ ] Add corresponding Hindi/Odia translations in `shared.js`
- [ ] Consider: some proper nouns (Sanskrit terms) should remain untranslated across languages

#### 7. Form Placeholder Text Translation

Form placeholder text (e.g., "Full Name *", "Phone Number *", "Message *") is NOT translated when language switches:

- [ ] Add `data-i18n` to all `<input placeholder="...">` and `<select>` elements
- [ ] Add placeholder translations in `shared.js` for all 3 languages
- [ ] Note: `placeholder` attribute cannot use `data-i18n` directly — need JS to update placeholders

#### 8. Add `thank-you.html` to Sitemap

The new `thank-you.html` page is not listed in `sitemap.xml`.
- [ ] Add `<url>` entry to `sitemap.xml` (with `noindex` if preferred)

#### 9. Cross-Page Language Consistency

When user switches language on `index.html`, navigates to `about.html`, the language should persist. Currently works via localStorage, but verify:
- [ ] Test language persistence across ALL page transitions
- [ ] Verify footer translations persist on subpages
- [ ] Check that `lang` attribute on `<html>` updates correctly on each page

---

### 🟢 NICE TO HAVE — Future Enhancements

#### 10. Missing Content Pages (from `more.txt` / `BOOKS.txt`)

These sections are referenced in the project but not yet built:

| Missing Page | Source | Complexity | Priority |
|---|---|---|---|
| Books Library | `BOOKS.txt` — full book descriptions | Medium | Medium |
| Brahma Vidya (dedicated) | Referenced in footer/philosophy | Medium | Medium |
| Testimonials | Referenced in footer | Low | Low |
| Media & Films | Referenced in footer | Low | Low |
| Digital Temple | Referenced in footer | High | Low |
| Free eBooks | Referenced in footer | Medium | Low |
| Podcasts | Referenced in footer | Medium | Low |
| 21 Shakti Sadhanas (detailed) | `sadhana_content.html` covers overview | High | Medium |
| Nav Durga Practices (detailed) | Referenced in sadhana | Medium | Medium |
| Maa Kali Sadhana (detailed) | Referenced in sadhana | Medium | Medium |

#### 11. Performance Optimizations

- [ ] **Image optimization** — convert to WebP, add responsive `srcset`
- [ ] **Critical CSS** — inline above-fold CSS for faster FCP
- [ ] **Font loading** — add `font-display: swap` and preload key fonts
- [ ] **Minification** — minify `styles.css` and `shared.js` for production
- [ ] **Lazy loading** — add `loading="lazy"` to all below-fold images
- [ ] **DNS prefetch** — add `<link rel="dns-prefetch">` for Google Fonts and Formspree

#### 12. SEO Enhancements

- [ ] **JSON-LD structured data** — add schema.org markup for:
  - `Organization` (ashram details)
  - `LocalBusiness` (location, phone)
  - `Event` (upcoming events)
  - `Course` (course offerings)
  - `FAQPage` (FAQ page)
  - `BreadcrumbList` (all pages)
- [ ] **Google Search Console** — verify site ownership
- [ ] **Submit sitemap** to Google and Bing
- [ ] **Add `hreflang` tags** for multilingual SEO
- [ ] **Open Graph images** — create unique OG images for each page

#### 13. Analytics & Monitoring

- [ ] **Google Analytics 4** or **Plausible** (privacy-friendly) — add tracking script
- [ ] **Form submission tracking** — track which forms are submitted
- [ ] **Language usage tracking** — monitor which language is most used
- [ ] **Error monitoring** — add 404 tracking
- [ ] **Uptime monitoring** — ensure site stays available

#### 14. PWA / Offline Support

- [ ] Create `manifest.json` for PWA support
- [ ] Add service worker for offline caching
- [ ] Add "Add to Home Screen" prompt
- [ ] Cache critical assets (CSS, JS, fonts)

#### 15. Content Enrichment

- [ ] **Guruji biography** — detailed life story, photos, timeline
- [ ] **Course syllabi** — detailed curriculum for each course
- [ ] **Sadhana descriptions** — expanded descriptions for each practice
- [ ] **Event photos** — gallery from past events
- [ ] **Video content** — embedded YouTube/Vimeo for satsangs
- [ ] **Blog/News section** — regular updates from the ashram
- [ ] **Testimonials page** — student experiences and stories

#### 16. Interactive Features

- [ ] **FAQ accordion** — collapsible Q&A sections (currently flat list)
- [ ] **Event calendar** — interactive calendar with event details
- [ ] **Shop filtering** — JavaScript-based product category filtering
- [ ] **Sadhana filtering** — working filter buttons on sadhana page
- [ ] **Smooth scroll** — smooth scroll to anchor links
- [ ] **Back to top button** — appear on scroll

#### 17. Email Integration

- [ ] **Formspree email templates** — customize confirmation emails
- [ ] **Newsletter signup** — add email subscription form
- [ ] **Welcome sequence** — automated email for new subscribers
- [ ] **Donation receipt** — auto-send tax receipt for donations

#### 18. Security Hardening

- [ ] **Content Security Policy (CSP)** headers
- [ ] **X-Frame-Options** — prevent iframe embedding
- [ ] **Referrer-Policy** — control referrer information
- [ ] **Permissions-Policy** — restrict browser features
- [ ] **HTTPS enforcement** — ensure all pages load over HTTPS

---

### Priority Order for Implementation

| Step | Task | Effort | Impact |
|------|------|--------|--------|
| 1 | Replace Formspree placeholder IDs | 15 min | 🔴 Forms work |
| 2 | Add bank/UPI/SWIFT details to donate.html | 30 min | 🔴 Donations possible |
| 3 | Add 80G certificate number | 10 min | 🔴 Tax compliance |
| 4 | Add real photographs | 2-4 hours | 🟡 Visual trust |
| 5 | Fix footer link translations | 1-2 hours | 🟡 i18n completeness |
| 6 | Add form placeholder translations | 1-2 hours | 🟡 Form UX |
| 7 | Test cross-page language persistence | 30 min | 🟡 i18n reliability |
| 8 | Add JSON-LD structured data | 2-3 hours | 🟢 SEO boost |
| 9 | Add analytics tracking | 30 min | 🟢 Data insights |
| 10 | Create missing content pages | 1-2 days | 🟢 Content completeness |

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

*Last updated: June 4, 2026 (v2 — with comprehensive updates checklist)*
*Project repository: https://github.com/jkeylight/DIVYA-JEEVAN-SIDDHA-ASHRAM*
