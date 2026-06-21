# CNX Cigars Handover
Updated: 21/06/2026

## Where We Are

Vanilla rebuild essentially complete. All pages built and deployed to Cloudflare Workers via GitHub.

- **Homepage:** `index.html` - full build, all sections done
- **Founder:** `founder.html` - Amir Nadimi full biography, 6 sections
- **About:** `about.html` - CNX Cigars company page, 6 sections
- **Brands:** `brands/index.html` - pre-existing
- **Services:** `services.html` - pre-existing OLD template, do not use as design reference

## What Was Done This Session (21/06/2026)

- Replaced cigar cursor with dot cursor (gold dot + lagging ring, vanilla)
- Built testimonials carousel with 6 real Google reviews (3 per page)
- All 20 real reviews saved to `reviews-bank.md`
- Fixed 3 broken image references
- Removed transparent ghost portrait from hero
- Added founder portrait (red blazer) to founder section
- Fixed descender clip on hero h1 (padding-bottom:.18em on .w wrapper)
- Collections: all cigar-only photos
- Removed all double hyphens from copy
- Added 5 new homepage sections: stats, community, bar, B2B/HORECA, recognition
- Phone number: +66 622 769 937 (wa.me/66622769937 live)
- LINE: Bodazey and email in contact + footer
- Created founder.html (same design system as homepage)
- Created about.html (same design system as homepage)
- Gallery: 3rd photo = opening-night-fisheye, 5th = teal-reserved-seating-nook

## Pending Before Delivery

1. **Unhide age gate** - remove `style="display:none"` from `<div id="gate">` in index.html
2. **Analytics token** - replace `ANALYTICS_TOKEN_PLACEHOLDER` in all 5 pages (index, founder, about, services, brands/index)
3. **Chaty widget** - WhatsApp +66 622 769 937, LINE: Bodazey
4. **Browser verify** - desktop + mobile full scroll

## Key Technical Notes

- Build: `npm run build && npx wrangler deploy`
- Build copies: index.html services.html founder.html about.html brands favicon fonts images _headers robots.txt sitemap.xml site.webmanifest
- Design template: index.html / founder.html / about.html (NOT services.html - old template)
- Fonts: `./fonts/woff2/` from root
- Vimeo hero: video ID 1203211104

## Next Session

Browser verify full site desktop + mobile, then unhide age gate, replace analytics tokens, set up Chaty, ship.
