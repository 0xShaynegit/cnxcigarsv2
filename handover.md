# CNX Cigars - Session Handover

**Date**: 21 June 2026
**Status**: Premium vanilla rebuild complete. Project folder archived and clean. Ready for browser verification.

## What's Done
- Full premium vanilla rebuild (index.html, services.html, brands/index.html)
- Hero with B&W / colour video toggle (cnxcigars-hero-bw.mp4 default, cnxcigars-hero.mp4 colour)
- 33 lounge WebPs + 10 humidor WebPs, all under 200KB, semantically named
- Age gate hidden (display:none) for dev -- unhide before delivery
- All bare "CNX" updated to "CNX Cigars" throughout
- Archive complete: old CSS/JS/framework/TTFs moved to _archive/

## Before Delivery (in order)
1. **Unhide age gate** -- remove `style="display:none"` from `<div id="gate">` in index.html
2. **Analytics token** -- replace `ANALYTICS_TOKEN_PLACEHOLDER` in index.html, services.html, brands/index.html
3. **WhatsApp number** -- replace `66PHONENUMBER` with Amir's real number in index.html
4. **Browser verify** -- full scroll desktop + mobile, age gate fires, all CTAs work

## Project Structure (clean)
- `index.html` -- homepage (main file, 3200+ lines)
- `services.html` -- lounge + B2B intake
- `brands/index.html` -- brand cards
- `images/` -- all WebPs + 2 hero mp4s
- `fonts/woff2/` -- TrajanPro, Cormorant Garamond, DM Sans, DM Serif Display
- `favicon/` -- full set
- `_headers`, `robots.txt`, `sitemap.xml`, `site.webmanifest`

## Critical Technical Notes

### Encoding
- index.html contains UTF-8 non-breaking spaces (hex c2a0) in original template text
- These break PowerShell `-replace` regex and Edit tool string matching
- Reliable fix: Python `f.readlines()` + line-index replacement + `f.writelines()`

### Age Gate
- Gate ID: `<div id="gate" style="display:none">`
- localStorage key: `cnx_age_verified` = `'1'`
- Thai law: 20+ only

### Hero Video Toggle
- Default loads B&W version
- Button swaps src, calls `.load()` + `.play()` with 400ms opacity crossfade

## Content Reference Files (kept)
- `content-homepage-final.md` -- master copy
- `founder-bio.md` -- Amir's story
- `content-faq.md` -- FAQ
- `content-reference.md` -- full library
- `design-brief.md` -- design tokens
- `seo-report.md` -- SEO
