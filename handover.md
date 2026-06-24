# CNX Cigars Handover
**Session:** 24/06/2026 (third pass)
**Branch:** master
**Deploy:** Cloudflare Workers via GitHub (0xShaynegit/cnxcigarsv2)
**Live URL:** https://cnxcigarsv2.slrclaude.workers.dev

---

## Current State

Site is live and building correctly. Chaty widget working on live site. PageSpeed 96 accessibility, 100 SEO.

---

## What Was Done This Session

### Chaty Widget (bespoke, no external CSS)
- Built from scratch: gold trigger (52px), 4 channels (WhatsApp, LINE, Facebook, Messenger)
- WA + LINE URLs obfuscated with `atob()` base64
- MutationObserver waits for `#preloader` removal before init (index.html); immediate on all other pages
- **Desktop hover-to-open**: channels fan out on trigger mouseenter, close on mouseleave (260ms timer). Channel rows cancel the timer while mouse is over them.
- Trigger icon swaps to CNX circle logo (`cnxcigars-cnx-cigars-logo-circle.webp`, 52x52, overflow:hidden) on open/hover; reverts to chat bubble on close
- Labels hidden by default, appear in gold on hover (desktop only)
- "Chat now" label appears on desktop hover + bottom-left zone mousemove
- Mobile: tap to open/close only, no hover states
- File: `scripts/chaty-widget.js`
- Loaded via `<script src="./scripts/chaty-widget.js?v=3" defer></script>` on all 11 pages

### Worker Deploy Fix
- `wrangler.toml` was pointing to `./dist` but site has no build step
- Fix: `directory = "."` + `.assetsignore` file excludes `.git/`, `_archive/`, `*.md`, `*.toml`, `*.json`, `node_modules/`, `dist/`
- Build command in Cloudflare dashboard: `npx wrangler deploy` (no npm run build)

### Performance
- Vimeo iframe deferred to `window.load` (no longer blocks first paint)
- Preloader halved: 1400ms to 700ms
- Hero logo resized: 960x960 (132KB) to 260x260 (16KB)
- Vimeo preconnects added: `player.vimeo.com`, `f.vimeocdn.com`, `skyfire.vimeocdn.com`

### Accessibility (78 to 96)
- `role="button"` + `tabindex="0"` on chat trigger div
- `title="CNX Cigars Lounge"` + `aria-hidden="true"` on Vimeo iframe
- `aria-label="Scroll down"` on `.h-arrow` hero link
- `.testi-dot` touch target: padding 11px (28px hit area from 6px dot)
- Footer `h4` changed to `h3` (heading order fix); CSS selector updated

### Collections Carousel Fix
- Arrows were broken: `scrollBy()` doesn't work without `overflow` on the element
- Rewrote entire carousel to use `transform: translateX` (autoplay, drag, touch, buttons all use offset variable)
- Smooth 0.5s transition on button clicks; autoplay resumes cleanly after

### Mobile Hero
- At max-width 768px: hero height reduced to 55svh (min 320px)
- Hero logo halved: 36px on mobile (from 70px minimum)

### Collection Page: 1 Column Mobile
- Breakpoint extended from 768px to 960px
- Switched from `flex` override to `display:grid; grid-template-columns:1fr` for guaranteed single column

### Collection CTA
- "Ask the team for a recommendation" button links to `./services.html`

### Cache Fix
- `/scripts/*` `_headers` changed from `immutable` to `max-age=3600, must-revalidate`
- All pages updated to `chaty-widget.js?v=3` to bust cached old widget version

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
- **All 11 pages** share the same chaty widget script via `?v=3` cache buster
- **Fonts**: WOFF2 from `./fonts/woff2/` with `font-display:swap`
- **Images**: WebP only, `./images/`

## File Line Endings (Critical)

collection.html = **CRLF** (`\r\n`)
accessories.html = **LF** (`\n`)
Other files vary. Always check before any PowerShell string replacement.

---

## Current Commit

b75a39d - Collection CTA: link to services page
