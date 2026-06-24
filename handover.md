# CNX Cigars Handover
**Session:** 24/06/2026 (second pass)
**Branch:** master
**Deploy:** Cloudflare Pages via GitHub (0xShaynegit/cnxcigarsv2)

---

## Where We Left Off

SEO audit completed and all actionable fixes applied. Brands/ticker fixed. Ready for pre-delivery checklist.

---

## What Was Done This Session

### Brands Link Fix (all pages)
- `./brands/` directory never existed in the live project
- Replaced all instances with `./collection.html` across: index.html, services.html, legal-privacy-policy.html, legal-photo-disclaimer.html, legal-terms-of-service.html

### Marquee Ticker Rebuild
- Previous ticker had "Padron 1926" and "Oliva Serie V" - neither in the collection
- Rebuilt with all 35 actual collection brands (13 Cuban + 22 New World), deduplicated
- Animation slowed from 24s to 80s to match longer track

### SEO Fixes Applied
| Fix | File |
|-----|------|
| Organization schema added | index.html |
| priceRange: "500-2000+ THB" | index.html |
| No aggregateRating (client preference) | index.html |
| Twitter Card + OG image added | services.html |
| Legal pages removed from sitemap | sitemap.xml |
| noindex meta added | legal-*.html (all 3) |
| ItemList schema (Cuban + New World) added | collection.html |

---

## Still Pending Before Delivery

1. **Age gate** - remove `style="display:none"` from `<div id="gate">` in index.html
2. **Analytics token** - replace `ANALYTICS_TOKEN_PLACEHOLDER` in all 10 pages
3. **Chaty widget** - WhatsApp (+66 622 769 937) + LINE (Bodazey), bottom-left position
4. **Browser verify** - full scroll desktop + mobile on all pages
5. **OG social card image** - all pages still use logo (black on black). Needs a proper 1200x630 dark scene image. Low priority but worth noting.
6. **Google Business Profile** - set up post-launch
7. **Search Console** - submit sitemap post-launch

---

## File Line Endings (Critical)

collection.html = **CRLF** (`\r\n`)
accessories.html = **LF** (`\n`)
Other files vary. Always check before any PowerShell string replacement.

---

## Current Commit

Not yet committed. Multiple sessions of changes uncommitted.
