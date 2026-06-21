# CNX Cigars   Design Brief

**Visual Concept**: "The Underground Humidor Lab"  
An elite engineering approach to legacy cigar curation. Dark, ultra-premium, cinematic, mathematically precise. No generic hospitality templates.

## Master Palette

| Token | Value | Purpose |
|-------|-------|---------|
| `--bg-deep` | #0a0a0a | Primary layout canvas (deep obsidian black) |
| `--bg-charcoal` | #121212 | Container & card backgrounds |
| `--gold-primary` | #D4AF37 | Brushed gold accent, legacy anchors |
| `--gold-glow` | rgba(212, 175, 55, 0.15) | Volumetric glow on hover/focus |
| `--text-cream` | #f5f5f0 | Primary text (soft slate cream, high contrast) |
| `--text-muted` | #8a8a8a | Auxiliary details (tobacco ash grey) |

## Typography

| Use | Font | Weight | Spacing |
|-----|------|--------|---------|
| Headings | Cinzel, serif | 500-700 | letter-spacing: 0.08em |
| Body | Inter, sans-serif | 300-600 | line-height: 1.65 |

## Component System

### Lux Card
- Background: `--bg-charcoal`
- Border: 1px solid rgba(214, 175, 55, 0.2)
- Border-radius: 0px (hard edges)
- Padding: 2.5rem
- Hover: translateY(-4px), border-color shifts to `--gold-primary`, shadow 0 12px 30px rgba(0,0,0,0.7)
- Glow effect: ::before pseudo-element, 135deg gradient, opacity 0→1 on hover

### Age Gate Overlay
- Position: fixed, full viewport (100vw × 100vh)
- Z-index: 99999
- Background: `--bg-deep`
- Panel max-width: 500px
- Button style: Transparent bg, 1px gold border, cream text, hover reverses (gold bg, black text)

### Bento Grid
- Display: grid, 12 columns
- Gap: 1.5rem
- Max-width: 1400px
- Large items: span 8 cols
- Small items: span 4 cols
- Mobile (max-width: 991px): all items span 12 cols

## Interaction Design

| Element | State | Effect |
|---------|-------|--------|
| Lux card | Hover | Lift 4px, gold border glow, shadow |
| Button | Hover | Invert colors (gold ↔ black) |
| Age gate | Dismiss | Fade out (opacity 0.6s), reveal main content |

## Accessibility
- Minimum contrast: WCAG AA (#D4AF37 on #0a0a0a passes)
- Keyboard focus: Explicit tab-indexing on buttons
- Reduced motion: Respect `prefers-reduced-motion` (no auto-animations)

## Brand Voice
- Formal, authoritative, elite
- Legacy emphasis (30 years, Amir Nadimi expertise)
- Trust through precision and verification language
- No hype, no urgency, no generic luxury clichés
