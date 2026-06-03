# DIVYA JIVAN SIDDHA ASHRAM — FULL WEBSITE BUILD PROMPT
## For: Google Antigravity / Vibe Coding Session
## Project: Production-ready multi-page spiritual ashram website

---

## OVERVIEW

Build a complete, production-ready website for **Divya Jivan Siddha Ashram** — an ancient Tantric and Vedic science centre in Borigumma, Horadali, Odisha, India. The site preserves and transmits the flame of **Brahma Vidya** through authentic Guru-to-Shishya lineage.

**Tagline:** *Preserving the ancient flame of Brahma Vidya*
**Phone:** +91 8260437455
**Location:** Borigumma, Horadali, Odisha, India

---

## TECH STACK — EXACT

```
Vite 5 (build tool)
React 18 (UI framework)
React Router v6 (routing)
GSAP 3 + ScrollTrigger (all animations)
Lenis (smooth scroll)
i18next + react-i18next (EN / Hindi / Odia trilingual)
Tailwind CSS v3 (utility classes, custom config)
Framer Motion (page transitions)
Vite PWA plugin (offline support)
```

**Install command:**
```bash
npm create vite@latest divya-jivan-ashram -- --template react
cd divya-jivan-ashram
npm install gsap @gsap/react lenis i18next react-i18next react-router-dom framer-motion
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
```

---

## FOLDER STRUCTURE — EXACT

```
divya-jivan-ashram/
├── public/
│   ├── favicon.ico
│   ├── logo-transparent.png          ← diya logo (transparent bg)
│   ├── images/
│   │   ├── fire.jpg                  ← sacred yagna fire (for Diksha section)
│   │   ├── hero-bg.jpg               ← dark temple interior
│   │   ├── guruji.jpg                ← Guruji portrait placeholder
│   │   ├── ashram.jpg                ← ashram exterior
│   │   └── books/
│   │       ├── book-sadhana.jpg
│   │       ├── book-brahma.jpg
│   │       ├── book-itar.jpg
│   │       └── book-21devi.jpg
│   └── fonts/                        ← self-hosted fallback fonts
│
├── src/
│   ├── main.jsx                      ← Vite entry, Lenis init, i18n init
│   ├── App.jsx                       ← Router, page transitions wrapper
│   │
│   ├── styles/
│   │   ├── globals.css               ← CSS variables, base reset, grain texture
│   │   └── fonts.css                 ← Google Fonts imports
│   │
│   ├── tokens/
│   │   └── design.js                 ← All design tokens as JS constants
│   │
│   ├── i18n/
│   │   ├── index.js                  ← i18next config
│   │   └── locales/
│   │       ├── en.json               ← English strings
│   │       ├── hi.json               ← Hindi strings (Devanagari)
│   │       └── od.json               ← Odia strings
│   │
│   ├── components/
│   │   ├── layout/
│   │   │   ├── Nav.jsx               ← Fixed nav, 3-col grid, lang switcher
│   │   │   ├── Footer.jsx            ← 3-col footer, gold on void
│   │   │   └── PageWrapper.jsx       ← Framer Motion page transition
│   │   │
│   │   ├── preloader/
│   │   │   ├── Preloader.jsx         ← Full cinematic entry sequence
│   │   │   ├── DiyaSVG.jsx           ← Animated transparent diya SVG
│   │   │   ├── CurtainDoors.jsx      ← Temple door open animation
│   │   │   └── Preloader.css
│   │   │
│   │   ├── ui/
│   │   │   ├── Cursor.jsx            ← Custom gold cursor + ring
│   │   │   ├── ScrollReveal.jsx      ← GSAP ScrollTrigger wrapper
│   │   │   ├── GoldDivider.jsx       ← — ASHRAM — style divider
│   │   │   ├── ArchFrame.jsx         ← Reusable arch SVG frame
│   │   │   ├── GrainOverlay.jsx      ← Fixed noise texture layer
│   │   │   ├── LangSwitcher.jsx      ← EN · हि · ଓ toggle
│   │   │   ├── Badge.jsx             ← Event/course type badge
│   │   │   └── Ticker.jsx            ← Horizontal scrolling text strip
│   │   │
│   │   └── sections/
│   │       ├── Hero.jsx
│   │       ├── AboutStrip.jsx
│   │       ├── Sadhanas.jsx
│   │       ├── Events.jsx
│   │       ├── Books.jsx
│   │       ├── DikshaCTA.jsx         ← fire.jpg full-bleed section
│   │       └── Courses.jsx
│   │
│   └── pages/
│       ├── Home.jsx
│       ├── About.jsx
│       ├── Sadhana.jsx
│       ├── Events.jsx
│       ├── Courses.jsx
│       ├── Diksha.jsx
│       ├── Shop.jsx
│       └── Contact.jsx
│
├── tailwind.config.js                ← Custom design tokens
├── vite.config.js
├── index.html
└── package.json
```

---

## DESIGN SYSTEM — EXACT TOKENS

### CSS Variables (globals.css)
```css
:root {
  /* Backgrounds */
  --void:    #0A0805;   /* near-black — hero, footer, preloader */
  --forest:  #3D4A35;   /* deep olive — about, events sections */
  --ash:     #1E2419;   /* dark green panel — cards on forest bg */
  --smoke:   #1A130C;   /* dark brown — cards on void bg */

  /* Gold palette — from logo */
  --gold:    #C4A96B;   /* primary gold — all accents */
  --gold-b:  #E2C97E;   /* bright gold — hover states */
  --gold-d:  #7A6640;   /* dim gold — borders, dividers */
  --gold-g:  #8A9A72;   /* olive-gold — green section accents */

  /* Text */
  --paper:   #F5EDD8;   /* warm cream — body text on dark */
  --muted:   rgba(245,237,216,0.45);
  --border:  rgba(196,169,107,0.18);
  --ghost:   rgba(196,169,107,0.06);
  --signal:  #AE431E;   /* burnt sienna — CTAs only */

  /* Typography */
  --display: 'Cormorant Garamond', serif;   /* headings */
  --sc:      'Cormorant SC', serif;          /* small caps labels */
  --body:    'Hind', sans-serif;             /* body — works for Hindi/Odia */
  --ui:      'Outfit', sans-serif;           /* nav, labels, UI */

  /* Type scale */
  --xs:   clamp(.7rem,  1.1vw, .8rem);
  --sm:   clamp(.85rem, 1.5vw, .95rem);
  --base: clamp(1rem,   1.8vw, 1.1rem);
  --md:   clamp(1.1rem, 2.2vw, 1.35rem);
  --lg:   clamp(1.4rem, 3vw,   2rem);
  --xl:   clamp(2rem,   5vw,   3.5rem);
  --hero: clamp(3.5rem, 10vw,  9rem);

  /* Easing */
  --expo: cubic-bezier(.16,1,.3,1);
  --circ: cubic-bezier(.85,0,.15,1);
}
```

### Tailwind Config
```js
// tailwind.config.js
module.exports = {
  content: ['./src/**/*.{js,jsx}'],
  theme: {
    extend: {
      colors: {
        void: '#0A0805',
        forest: '#3D4A35',
        ash: '#1E2419',
        gold: '#C4A96B',
        'gold-bright': '#E2C97E',
        'gold-dim': '#7A6640',
        paper: '#F5EDD8',
        signal: '#AE431E',
      },
      fontFamily: {
        display: ['Cormorant Garamond', 'serif'],
        sc: ['Cormorant SC', 'serif'],
        body: ['Hind', 'sans-serif'],
        ui: ['Outfit', 'sans-serif'],
      },
    },
  },
}
```

---

## GOOGLE FONTS (load in index.html)
```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;0,700;1,300;1,400;1,600&family=Cormorant+SC:wght@300;400;600&family=Hind:wght@300;400;500&family=Outfit:wght@200;300;400;500&display=swap" rel="stylesheet">
```

---

## TRILINGUAL CONTENT — ALL STRINGS

### English (en.json)
```json
{
  "nav": {
    "home": "Home",
    "about": "About",
    "sadhana": "Sadhana",
    "events": "Events",
    "courses": "Courses",
    "diksha": "Diksha",
    "shop": "Shop",
    "contact": "Contact"
  },
  "hero": {
    "eyebrow": "Borigumma · Horadali · Odisha",
    "name": "DIVYA",
    "ashram": "Jivan Siddha Ashram",
    "brahma": "Brahma Vidya",
    "tagline": "Preserving the ancient flame of",
    "cta1": "Explore Sadhanas",
    "cta2": "Seek Initiation",
    "scroll": "Scroll"
  },
  "about": {
    "eyebrow": "The Lineage",
    "heading": "Ancient Roots. Living Wisdom.",
    "body1": "Divya Jivan Siddha Ashram, nestled in Borigumma, Horadali, Odisha, is a living repository of Tantric and Vedic sciences — where unbroken Guru Parampara ensures authentic transmission of rare and powerful Sadhanas.",
    "body2": "Drawing from the Atharvaveda and the deepest esoteric traditions, the centre offers Sadhanas for spiritual growth, Tantric healing, deity initiation, and rare sciences available nowhere else — all through proper disciplic succession.",
    "stat1_n": "10", "stat1_l": "Mahavidyas",
    "stat2_n": "3yr", "stat2_l": "Sarp Vidya",
    "stat3_n": "16", "stat3_l": "Sanskar Vidhi",
    "stat4_n": "Nav", "stat4_l": "Durga Kriyas"
  },
  "sadhanas": {
    "eyebrow": "Sacred Practices",
    "heading": "The Sadhanas",
    "lead": "Each Sadhana is a complete path — a precise, time-tested method to awaken direct experience of the divine.",
    "cards": [
      {
        "num": "01", "icon": "🔱",
        "name": "Das Mahavidya Sadhana",
        "desc": "Collective practice of all ten primary Tantric goddesses — the complete mandala of Shakti in her ten supreme forms.",
        "level": "Advanced", "deity": "Dasha Mahavidya"
      },
      {
        "num": "02", "icon": "🌙",
        "name": "Maa Kali Pratyaksh Sadhana",
        "desc": "Night Sadhana and Full Siddhi Kriya for direct vision of Maa Kali — secret applications and the sacred mysteries of Kali's grace.",
        "level": "Advanced", "deity": "Maa Kali"
      },
      {
        "num": "03", "icon": "🌸",
        "name": "Nav Durga Sadhana",
        "desc": "Focused one-day Sadhanas for each of the nine forms of Durga, including Pratyaksh Darshan and rapid Siddhi practices during Navratri.",
        "level": "Intermediate", "deity": "Nav Durga"
      },
      {
        "num": "04", "icon": "🪬",
        "name": "Samsan Sadhana",
        "desc": "Three-day Cemetery practice for attaining specific results — among the most potent and rarely transmitted Tantric methods.",
        "level": "Rare · Restricted", "deity": "Samsan Kriya"
      },
      {
        "num": "05", "icon": "🔥",
        "name": "Agni Tattva Sadhana",
        "desc": "Fire element practice drawn from the Atharvaveda — for burning accumulated sin, treating bodily disease, and purifying the subtle body.",
        "level": "All Levels", "deity": "Atharvaveda"
      },
      {
        "num": "06", "icon": "🐍",
        "name": "Sarp Vidya — Naga Science",
        "desc": "A comprehensive three-year course in serpent science — rare, complete, transmitted through the unbroken living Guru lineage of the ashram.",
        "level": "3-Year Course", "deity": "Naga Vidya"
      },
      {
        "num": "07", "icon": "🌿",
        "name": "Brahma Vidya",
        "desc": "Direct teaching of Brahman and Atman — the supreme non-dual science. Vedic prayers for longevity, wealth, protection, and safe childbirth.",
        "level": "All Levels", "deity": "Brahma Vidya"
      }
    ]
  },
  "events": {
    "eyebrow": "Sacred Calendar",
    "heading": "Upcoming Gatherings",
    "lead": "Initiations, Sadhana camps, and healing sessions open to sincere seekers — by prior contact only.",
    "call": "Call Ashram: 8260437455",
    "items": [
      {
        "day": "19", "month": "Mar '26",
        "title": "Navratri Sadhana Camp",
        "sub": "Nine days · Nav Durga practices · March 19–27, 2026",
        "badge": "Free"
      },
      {
        "day": "26", "month": "Sep '25",
        "title": "Sarp Vidya Gathering",
        "sub": "Full three-year course material transmitted in one sacred day",
        "badge": "Diksha"
      },
      {
        "day": "◆", "month": "Ongoing",
        "title": "Vaishnav Diksha",
        "sub": "Initiation ceremonies — by appointment with Guruji",
        "badge": "Initiation"
      },
      {
        "day": "◆", "month": "Ongoing",
        "title": "Tantra Kat & Healing",
        "sub": "Black magic removal · Piliya Utar Kriya · Spiritual treatment",
        "badge": "Healing"
      },
      {
        "day": "◆", "month": "Seasonal",
        "title": "Maha Yagna & Chatur Veda",
        "sub": "Sacred fire ceremonies and Vedic recitation camps",
        "badge": "Yagna"
      }
    ]
  },
  "books": {
    "eyebrow": "Sacred Library",
    "heading": "From the Archives",
    "cta": "View All Books",
    "items": [
      {
        "tag": "Sadhana",
        "title": "21 Devi Sadhana",
        "subtitle": "Complete practices for 21 goddess forms",
        "langs": ["EN", "HI"]
      },
      {
        "tag": "Brahma Vidya",
        "title": "Brahma Vidya — The Supreme Science",
        "subtitle": "Non-dual wisdom and Vedic prayer",
        "langs": ["EN", "HI", "OD"]
      },
      {
        "tag": "Esoteric",
        "title": "Itar Yoni Sadhana",
        "subtitle": "Rare esoteric practices of the tradition",
        "langs": ["HI"]
      },
      {
        "tag": "Vedic",
        "title": "Sadhana Aur Sadhak",
        "subtitle": "The seeker and the path — a guide",
        "langs": ["HI", "OD"]
      }
    ]
  },
  "diksha": {
    "eyebrow": "Seek the Sacred Flame",
    "heading": "Initiation is not a ceremony —\nit is a transmission.",
    "body": "The flame of Brahma Vidya is passed from Guru to Shishya, as it has been since the beginning. To receive Diksha is to enter an unbroken chain of living wisdom that stretches back to the origin of time.",
    "cta1": "Apply for Diksha",
    "cta2": "Learn About Initiation"
  },
  "courses": {
    "eyebrow": "Paths of Knowledge",
    "heading": "Vidya & Courses",
    "lead": "Each tradition transmitted Guru to Shishya — as it has been for thousands of years.",
    "items": [
      {
        "tag": "3-Year Programme",
        "name": "Sarp Vidya — Serpent Science",
        "desc": "The ancient complete science of Naga wisdom — mantra, sadhana, and the full corpus of serpent knowledge transmitted across three years of committed practice.",
        "duration": "3 Years", "mode": "On-site", "level": "All Levels"
      },
      {
        "tag": "Initiation Course",
        "name": "Tantra Vidya & Diksha",
        "desc": "Complete initiation into Tantra — Sabar Mantra, Agama practices, Aghor and Karna Pishacha vidyas for deeply qualified and sincere seekers.",
        "duration": "Duration Varies", "mode": "On-site", "level": "Advanced"
      },
      {
        "tag": "Vedic Science",
        "name": "Atharvaveda Healing Kriyas",
        "desc": "Vedic prayers and kriyas for longevity, wealth, protection, safe childbirth, national welfare, and curing disease — directly from the Atharvaveda tradition.",
        "duration": "Multiple Days", "mode": "On-site", "level": "All Levels"
      },
      {
        "tag": "Life Rites",
        "name": "16 Sanskar Vidhi",
        "desc": "All sixteen life-cycle rites performed through authentic Tantric methods — from birth to moksha, each Sanskar carried out as prescribed in the sacred tradition.",
        "duration": "Ritual Service", "mode": "By Appointment", "level": "All Levels"
      }
    ]
  },
  "footer": {
    "tagline": "Preserving the ancient flame of Brahma Vidya",
    "location": "Borigumma, Horadali, Odisha, India",
    "phone": "+91 8260437455",
    "sadhana_links": ["Das Mahavidya", "Maa Kali Sadhana", "Nav Durga", "Sarp Vidya", "Samsan Sadhana", "Agni Tattva"],
    "learn_links": ["About Guruji", "Guru Parampara", "Books", "Courses", "Brahma Vidya", "Testimonials"],
    "join_links": ["Diksha — Initiation", "Events", "Navratri Camp", "Shop", "Donate", "Contact"],
    "copyright": "© 2025 Divya Jivan Siddha Ashram. All rights reserved.",
    "disclaimer": "This site is for spiritual education only. Advanced practices require direct Guru guidance. Not a substitute for medical advice."
  }
}
```

### Hindi (hi.json)
```json
{
  "nav": {
    "home": "होम", "about": "परिचय", "sadhana": "साधना",
    "events": "आयोजन", "courses": "पाठ्यक्रम",
    "diksha": "दीक्षा", "shop": "दुकान", "contact": "सम्पर्क"
  },
  "hero": {
    "eyebrow": "बोरीगुम्मा · होरादाली · ओडिशा",
    "name": "दिव्य", "ashram": "जीवन सिद्ध आश्रम",
    "brahma": "ब्रह्म विद्या",
    "tagline": "की प्राचीन ज्वाला को संरक्षित करना",
    "cta1": "साधनाएँ देखें", "cta2": "दीक्षा प्राप्त करें",
    "scroll": "स्क्रॉल"
  },
  "about": {
    "eyebrow": "परम्परा",
    "heading": "प्राचीन जड़ें। जीवित ज्ञान।",
    "body1": "दिव्य जीवन सिद्ध आश्रम, ओडिशा के बोरीगुम्मा-होरादाली में स्थित, तांत्रिक और वैदिक विज्ञानों का एक जीवित केंद्र है — जहाँ गुरु परम्परा की अखंड श्रृंखला प्रामाणिक दीक्षा की गारंटी देती है।",
    "body2": "अथर्ववेद और गहनतम रहस्यमय परम्पराओं से प्रेरित, यह केंद्र साधना, तांत्रिक उपचार, देवी दीक्षा और दुर्लभ विद्याएँ प्रदान करता है।"
  },
  "diksha": {
    "eyebrow": "पवित्र ज्वाला खोजें",
    "heading": "दीक्षा एक समारोह नहीं —\nयह एक संचरण है।",
    "body": "ब्रह्म विद्या की ज्वाला गुरु से शिष्य को दी जाती है, जैसा कि अनादि काल से होता आया है।",
    "cta1": "दीक्षा के लिए आवेदन करें",
    "cta2": "दीक्षा के बारे में जानें"
  },
  "footer": {
    "tagline": "ब्रह्म विद्या की प्राचीन ज्वाला को संरक्षित करना",
    "location": "बोरीगुम्मा, होरादाली, ओडिशा, भारत",
    "copyright": "© 2025 दिव्य जीवन सिद्ध आश्रम। सर्वाधिकार सुरक्षित।"
  }
}
```

### Odia (od.json)
```json
{
  "nav": {
    "home": "ଘର", "about": "ବିଷୟ", "sadhana": "ସାଧନା",
    "events": "ଇଭେଣ୍ଟ", "courses": "ପ୍ରୋଗ୍ରାମ",
    "diksha": "ଦୀକ୍ଷା", "shop": "ଦୋକାନ", "contact": "ଯୋଗାଯୋଗ"
  },
  "hero": {
    "eyebrow": "ବୋରୀଗୁମ୍ମା · ହୋରାଦାଲି · ଓଡ଼ିଶା",
    "name": "ଦିବ୍ୟ", "ashram": "ଜୀବନ ସିଦ୍ଧ ଆଶ୍ରମ",
    "brahma": "ବ୍ରହ୍ମ ବିଦ୍ୟା",
    "tagline": "ର ପ୍ରାଚୀନ ଜ୍ୟୋତି ଅଖଣ୍ଡ ରଖିବା",
    "cta1": "ସାଧନା ଦେଖନ୍ତୁ", "cta2": "ଦୀକ୍ଷା ଖୋଜନ୍ତୁ",
    "scroll": "ସ୍କ୍ରୋଲ"
  },
  "diksha": {
    "eyebrow": "ପବିତ୍ର ଶିଖା ଖୋଜ",
    "heading": "ଦୀକ୍ଷା ଏକ ଉତ୍ସବ ନୁହେଁ —\nଏହା ଏକ ସଂଚାରଣ।",
    "body": "ବ୍ରହ୍ମ ବିଦ୍ୟାର ଜ୍ୟୋତି ଗୁରୁଙ୍କ ଠାରୁ ଶିଷ୍ୟଙ୍କୁ ଦିଆଯାଏ, ଯେପରି ଆଦିକାଳରୁ ହୋଇଆସୁଛି।",
    "cta1": "ଦୀକ୍ଷା ଆବେଦନ", "cta2": "ଦୀକ୍ଷା ବିଷୟ"
  },
  "footer": {
    "tagline": "ବ୍ରହ୍ମ ବିଦ୍ୟାର ପ୍ରାଚୀନ ଜ୍ୟୋତି ଅଖଣ୍ଡ ରଖିବା",
    "location": "ବୋରୀଗୁମ୍ମା, ହୋରାଦାଲି, ଓଡ଼ିଶା, ଭାରତ",
    "copyright": "© 2025 ଦିବ୍ୟ ଜୀବନ ସିଦ୍ଧ ଆଶ୍ରମ।"
  }
}
```

---

## PRELOADER — EXACT CINEMATIC SEQUENCE

Build `Preloader.jsx` with this precise timing:

```
Time 0.0s  → Black screen
Time 0.5s  → Diya SVG fades in (transparent, gold lines, 0.8s fade)
Time 1.4s  → Diya flame animation begins (sway + breath + flicker)
Time 3.5s  → "DIVYA" fades up (0.6s, Cormorant Garamond, gold)
Time 4.1s  → "Jivan Siddha Ashram" fades up (0.6s, Cormorant SC)
Time 5.1s  → All elements hold
Time 6.1s  → "ENTER →" button fades in (Outfit 300, 0.5s)
Time ?     → User clicks ENTER:
             - Two black panels (temple doors) slide apart left+right
             - 1.3s cubic-bezier(.76,0,.24,1)
             - Gold seam line on each door edge
             - Home page reveals underneath
             - Preloader unmounts
```

**DiyaSVG.jsx — The animated diya mark (transparent background):**

```jsx
// Pure SVG recreation of the logo mark
// Arch frame → radiating rays → diya bowl → wick → animated flame
// Flame has 3 layers: outer teardrop, inner core, glow halo
// Each animates with different durations: 2.1s / 1.8s / 1.4s / 2s / 2.5s
// So they NEVER sync — always feels organic and alive

// Key SVG structure:
// - Arch: path M52,220 L52,95 A48,48 0 0 1 148,95 L148,220
// - 3 pedestal steps: rects at y=208, y=200, y=193
// - Bowl: two arcs for rim + bottom
// - Wick: line + circle tip
// - Rays: 9 lines radiating from centre (100,112)
// - Flame outer: teardrop path, fill=radialGradient (cream→gold→amber→transparent)
// - Flame inner: smaller teardrop, brighter core
// - Glow halo: ellipse with radialGradient, low opacity

// CSS animations (all on SVG elements):
// .flame-group     { animation: flameSway 2.1s ease-in-out infinite }
// .flame-outer     { animation: flameBreath 1.8s ease-in-out infinite }
// .flame-inner     { animation: flameBreath 1.4s ease-in-out .2s infinite,
//                               flameCoreFlicker 2.3s ease-in-out infinite }
// .flame-glow-halo { animation: flameGlow 2s ease-in-out infinite }
// .ray-group       { animation: rayPulse 2.5s ease-in-out infinite }
// svg              { animation: divaGlow 3s ease-in-out 1.4s infinite }
```

---

## NAV COMPONENT — EXACT LAYOUT

```jsx
// Nav.jsx
// Layout: CSS Grid — 3 columns: logo | links (centre) | lang+extras (right)
// grid-template-columns: 1fr auto 1fr

// Left: Logo mark (small) + "DIVYA" text + "Jivan Siddha Ashram" sub
// Centre: 8 links — Home About Sadhana Events Courses Diksha Shop Contact
// Right: Lang switcher (EN · हि · ଓ)

// On scroll > 40px: background rgba(10,8,5,0.96) + border-bottom
// Link hover: gold underline sweep from centre (scaleX 0→1)
// Active page: gold colour + underline always visible

// Mobile (<860px):
// Row 1: Logo centred
// Row 2: Horizontally scrollable link row (no hamburger, no hidden menu)
// Lang switcher hidden on mobile

// Animation: nav fades in after preloader exit (opacity 0→1, 0.6s)
```

---

## LENIS SMOOTH SCROLL SETUP

```js
// main.jsx
import Lenis from 'lenis'
import gsap from 'gsap'
import ScrollTrigger from 'gsap/ScrollTrigger'

gsap.registerPlugin(ScrollTrigger)

const lenis = new Lenis({
  duration: 1.4,
  easing: (t) => Math.min(1, 1.001 - Math.pow(2, -10 * t)),
  smooth: true,
})

function raf(time) {
  lenis.raf(time)
  requestAnimationFrame(raf)
}
requestAnimationFrame(raf)

// Connect Lenis to GSAP ScrollTrigger
lenis.on('scroll', ScrollTrigger.update)
gsap.ticker.add((time) => { lenis.raf(time * 1000) })
gsap.ticker.lagSmoothing(0)
```

---

## GSAP ANIMATIONS — KEY IMPLEMENTATIONS

### ScrollReveal (reusable hook)
```js
// useScrollReveal.js
// On element enter viewport:
// - opacity: 0 → 1
// - y: 28px → 0
// - duration: 0.9s, ease: power3.out
// - stagger: 0.1s for lists/grids
```

### Hero Ticker Strip
```js
// Horizontal marquee using GSAP infinite loop
// Content: "Ten Mahavidyas ◆ Nav Durga Sadhana ◆ Vaishnav Diksha ◆
//           Sarp Vidya ◆ Atharvaveda Kriyas ◆ Samsan Sadhana ◆
//           Tantra Kat Healing ◆ Agni Tattva ◆ 16 Sanskar Vidhi ◆
//           Karna Pishacha ◆"
// Speed: 35s, seamless loop (duplicate content)
// Background: var(--mud) #3D1F0D
// Text: var(--sunset) #EAC891
// Dots: var(--terracota) #D08224
```

### Page Transitions (Framer Motion)
```jsx
// Variants: { initial: {opacity:0, y:20}, animate: {opacity:1, y:0}, exit: {opacity:0, y:-10} }
// Duration: 0.5s ease-out
```

---

## ALL 8 PAGES — FULL CONTENT

### HOME (index / Home.jsx)
Sections in order:
1. Hero (full-height, dark void bg, rotating sacred geometry)
2. Ticker strip (gold text on dark)
3. About strip (2-col: animated yantra SVG left, text + stats right)
4. Sadhanas grid (3×3, arch-clipped cards on void bg)
5. Events list (left: heading + call CTA, right: 5-event timeline)
6. Books (4 book cards on forest bg)
7. Diksha CTA (fire.jpg full-bleed, 55% opacity, text overlay)
8. Courses (2×2 grid on void bg)
9. Footer

### ABOUT (About.jsx)
Full page with these sections:
- **Hero band:** "The Living Lineage" — dark, full width, eyebrow + large heading
- **Guruji section:** 2-col — arch-framed photo left, bio right
  - Content: *"Guruji has spent decades in the direct practice and transmission of Tantric and Vedic sciences in the ancient tradition of Odisha. His lineage traces an unbroken chain of Guru-Shishya transmission that predates recorded history. He resides at the ashram in Borigumma, Horadali, and receives seekers by appointment."*
- **Guru Parampara:** Vertical timeline with gold line and nodes
  - Nodes (5): Ancient Vedic Origins → Atharvaveda Tradition → Odisha Tantric Schools → Direct Guru Transmission → Present Day: Divya Jivan Siddha Ashram
- **Mission & Vision:** Pull quote section on forest bg
  - Quote: *"The mission of Divya Jivan Siddha Ashram is singular: to keep the flame burning. Not to reform, not to modernise, not to dilute — but to transmit what has been received, intact and alive, to those rare souls who are truly ready."*
- **Philosophy:** 3 columns
  - Col 1 — Guru Parampara: *"All authentic transmission is Guru to Shishya. The book cannot initiate. The video cannot transmit. The living flame passes only hand to hand, heart to heart."*
  - Col 2 — Brahma Vidya: *"The supreme science is not philosophy — it is direct experience. Brahma Vidya is the path of knowing the self as Brahman, the infinite consciousness, through disciplined practice and grace."*
  - Col 3 — Tantra as Liberation: *"Tantra is not ritual for ritual's sake. Every Sadhana, every Diksha, every practice is a doorway — not to power, but to liberation. The goal is always Mukti."*
- **Ashram:** Location block — address, contact, map embed placeholder

### SADHANA (Sadhana.jsx)
- **Hero band:** "The Sacred Practices" on void
- **Filter row:** All · Mahavidyas · Nav Durga · Vedic · Aghor · Cemetery · Healing
- **Full sadhana grid** (all 7 + extras):
  1. Das Mahavidya Sadhana — Advanced
  2. Maa Kali Pratyaksh Sadhana — Advanced
  3. Nav Durga (9 individual forms) — Intermediate
  4. Maa Shailputri — Pratyaksh Darshan in one day
  5. Maa Katyayani — Siddhi in one day
  6. Samsan Sadhana — Rare/Restricted
  7. Masan Jagran — Cemetery spirits awakening, 3-day
  8. Agni Tattva Sadhana — All levels
  9. Sarp Vidya — 3-year course
  10. Karna Pishacha — Esoteric
  11. Aghor Vidya — Restricted
  12. Tantra Kat — Healing/Protection
  13. Piliya Utar Kriya — Jaundice healing
  14. Brahma Vidya — All levels
  15. Vaishnav Diksha Sadhana — Initiation
- **Safety notice:** Gold box — *"Many practices on this page require direct Guru transmission. Self-practice of restricted Sadhanas without initiation can cause serious harm. Please contact the ashram before attempting any advanced practice."*

### EVENTS (Events.jsx)
- **Hero band:** "Sacred Calendar 2025–2026"
- **Featured event** (full width): Navratri Sadhana Camp, March 19–27 2026
  - *"Nine consecutive days of intensive Nav Durga practices. Each day is dedicated to one form of Durga — from Maa Shailputri on day one to Maa Siddhidatri on day nine. Open to all sincere seekers. Free of charge. Prior registration required."*
- **Event list** (all 5 from above)
- **Registration section:** Contact form — Name, Phone, Email, Which Event, Message
  - Note: *"All gatherings are held at Divya Jivan Siddha Ashram, Borigumma, Horadali, Odisha. Accommodation available on request. Call +91 8260437455 to confirm attendance."*

### COURSES (Courses.jsx)
- **Hero band:** "Paths of Vidya"
- **Featured course** (hero card): Sarp Vidya 3-Year Programme
  - Full description: *"Sarp Vidya — the science of the serpent — is one of the oldest and most complete esoteric sciences in the Indian tradition. This three-year residential programme covers: Naga mantra and stotra, Sarp Sadhana methods, serpent deity worship, antidote kriyas, and the complete philosophy of Naga consciousness. This course is transmitted only in person and only through direct Guru initiation. The next cohort begins by appointment."*
- **4 course cards** (as above)
- **Enquiry form:** Name, Phone, Email, Which Course, Background/Experience, Message

### DIKSHA (Diksha.jsx)
The most editorial, sacred page on the site.
- **Hero:** fire.jpg full-bleed, same treatment as home section
  - Heading: *"Initiation is not a ceremony — it is a transmission."*
  - Sub: *"The flame of Brahma Vidya is passed from Guru to Shishya, as it has been since the beginning."*
- **What is Diksha?**
  - *"Diksha is the sacred act by which a Guru transmits a portion of his own realisation, his own Shakti, directly into the consciousness of the prepared student. It cannot be read about, watched on video, or received online. It requires physical presence, sincere preparation, and the grace of the Guru. At Divya Jivan Siddha Ashram, Diksha is not given lightly. It is a sacred contract between Guru and Shishya that carries obligations on both sides."*
- **Levels of Initiation** (4 levels):
  1. Mantra Diksha — entry level, receiving a personal mantra
  2. Tantra Diksha — initiation into Tantric practice
  3. Vaishnav Diksha — formal Vaishnav lineage initiation
  4. Sarp Vidya Diksha — rare, by invitation only
- **Eligibility:**
  - *"The Guru alone determines readiness. However, sincere seekers should: be of stable mind and body, have no current involvement in conflicting spiritual paths, be willing to commit to practice as prescribed, and approach with genuine humility and devotion. Age minimum: 18 years."*
- **Code of Conduct:**
  - *"Initiated students are expected to maintain: daily practice as prescribed, respect for the Guru Parampara, confidentiality of transmitted practices, abstention from sharing initiatory material with uninitiated persons, and regular communication with the ashram."*
- **Application form:** Name, Age, Location, Phone, Email, Spiritual Background, Which Diksha, Why seeking initiation (textarea), Declaration checkbox

### SHOP (Shop.jsx) — CATALOGUE ONLY
- **Hero band:** "Sacred Store"
- Note: *"All items are available for enquiry. WhatsApp or call to order: +91 8260437455"*
- **Categories filter:** All · Books · Yantras · Rudraksha · Ritual Items · Spiritual Art
- **Product grid** (12 items):
  - 21 Devi Sadhana (Book) — Enquire
  - Brahma Vidya (Book) — Enquire
  - Itar Yoni Sadhana (Book) — Enquire
  - Sadhana Aur Sadhak (Book) — Enquire
  - Shri Yantra (Copper) — Enquire
  - Kali Yantra (Copper) — Enquire
  - 5-Mukhi Rudraksha — Enquire
  - 7-Mukhi Rudraksha — Enquire
  - Rudra Mala (108 beads) — Enquire
  - Copper Havan Kund — Enquire
  - Navagraha Yantra — Enquire
  - Ritual Incense Set — Enquire
- Each card: arch-clipped image placeholder, name, category tag, "Enquire via WhatsApp" button

### CONTACT (Contact.jsx)
- **Hero band:** "Reach the Ashram"
- **2-col layout:**
  - Left: contact details
    ```
    Address: Divya Jivan Siddha Ashram
             Borigumma, Horadali
             Koraput District, Odisha — 764059
    Phone/WhatsApp: +91 8260437455
    Tradition: Atharvaveda & Tantric Lineage
    Language: Odia · Hindi · English
    ```
  - Right: contact form — Name, Phone, Email, Subject (dropdown: General Enquiry / Diksha / Events / Courses / Healing / Shop), Message
- **Map placeholder:** Embedded iframe for Borigumma location
- **Hours note:** *"The ashram does not maintain fixed visiting hours. All visits are by prior appointment only. Please call or WhatsApp before travelling."*

---

## SECTION BACKGROUND RHYTHM

| Section | Background | Feel |
|---|---|---|
| Preloader | `#0A0805` void | Sacred darkness |
| Nav (scrolled) | `rgba(10,8,5,.96)` | Invisible then present |
| Hero | `#0A0805` void | Commanding |
| Ticker strip | `#3D1F0D` dark brown | Earthy break |
| About | `#0A0805` void | Deep |
| Sadhanas | `#3D4A35` forest | Living, earthy |
| Events | `#0A0805` void | Mysterious |
| Books | `#3D4A35` forest | Scholarly |
| Diksha CTA | fire.jpg + overlay | Sacred fire |
| Courses | `#0A0805` void | Serious |
| Footer | `#0A0805` void | Grounding close |

---

## CUSTOM CURSOR

```jsx
// Cursor.jsx
// Dot: 10px, background var(--gold), mix-blend-mode: multiply
// Ring: 30px, border 1.5px var(--gold), opacity 0.4, lag behind by 10% per frame
// On hover (links, buttons, cards): dot grows to 40px, background var(--signal) #AE431E, opacity 0.55
// Both hidden on mobile (touch devices)
```

---

## GRAIN TEXTURE OVERLAY

```css
/* Fixed, full-screen, pointer-events: none, z-index: 9000 */
/* opacity: 0.028 */
/* SVG noise filter — fractalNoise baseFrequency=".75" numOctaves="4" */
/* Adds subtle film grain to every page — critical for the luxury feel */
```

---

## ARCH FRAME MOTIF

The arch from the logo (rounded top, straight sides) is the **repeating visual motif** across the site:
- Image containers use arch-clip (clip-path: `path('M0,100% L0,40% Q0,0 50%,0 Q100%,0 100%,40% L100%,100% Z')`)
- Section dividers use arch-top SVG cuts
- Card hover states reveal arch border outlines
- Book covers clipped in arch shape
- Guruji photo clipped in arch shape

---

## PERFORMANCE NOTES

- All images: lazy loaded with `loading="lazy"`
- Fonts: `display=swap`
- Fire.jpg: compress to under 200KB before deploy
- Logo PNG: use WebP version if possible
- Preloader unmounts completely from DOM after entry
- GSAP ScrollTrigger: `once: true` for all reveal animations
- Lenis: disabled on `prefers-reduced-motion`

---

## DEPLOYMENT

```bash
npm run build
# Output: dist/
# Deploy to: Netlify / Vercel / Firebase Hosting
# Domain suggestion: divyajivansiddha.org or divyajivan.ashram.in

# Vercel deploy:
vercel --prod

# Netlify:
netlify deploy --prod --dir=dist
```

---

## FINAL CHECKLIST BEFORE GOING LIVE

- [ ] Replace all image placeholders with real photos
- [ ] Verify all phone numbers (8260437455)
- [ ] Add real Guruji bio and photo
- [ ] Google Maps embed for ashram location
- [ ] Connect contact/application forms to email (use Formspree or EmailJS)
- [ ] Add Google Analytics
- [ ] Add meta tags (og:image, og:title, description) per page
- [ ] Test all 3 languages on mobile
- [ ] Test preloader on slow 3G (Chrome DevTools throttle)
- [ ] Add sitemap.xml
- [ ] Add robots.txt
- [ ] SSL certificate (auto on Vercel/Netlify)
- [ ] Add WhatsApp floating button (bottom-right, links to wa.me/918260437455)
