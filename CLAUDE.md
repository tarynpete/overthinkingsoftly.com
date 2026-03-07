# Overthinking Softly — Claude Code Setup & Design Documentation

## Project Overview

**Website:** overthinkingsoftly.com
**GitHub Repo:** github.com/TARYNPETE/overthinkingsoftly.com
**Main File:** index.html (single-file website, all HTML/CSS/JS in one file)
**Hosting:** GitHub Pages (free)
**Domain Registrar:** Namecheap

---

## Website Purpose

Overthinking Softly is a warm, minimalist personal blog created to support people who struggle with anxiety, overthinking, and emotional stress. The site is built around a sense of safety, community, and gentle self-improvement. The creator writes under the **pen name Hazel** and remains fully anonymous — no real name, photo, or personal identifying information should ever appear on the site.

---

## Author / Pen Name

- **Pen name:** Hazel
- **Tone:** Warm, conversational, honest — like a trusted friend
- **Background (fictional/anonymous):** A woman in her 30s-40s who has personally experienced overthinking, anxiety, people-pleasing, and difficulty setting boundaries. Found peace through writing and wellness.
- **Important:** The real author's identity is never revealed. No real photos. Stock images or aesthetic placeholder images only.

---

## Design System

### Color Palette (CSS Variables)

```css
--cream: #faf8f4;           /* Main background */
--warm-white: #f5f2ec;      /* Secondary background */
--parchment: #ede8df;       /* Cards, subtle sections */
--tan: #d4c9b8;             /* Borders on hover */
--sage: #9aab96;            /* Accent, buttons */
--sage-dark: #7a8f76;       /* Tags, labels */
--terracotta: #c4845a;      /* Primary accent color */
--terracotta-light: #e8c4a8;/* Soft accent, gradients */
--espresso: #3d2f27;        /* Primary text, dark buttons */
--mocha: #6b4f3f;           /* Button hover states */
--text: #3a3028;            /* Body text */
--text-soft: #7a6e65;       /* Secondary text */
--text-muted: #a09589;      /* Labels, meta text */
--border: #e5dfd6;          /* Default borders */
--shadow: rgba(61,47,39,0.07); /* Card shadows */
```

### Typography

- **Display / Headings:** Cormorant Garamond (Google Fonts) — serif, elegant, warm
  - Weights used: 300, 400, 500 — italic variants heavily used for emphasis
- **Body / UI:** Jost (Google Fonts) — clean, modern, minimal
  - Weights used: 300, 400, 500
- **Font import:**

```html
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,500;1,300;1,400&family=Jost:wght@300;400;500&display=swap" rel="stylesheet">
```

### Design Aesthetic

- Minimalist but warm — never cold or empty
- Generous white space
- Soft neutral tones with terracotta as the signature accent
- Subtle noise texture overlay on body (CSS SVG filter)
- Smooth fade-up animations on page load
- Cards with subtle hover lift effects
- Rounded buttons (border-radius: 30px for pill buttons, 4px for rectangular)
- No harsh shadows — always soft and warm

---

## Site Structure

The entire website is a **single HTML file** (index.html) with a JavaScript page-switching system. There is no backend, no database, and no server-side code. All navigation is handled by `showPage('pageid')` JavaScript function.

### Pages

| Page ID     | Nav Label   | Description                                                            |
|-------------|-------------|------------------------------------------------------------------------|
| `home`      | Home        | Landing page with hero, about strip, Hazel intro, feature cards, quote |
| `blog`      | Blog        | Grid of blog post cards                                                |
| `ask`       | Ask         | Anonymous question submission form                                     |
| `meals`     | Meal Prep   | Recipe cards grid                                                      |
| `resources` | My Picks 💛 | Curated books, apps, products (will include Amazon affiliate links)    |

### Navigation

- Fixed top nav bar (64px height) with blur/glass effect
- Logo: "Overthinking Softly" with italic terracotta "Softly"
- Desktop: full nav links + search bar + Admin button
- Mobile: hamburger menu that expands full-width dropdown

---

## Key Features

### Admin Panel

- Accessible via "Admin" button in nav
- Demo password: `admin123` ⚠️ **This should be changed to a real secure password**
- Features: publish new posts, upload cover images, view anonymous submissions, tag selection
- **Note:** The admin panel is currently front-end only — it does not save to a database. Posts published through the admin panel do not persist. All real content updates currently require editing index.html directly.

### Anonymous Question Form

- Located on the Ask page
- No name or identifying info collected (by design)
- Currently front-end only — submissions are not stored anywhere
- Shows a success message on submit
- **Future need:** Connect to a real form backend (e.g. Formspree, Netlify Forms, or EmailJS) so submissions are actually received

### Search Bar

- Located in the nav
- Currently redirects to the blog page on any input
- **Future need:** Implement real search functionality across posts

### Crisis Resources Bar

- Appears above the footer on every page
- Contains: 988 Suicide & Crisis Lifeline, Crisis Text Line (741741), NAMI (1-800-950-6264), SAMHSA (1-800-662-4357)
- All numbers are tappable/clickable links (tel: and sms: links)
- **Do not remove this section**

### Legal Disclaimer

- Located in the footer on every page
- States clearly that Hazel is not a therapist or licensed professional
- **Do not remove this section**

---

## Content Guidelines

- **Tone:** Always warm, gentle, honest, and non-clinical
- **No public comments** on any posts (by design decision)
- **No real photos of the author** — use aesthetic stock images (flat lays, nature, cozy scenes)
- **No medical advice** — always redirect to professionals for serious issues
- Blog posts should feel like journal entries or letters to a friend
- Categories: Overthinking, Anxiety, Relationships, Growth, Self-compassion, Reader Q&A, Meal Prep

---

## Planned Next Steps & Feature Requests

### High Priority

- [ ] **Connect question form to real backend** — Use Formspree (free tier) or EmailJS so anonymous submissions are actually emailed to Hazel. This is the most important functional gap.
- [ ] **Change admin password** from `admin123` to something secure
- [ ] **Add real blog posts** — Replace placeholder sample posts with real written content from Hazel
- [ ] **Add Amazon affiliate links** to My Picks 💛 page — Replace placeholder product cards with real products and affiliate URLs

### Medium Priority

- [ ] **Add photos** — Replace the small 🌿 placeholder boxes with real aesthetic stock images (from Unsplash or similar). Images should feel cozy, warm, minimal — flat lays, candles, journals, nature, soft textures. No photos of real people.
- [ ] **Implement real search** — Search across blog post titles and content
- [ ] **Make admin panel functional** — Either connect to a CMS (like Netlify CMS or Forestry) or build a simple JSON-based post system so Hazel can publish posts without editing raw HTML
- [ ] **Add newsletter signup** — Consider adding an email list (Mailchimp or ConvertKit free tier) for readers to subscribe
- [ ] **Add social media links** — If Hazel creates social accounts (Instagram, Pinterest, TikTok) under the pen name, add to footer

### Lower Priority / Nice to Have

- [ ] **Individual blog post pages** — Currently posts are cards that don't open full articles. Need to implement a post detail view
- [ ] **Add more recipe pages** with full ingredient lists and instructions
- [ ] **Improve mobile experience** further — especially the Hazel about section layout
- [ ] **Add a favicon** — Small icon that appears in browser tab (should match the site aesthetic — perhaps a small leaf or soft geometric)
- [ ] **SEO optimization** — Add meta description, Open Graph tags for social sharing previews
- [ ] **Add Google Analytics** — To track visitor numbers and popular content

---

## Technical Notes

- **No npm, no build system, no dependencies** — pure HTML/CSS/JS only
- **All fonts loaded from Google Fonts CDN**
- **No localStorage or cookies used**
- **Mobile breakpoint:** 768px (hamburger menu activates)
- **Small mobile breakpoint:** 600px (crisis bar stacks vertically)
- The noise texture overlay uses an inline SVG data URI — do not remove it, it adds warmth to the design
- Page transitions use CSS `animation: fadeUp 0.5s ease forwards`
- All page content lives inside `<div id="page-[name]" class="page">` wrappers

---

## File Structure

```
overthinkingsoftly.com/
└── index.html          ← Entire website (HTML + CSS + JS)
└── CLAUDE.md           ← This file (setup notes for Claude Code)
└── CNAME               ← Custom domain config for GitHub Pages
```

---

## Important Reminders

1. **Always preserve the crisis resources bar** above the footer
2. **Always preserve the legal disclaimer** in the footer
3. **Never reveal the author's real identity** — Hazel is a pen name
4. **Keep the warm, minimalist aesthetic** — avoid anything that feels corporate, clinical, or cold
5. **No public comments section** — this is intentional
6. **The color palette above is fixed** — do not introduce new colors without discussion
7. **Typography is fixed** — Cormorant Garamond + Jost only

---

*Documentation created March 7, 2026. Website built in a single session from concept to live deployment.*
