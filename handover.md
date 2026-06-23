# CNX Cigars Handover
Updated: 23/06/2026

## Where We Are

Vanilla rebuild complete. 7 pages live on GitHub, deployed via Cloudflare Pages. Full SEO and AI SEO pass done this session. Site is pre-delivery   3 blockers remain before ship.

## Live Pages

- `index.html` - homepage, full build
- `about.html` - company page, 6 sections
- `founder.html` - Amir Nadimi biography, 6 sections
- `collection.html` - Cuban cellar (28 vitolas, 10 marques), Founder's Picks section, New World note
- `accessories.html` - 43 items across 6 categories, same card system as collection
- `lounge.html` - Private Lounge page (VIP 4-6 + open 30+), full-bleed Google Maps embed
- `services.html` - OLD template (not design reference), reservation form at #reserve, B2B at #b2b
- `404.html` - branded, canonical nav
- `_redirects` - 301 /brands/ -> /collection.html
- `brands/index.html` - archived to `_archive/brands/`, NOT live

## Navigation (Canonical - All Pages)

Services | Collection | Accessories | The Lounge | About

Reserve a Seat CTA -> services.html#reserve on all pages.

## What Was Done This Session (22-23/06/2026)

### New Pages Built
- `collection.html` - centred card layout, 10 marque groups, Founder's Picks (4 cards), New World note
- `accessories.html` - same card system, 6 groups, 43 items
- `lounge.html` - cloned from founder.html master template, full-bleed map at bottom
- `404.html` - branded error page

### SEO Audit + Fixes
- Rebuilt `sitemap.xml` - 10 canonical URLs, /brands/ removed
- Created `_redirects` - 301 /brands/ -> /collection.html
- Archived brands/index.html to _archive/
- Homepage nav updated to canonical 5-page set (was old #anchor links)
- Homepage inline links added to collection, accessories, lounge
- All ./brands/ links replaced with ./collection.html

### AI SEO Pass
- FAQPage schema added to index.html (9 Q&A pairs)
- Person schema added to founder.html (Amir Nadimi, knowsAbout, image)
- Service schema added to services.html (OfferCatalog with 3 services)
- BreadcrumbList added to all 7 pages
- LocalBusiness schema on index.html expanded (phone, priceRange)
- robots.txt: Crawl-delay removed (redundant on Cloudflare CDN)
- `llms.txt` created (machine-readable context for AI agents)

### Copy Fixes
- "Ask Amir" -> "Ask the team" in Selection/Hospitality cards
- Added: "Amir has spent years passing his knowledge to the team and regularly quizzes them on every aspect of cigar mastery" in Selection card
- FAQ HTML and FAQPage schema both updated: "Amir and the team" -> "the team" / "CNX Cigars offers"

## Pending Before Delivery (Blockers)

1. **Unhide age gate** - remove `style="display:none"` from `<div id="gate">` in index.html
2. **Analytics token** - Amir must supply the real Cloudflare token. Replace `ANALYTICS_TOKEN_PLACEHOLDER` across all 10 pages (index, about, founder, collection, accessories, lounge, services, 404, plus legal pages)
3. **Chaty widget** - WhatsApp +66 622 769 937, LINE: Bodazey

## Key Technical Notes

- Git remote: https://github.com/0xShaynegit/cnxcigarsv2.git (branch: master)
- Deploy: Cloudflare Pages (auto-deploys from GitHub push)
- Design template: index.html / founder.html (NOT services.html - old template)
- Fonts: ./fonts/woff2/ from root
- Images: ./images/ - all WebP, all under 200KB
- Booking anchor: services.html#reserve (all Reserve CTAs point here)
- B2B anchor: services.html#b2b (all B2B CTAs point here)
- WhatsApp: https://wa.me/66622769937

## Next Session

Replace analytics token (need from Amir), unhide age gate, add Chaty widget, browser verify desktop + mobile full scroll, ship.
