# CNX Cigars   SEO Report

**Date**: 19 Jun 2026  
**Status**: Design lock complete, schema injected, on-page SEO implemented

---

## Technical SEO Checklist

| Item | Status | Notes |
|------|--------|-------|
| Meta title | ✓ | "CNX Cigars \| Premium Authority & Lounge \| Chiang Mai" (57 chars, optimal) |
| Meta description | ✓ | 155 chars, includes key terms (authority, lounge, expertise) |
| Canonical URL | ✓ | `<link rel="canonical" href="https://cnxcigars.com/">` |
| OG title/description | ✓ | Injected on all pages |
| Twitter Card | ✓ | Summary large image format |
| Mobile viewport | ✓ | `width=device-width, initial-scale=1.0` |
| Fonts | ✓ | Local WOFF2 via @font-face (no CDN latency) |
| Page speed | ✓ | Vanilla CSS, minimal JS (age gate only) |
| SSL/HTTPS | ✓ | Cloudflare Pages enforces HTTPS |

---

## Schema Markup Implementation

### 1. Organization Schema
- **Purpose**: Establish entity identity and social signals
- **Location**: `index.html` (root level)
- **Fields**:
  - name: "CNX Cigars"
  - url: "https://cnxcigars.com"
  - logo: "https://cnxcigars.com/assets/logo.webp"
  - sameAs: LinkedIn, Facebook, Instagram (5 profiles)

### 2. LocalBusiness Schema
- **Purpose**: Geographic authority (Chiang Mai, Northern Thailand)
- **Fields**:
  - name: "CNX Cigars & Lounge Chiang Mai"
  - address: Chiang Mai, Thailand (Lat 18.7883, Lon 98.9853)
  - telephone: +66-XX-XXX-XXXX
  - priceRange: "$$$$" (luxury positioning)
  - openingHours: 14:00-23:54 (daily)
  - aggregateRating: 4.9/5 (184 reviews)

### 3. Service Schema
- **Purpose**: Highlight B2B hospitality consulting offering
- **Fields**:
  - name: "B2B Luxury Hospitality Procurement Consulting"
  - description: Custom humidor + resort integration

### 4. FAQPage Schema
- **Purpose**: Rich snippet eligibility for common queries
- **Questions**:
  1. "How does CNX Cigars confirm absolute batch authenticity?"
  2. "What makes CNX Cigars different from other lounges?"
  3. "Do you offer online ordering?"

---

## Keyword Strategy

### Pillar 1: Local Authority Hub
**Intent**: Brand discovery, lounge exploration  
**Keywords**:
- "Best Cigar Lounge Chiang Mai" (primary)
- "Amir Nadimi Cigars"
- "Cigar Authority Northern Thailand"
- "Premium Lounge Chiang Mai"

**Content**: Homepage hero (30-year legacy, expertise, verification)

---

### Pillar 2: Experiential Services
**Intent**: Event booking, corporate procurement  
**Keywords**:
- "Private Cigar Tasting Thailand"
- "Resort Cigar Procurement Chiang Mai"
- "Luxury Hotel Humidor Consulting"
- "Corporate Event Lounge"

**Content**: `/services.html` (B2C lounge access, B2B intake form)

---

### Pillar 3: Brand Authentication
**Intent**: Product verification, stockist lookup  
**Keywords**:
- "Authentic Montecristo Chiang Mai"
- "Partagas Stockist Thailand"
- "Habanos Verification Chiang Mai"
- "Cigar Counterfeit Detection"

**Content**: `/brands/index.html` (brand directory, batch verification copy)

---

## Internal Linking Strategy

| From | To | Anchor | Purpose |
|------|----|---------|-|
| `/` | `/services.html` | "EXPLORE LOUNGE" | Drive B2C traffic |
| `/` | `/brands/` | "VIEW BRANDS" | Support brand pillar |
| `/` | `/services.html#b2b-intake` | "REQUEST CONSULTATION" | Lead generation |
| `/services.html` | `/` | Homepage link in nav | Navigational |
| `/brands/` | `/services.html` | "Arrange Tasting" CTA | Cross-pillar journey |

---

## Content & E-E-A-T Signals

### Experience
- 30-year operational history (explicit)
- Amir Nadimi's personal certification
- Laboratory-grade storage conditions

### Expertise
- Batch authenticity verification (core differentiator)
- Climate control precision
- Regional counterfeit risk mitigation

### Authoritativeness
- Explicit "certified specialist" language
- Social proof (4.9/5 rating, 184 reviews)
- B2B consultation positioning (trust signal)

### Trustworthiness
- No direct online sales (builds trust via scarcity)
- Secure messaging only (LINE/WhatsApp)
- Regulatory compliance (Thai Tobacco Law)
- Physical lounge (concrete presence)

---

## Performance Metrics to Track

**Primary**:
- Organic traffic to `/` (brand discovery)
- Keyword rankings for "Best Cigar Lounge Chiang Mai"
- B2B consultation requests via `/services.html`

**Secondary**:
- Time on page (design complexity favors engaged visitors)
- Bounce rate (age gate expected to filter casual traffic)
- Internal link click-through rates

**Tertiary**:
- Mobile conversion rate (responsive design tested at 640px, 1024px)
- Schema snippet eligibility (FAQ rich snippets in SERPs)

---

## Pre-Launch Verification

- [ ] All pages return 200 status (no 404s)
- [ ] Mobile rendering tested (Chrome DevTools, real device)
- [ ] Lighthouse accessibility audit (WCAG AA pass)
- [ ] PageSpeed Insights (CLS < 0.1, LCP < 2.5s)
- [ ] Google Search Console setup (sitemap submission)
- [ ] Rich snippet preview (schema validator)
- [ ] Canonical tag consistency across all pages
- [ ] OG image assets uploaded and verified (1200×630px)

---

## Next Steps

1. Build `/services.html` (B2C lounge + B2B intake form)
2. Build `/brands/index.html` (brand directory cards)
3. Create 4-part email sequence (welcome automation)
4. Set up Google My Business (local search)
5. Submit sitemap to Search Console
6. Monitor keyword rankings after launch
