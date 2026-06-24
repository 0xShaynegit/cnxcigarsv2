# CNX Cigars Handover
**Session:** 24/06/2026 (fourth pass)
**Branch:** master
**Deploy:** Cloudflare Workers via GitHub (0xShaynegit/cnxcigarsv2)
**Live URL:** https://cnxcigarsv2.slrclaude.workers.dev

---

## Current State

Site is live and building correctly. Chaty widget working on live site with 5 channels including email. PageSpeed 96 accessibility, 100 SEO. All CTAs route to services.html#reserve.

---

## What Was Done This Session (fifth pass)

### All CTAs to services.html#reserve
- All WhatsApp CTA buttons, `href="#contact"`, `href="#b2b"` replaced with `./services.html#reserve` across all 11 pages
- Legal pages: `./#contact` links also updated

### About Section: Sticky Scroll Replaced with Parallax
- Removed `position:sticky` + 110vh spacer (`.about-spacer{height:0}`)
- `.about-sticky` is now `position:relative; height:100svh; overflow:hidden`
- Background image: `height:125%; margin-top:-12%` for parallax travel room
- JS: simple `translateY` based on section scroll position (18% range), runs on init
- No more dead scroll space on desktop or mobile

### Tobacco Legal Disclaimer
- Added `.ft-legal` bar at very bottom of every footer (below `</div>` wrap, inside `<footer>`)
- Text: "Online sale of tobacco is strictly prohibited in the Kingdom of Thailand including sales to persons under 20 years."
- Style: small caps, muted, full-width, centred. Applied to all 11 pages via PowerShell batch.

### Recognition Section
- Previous section had text placeholders only, no images
- Downloaded Habanos Point + Asia Iconic badge PNGs from source site, converted to WebP
- Images: `cnxcigars-cnx-cigars-habanos-point-authorized-dealer.webp` (23KB), `cnxcigars-cnx-cigars-asia-iconic-excellence-innovation-award-2026.webp` (21KB)
- Restaurant Guru badge already existed: `cnxcigars-cnx-cigars-restaurant-guru-excellent-service-award.webp`
- Section redesigned: flex row, badges as `<img>` with name/sub text below
- CSS: `.rec-item img` 150x150, `.rec-item.rec-card img` height:180 (for rectangular RG card)
- Background changed to `var(--ink-2)`

### Footer Social Icons (replaces text links)
- Removed "WhatsApp: +66 622 769 937 / LINE: Bodazey / email" plain text from footer brand column
- Added `.ft-social` icon row: WhatsApp, LINE, Facebook, Messenger, Email (36px circles, gold on hover)
- WA + LINE hrefs set at runtime via `atob()` inline script (same obfuscation as Chaty)
- IDs: `ft-wa`, `ft-line`

### Contact Section Links
- WhatsApp button in contact section: `id="contact-wa-btn"`, href set via obfuscated JS
- Contact grid: WhatsApp number and LINE are now `<a>` tags with `id="contact-wa-link"` / `id="contact-line-link"`, hrefs set via obfuscated JS
- Email: plain `mailto:cigarschiangmai@gmail.com`
- "Use our contact form" links to `./services.html#reserve`
- Obfuscation script at bottom of inline `<script>` block in index.html

### Chaty Widget: Email Added (v4)
- Added 5th channel: Email (envelope SVG, `mailto:cigarschiangmai@gmail.com` via atob)
- `EMAIL_URL = atob('bWFpbHRvOmNpZ2Fyc2NoaWFuZ21haUBnbWFpbC5jb20=')`
- Cache version bumped to `?v=4` across all 11 pages

---

## Still Pending Before Delivery

1. **Age gate** - remove `style="display:none"` from `<div id="gate">` in index.html
2. **Analytics token** - replace `ANALYTICS_TOKEN_PLACEHOLDER` in all 11 pages (causes harmless CORS error in console until fixed)
3. **Browser verify** - full scroll desktop + mobile on all pages before launch
4. **OG social card image** - all pages use logo (black on black on social). Needs proper 1200x630 dark scene image. Low priority.
5. **Google Business Profile** - set up post-launch
6. **Search Console** - submit sitemap post-launch

---

## Architecture Notes

- **Vanilla HTML/CSS/JS only. Zero frameworks.**
- **No dist folder.** Files served from repo root via `.assetsignore`
- **Worker** (not Pages): `wrangler.toml` with `[assets] directory = "."`
- **Chaty widget**: `scripts/chaty-widget.js?v=4` on all 11 pages. 5 channels: WA, LINE, FB, Messenger, Email.
- **Fonts**: WOFF2 from `./fonts/woff2/` with `font-display:swap`
- **Images**: WebP only, `./images/`
- **Obfuscation pattern**: WA and LINE URLs decoded at runtime via `atob()`. Used in Chaty widget AND footer/contact inline script.

## File Line Endings (Critical)

collection.html = **CRLF** (`\r\n`)
accessories.html = **LF** (`\n`)
Other files vary. Always check before any PowerShell string replacement.

---

---

## What Was Done This Session (fifth pass)

### About Section: Sticky Scroll Replaced with Parallax
- Removed `position:sticky` + 110vh spacer
- `.about-sticky` now `position:relative; height:100svh; overflow:hidden`
- Background image `height:125%; margin-top:-12%` for parallax travel room
- JS: `translateY` based on section scroll position (18% range), runs on init

### Tobacco Legal Disclaimer
- `.ft-legal` bar added to footer on all 11 pages via PowerShell batch
- Moved above the `border-top` line (outside `.ft-bottom`, inside `.wrap`)
- Full brightness (opacity removed), centred, small caps

### Recognition Section
- Downloaded Habanos Point + Asia Iconic badge PNGs from reference site, converted to WebP
- `cnxcigars-cnx-cigars-habanos-point-authorized-dealer.webp` (23KB)
- `cnxcigars-cnx-cigars-asia-iconic-excellence-innovation-award-2026.webp` (21KB)
- Section redesigned: flex row, badges as `<img>`, name/sub text below
- Background changed to `var(--ink-2)`

### Footer Consolidation
- Removed entire `<!-- CONTACT -->` section (was duplicate of footer info)
- `<footer id="contact">`   footer now serves as the contact anchor
- 3-column layout: Brand + social icons | Visit + Enquiries | Explore + Newsletter
- Visit column: full address + hours
- Enquiries column: merged into Visit column below hours
- Newsletter description paragraph restored above form
- Responsive: 2-col at 1100px, 1-col at 768px

### Footer Social Icons
- All 5 social links (WA, LINE, FB, Messenger, Email) as 36px icon circles
- WA, LINE, Email obfuscated via `atob()` inline script
- FB and Messenger are plain hrefs (public pages, no obfuscation needed)
- IDs: `ft-wa`, `ft-line`, `ft-fb`, `ft-msg`, `ft-email`
- Obfuscation script at bottom of inline `<script>` block in index.html

### Chaty Widget: Email Added (v4)
- 5th channel: Email (envelope SVG, `mailto:` via atob)
- Cache bumped to `?v=4` across all 11 pages

### Founding Story Added
- index.html founder section: new paragraph with 2022 Chiang Mai arrival, community events phase, May 2024 official opening
- founder.html "Rooted in Chiang Mai" section: same narrative expanded into full paragraph before the existing copy

### Site Comparison vs Reference (cnx-cigars.cnxcigarwebhosting.workers.dev)
- Our site has MORE content overall (age gate, FAQ, testimonials, stats, accessories)
- Only meaningful gap was the founding story dates   now fixed
- Reference site uses Next.js; ours is vanilla

---

## Current Commit

b3895f9 - Add founding story: 2022 arrival, community phase, May 2024 opening
