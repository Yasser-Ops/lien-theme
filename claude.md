## Project

Aurelle — premium modern beauty DTC brand on Shopify. Single hero skincare product (for now), but architecture must stay general so products can be swapped organically. Store: `test1-239283829347123859139053.myshopify.com`. Theme built as a Dawn fork with heavy visual customization to achieve a luxury editorial aesthetic. Text logo for now.

**Deployment:** TBD — likely GitHub auto-sync to unpublished theme. Must publish via Shopify admin to go live.

## Commands

```bash
shopify theme dev --store <store>.myshopify.com          # Local dev (hot reload, proxies store data)
shopify theme push --unpublished                         # New unpublished theme
shopify theme push --theme <id>                          # Push to specific theme
shopify theme list                                       # List themes
```

Requires Node.js 18+, Shopify CLI. No local Liquid rendering — dev server requires internet.

## Architecture

**Dawn fork** — Dawn provides cart, Liquid, checkout, base OS 2.0 infrastructure. We own the visual layer via `aurelle-*` prefixed files. Dawn's core files stay unmodified where possible.

**Shopify OS 2.0:** All sections must be modular, movable, removable, duplicatable, configurable from the Shopify editor. Repetitive content MUST use blocks, not numbered settings (`feature_1`, `feature_2`).

### Pages (V1)

| Page | Template | Notes |
| --- | --- | --- |
| Homepage | `index.json` | Hero → Trust Bar → Featured Product → How It Works → Why Aurelle → Reviews → CTA Banner |
| Product | `product.json` | TBD — dynamic product with variants, add-to-cart |
| Collection | TBD | Future expansion |

### Key Sections (Homepage)

- `aurelle-hero` — Split layout, cinematic imagery left, strong typography + dual CTAs + social proof right. Responsive stacking.
- `aurelle-trust-bar` — Block-based icon + text pairs (free shipping, guarantee, secure checkout, dermatologist tested). Reorderable.
- `aurelle-featured-product` — Dynamic Shopify product selector, variant pricing, compare-at price, feature bullets as blocks, add-to-cart, urgency badge.
- `aurelle-how-it-works` — Numbered step cards as blocks. Icon support. Add/remove/reorder/duplicate.
- `aurelle-why-aurelle` — Dark premium section. Card-based layout with hover interactions. Cards as blocks.
- `aurelle-reviews` — Review cards as blocks. Star ratings, verified purchase badges, avatars. Add/delete/reorder.
- `aurelle-cta-banner` — Oversized typography, luxury spacing, strong CTA button, premium contrast.

### Key Snippets

- TBD — extract reusable patterns (buttons, badges, cards, icons) into snippets as sections are built.

## Design System

**Typography:** Large elegant type, thick sans-serif direction. Two fonts:
- **Headings:** Outfit (bold, geometric, premium thickness)
- **Body:** Inter (clean, modern readability)
Loaded via Google Fonts. Generous spacing, strong hierarchy.

**CSS:** `aurelle-base.css` (tokens + utilities), per-section CSS files (`aurelle-hero.css`, etc.). Vanilla CSS, custom properties, `aurelle-` prefix. No framework.

**Tokens:**

```css
/* Colors */
--aurelle-color-gold: #B8956A;        /* Accents, highlights, luxury cues */
--aurelle-color-cream: #F5F0EB;       /* Soft backgrounds, warmth */
--aurelle-color-dark: #1C1C1C;        /* Typography, CTA grounding */
--aurelle-color-offwhite: #FAFAF8;    /* Page backgrounds, minimalism */

/* Spacing — TBD, establish rhythm */
--aurelle-section-padding-desktop: 100px;
--aurelle-section-padding-mobile: 60px;
--aurelle-margin-desktop: 60px;
--aurelle-margin-mobile: 20px;
```

**Responsive:** Mobile-first. Primary breakpoint TBD (likely 768px and 1024px). Mobile must feel premium and spacious, not compressed. Large tap targets, clean stacking, readable type.

**Interactions:** Premium micro-interactions only. Subtle hover effects, smooth transitions (150–300ms). No flashy gradients, aggressive motion, or excessive shadows. The site must feel calm and sophisticated.

## Coding Standards

### Liquid

- Modern Shopify syntax: `image_url`, `render` (not `include`), schema-driven settings, dynamic objects
- No massive inline logic, no repeated code, no hardcoded repetitive settings
- Every section gets a full `{% schema %}` with `settings` and `blocks` where appropriate

### CSS

- CSS custom properties for all design tokens
- Responsive-first, utility-like consistency
- Minimal animation, premium transitions
- No flashy gradients, excessive shadows, or cluttered spacing

### JavaScript

- JS enhances UX, does not dominate
- Use for: quick add, sliders, animations, sticky CTA, dynamic interactions
- No bloated libraries or unnecessary frameworks
- Vanilla JS preferred

### Performance

- Lazy loading for images
- Optimized image sizing via Shopify `image_url` filters
- Minimal JS payload
- Reusable CSS
- Low cumulative layout shift

## Brand Voice

Refined, confident, feminine, calm sophistication. The store should emotionally communicate: "This is a real premium beauty brand."

**Tone:** Luxurious but minimal. Feminine without being cliché. Elegant without being cold. Editorial and cinematic.

**Never feel:** Overcrowded, flashy, cheap, gimmicky, "AliExpress", over-animated, "dropshippy."

## Development Workflow

1. Design section in HTML + CSS + JS (static prototype)
2. Refine responsiveness, spacing, aesthetics, interactions
3. Convert into Shopify Liquid section
4. Add schema, blocks, dynamic settings
5. Integrate into Dawn-based architecture

## Future Expansion

Architecture must support adding without major rewrites:
- FAQ accordions
- Bundles
- Collection showcases
- TikTok/video embeds
- Before/after sliders
- Comparison tables
- Announcement bars
- Influencer testimonials
- UGC galleries
- Sticky add-to-cart
- Metafields/metaobjects

## Reference Docs

- `aurelle_shopify_theme_prd.md` — Full PRD with section specs, visual direction, technical philosophy
