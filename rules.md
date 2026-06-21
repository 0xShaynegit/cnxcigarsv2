# CNX Cigars   Project Rules

## Brand & Positioning
- **Owner**: Amir Nadimi (30-year legacy, certified specialist)
- **Market**: Chiang Mai luxury cigar lounge & B2B hospitality procurement
- **Regulatory**: Thai Tobacco Law compliance   age gate (20+) mandatory
- **Revenue Model**: B2C lounge access (physical), B2B hospitality consulting (no online sales)

## Architecture
- **Template**: Single bespoke template (`template.html`)
- **Pages**: 
  - `/index.html`   homepage, age gate, legacy/authority
  - `/services.html`   B2C lounge, B2B hospitality procurement intake
  - `/brands/index.html`   brand directory, authenticity verification
- **No direct sales mechanisms**   all transactions route to LINE/WhatsApp secure channels

## Design System
- **Palette**: Deep obsidian (#0a0a0a), charcoal (#121212), brushed gold (#D4AF37), cream (#f5f5f0), ash grey (#8a8a8a)
- **Fonts**: Cinzel (headings, serif), Inter (body, sans-serif)
- **Layout**: Hard-edged cards, zero border-radius, bento grid, gold glow on hover
- **Concept**: "The Underground Humidor Lab"   dark, ultra-premium, cinematic, mathematically precise

## SEO Strategy
- **Pillar 1**: Local authority hub   "Best Cigar Lounge Chiang Mai", "Amir Nadimi Cigars"
- **Pillar 2**: Experiential services   "Private Cigar Tasting Thailand", "Resort Cigar Procurement"
- **Pillar 3**: Brand authentication   "Authentic Montecristo Chiang Mai", "Partagas Stockist Thailand"
- **Schema**: Organization + LocalBusiness + Service + FAQPage (all at root)

## Technical
- **Stack**: Vanilla HTML5, CSS3, ES6 (no frameworks)
- **Fonts**: Local WOFF2 only (no CDN)
- **Analytics**: Cloudflare Web Analytics token in all pages
- **Deployment**: Cloudflare Pages (no Vercel)
- **Portability**: All paths relative, no external dependencies

## Non-Negotiables
1. Age gate before any content access (localStorage key: `cnx_age_verified`)
2. No framework imports (vanilla only)
3. WCAG AA contrast compliance (gold on black verified)
4. Keyboard navigation support
5. Mobile-first responsive design
6. One page tested before propagating to others
