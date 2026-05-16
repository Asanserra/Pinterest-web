# The House Verdict — Design System

> Amazon affiliate landing page for home decoration. Clean, minimalist, editorial feel.  
> Inspired by: Broma Bakery visual language (off-white space, elegant serif headlines, warm accents).

---

## Brand Identity

| Element | Value |
|---|---|
| Brand name | The House Verdict |
| Tagline | *Honest picks for beautiful spaces.* |
| Niche | Home decoration & interiors |
| Tone | Warm, trustworthy, editorial — like a stylish friend recommending products |
| Language | English (US) |

---

## Color Palette

| Name | Hex | Usage |
|---|---|---|
| Cream (background) | `#F9F6F1` | Page background, hero background |
| Off-white | `#FFFFFF` | Cards, nav |
| Charcoal | `#1C1C1C` | Headings, primary text |
| Warm Gray | `#6B6560` | Body text, captions |
| Muted Gold | `#C4956A` | Accent, links, CTA hover, borders |
| Blush Pink | `#F2DDD5` | Badge backgrounds, highlight chips |
| Dark CTA | `#2B2420` | Primary buttons |

---

## Typography

### Fonts
- **Headlines (H1–H2):** Playfair Display — serif, elegant, editorial
- **Subheadings (H3–H4):** Playfair Display Italic or Regular
- **Body / UI:** Inter — clean sans-serif, highly readable
- **Labels / Captions:** Inter, letter-spacing 0.08em, uppercase, 11–12px

### CDN
```html
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,600;0,700;1,400&family=Inter:wght@300;400;500;600&display=swap" rel="stylesheet">
```

### Scale (desktop)
| Element | Size | Weight | Line-height |
|---|---|---|---|
| H1 hero | 56–72px | 700 | 1.1 |
| H2 section | 36–42px | 600 | 1.2 |
| H3 card title | 22–26px | 600 | 1.3 |
| Body | 16–17px | 400 | 1.7 |
| Small / label | 12–13px | 500 | 1.5 |
| CTA button | 14px | 600 | — |

---

## Spacing & Layout

- **Max content width:** 1200px centered
- **Section padding:** 80–100px top/bottom (desktop), 48–60px (mobile)
- **Column gap:** 24–32px
- **Card border-radius:** 12–16px
- **Button border-radius:** 50px (pill shape)
- **Grid system:** CSS Grid, primarily 3-column on desktop → 1-column on mobile

---

## Component Specs

### Navigation (sticky)
- Background: `#FFFFFF` with subtle bottom border `rgba(0,0,0,0.07)`
- Logo: Playfair Display, 22px, Charcoal
- Nav links: Inter 14px, letter-spaced, Warm Gray → hover Muted Gold
- CTA in nav: "Top Picks" pill button, Dark CTA background

### Hero Section
- Full-width, background `#F9F6F1`
- Left: large editorial headline (2–3 lines), subtext, CTA button
- Right: lifestyle image (home interior) in a soft-rounded frame
- Mobile: stacked, image below text

### Product Card (Affiliate)
```
┌─────────────────────┐
│  [product image]    │  aspect-ratio: 4/3, object-fit: cover
│                     │  border-radius: 12px top
├─────────────────────┤
│  CATEGORY LABEL     │  Inter 11px, uppercase, Muted Gold
│  Product Name       │  Playfair 20px bold
│  Short description  │  Inter 14px, Warm Gray
│  ★★★★☆  4.5 (1.2k) │  Inter 13px
│  $49.99             │  Playfair 24px bold, Charcoal
│  [Buy on Amazon ↗]  │  Pill button, Dark CTA bg, white text
└─────────────────────┘
```
- Card background: `#FFFFFF`
- Box shadow: `0 2px 16px rgba(0,0,0,0.06)`
- Hover: lift effect `translateY(-4px)`, shadow deepens
- Grid: 3 columns desktop / 2 tablet / 1 mobile

### Blog Preview Card
- Horizontal on desktop (image left, text right), vertical on mobile
- Image: 280×200px, border-radius 12px
- Category chip: Blush Pink background, small uppercase label
- Title: Playfair 20px
- Excerpt: Inter 14px, 3 lines max
- "Read more →" link: Muted Gold

### FAQ / AI-Friendly Section
- Accordion component
- Question: Inter 16px Semi-Bold, Charcoal
- Answer: Inter 15px, Warm Gray, revealed on click/open
- Structured data: JSON-LD `FAQPage` schema injected in `<head>`
- Organized by search intent categories: Buying Guides, Care & Styling, Best Products

### Privacy Policy
- Simple clean text layout
- Rendered in a single-column max-width 720px container
- Accessible via footer link and `/privacy` anchor

---

## SEO Requirements

### Meta Tags
```html
<title>The House Verdict | Honest Home Decor Picks & Reviews</title>
<meta name="description" content="Curated Amazon home decor picks, honest reviews, and styling tips for every room. Find the best products for your home at The House Verdict.">
<meta property="og:title" content="The House Verdict">
<meta property="og:description" content="Honest picks for beautiful spaces.">
<meta property="og:type" content="website">
<meta name="robots" content="index, follow">
<link rel="canonical" href="https://thehouseverdict.com">
```

### Structured Data (JSON-LD)
- `WebSite` — with sitelinks search box
- `Organization` — name, url, logo
- `FAQPage` — all FAQ questions/answers
- `ItemList` — featured product recommendations

### On-Page SEO
- Single `<h1>` per page
- All images have descriptive `alt` attributes
- Internal anchor links for all sections
- Semantic HTML5: `<header>`, `<main>`, `<article>`, `<section>`, `<footer>`, `<nav>`

---

## Responsive Breakpoints

| Name | Width | Changes |
|---|---|---|
| Mobile | < 640px | Single column, smaller text, stacked nav |
| Tablet | 640–1024px | 2-column product grid, compressed hero |
| Desktop | > 1024px | Full 3-column grid, side-by-side layouts |

---

## Page Sections (Order)

1. **`<header>`** — Sticky navigation with logo + links + CTA
2. **`#hero`** — Headline, subtext, hero image, scroll CTA
3. **`#products`** — "Editor's Picks" — affiliate product grid (6 cards)
4. **`#about`** — About The House Verdict
5. **`#blog`** — Latest from the blog (3 preview cards)
6. **`#faq`** — FAQ accordion (AI & SEO optimized)
7. **`#privacy`** — Privacy Policy (full text)
8. **`<footer>`** — Links, affiliate disclosure, copyright

---

## Affiliate Disclosure

Must appear:
- In the site header/nav (subtle bar above nav, or footer)
- At the top of the products section
- In the Privacy Policy

Text: *"As an Amazon Associate, The House Verdict earns from qualifying purchases. This comes at no extra cost to you."*

---

## Accessibility

- Color contrast: all text meets WCAG AA (4.5:1 minimum)
- Focus states: visible outline on all interactive elements
- ARIA labels on icon buttons and accordion triggers
- `prefers-reduced-motion` respected for animations
- Alt text on all images
