## Project

Lien — modern romantic accessories brand on Shopify. Hero product: magnetic couple bracelets (black & white cord, heart charm). Architecture stays general so products can expand to other couple/jewelry accessories. Store: TBD. Theme built as a Dawn fork with a cool-toned modern aesthetic — less luxury beauty, more clean editorial romance.

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

**Dawn fork** — Dawn provides cart, Liquid, checkout, base OS 2.0 infrastructure. We own the visual layer via `lien-*` prefixed files. Dawn's core files stay unmodified where possible.

**Shopify OS 2.0:** All sections must be modular, movable, removable, duplicatable, configurable from the Shopify editor. Repetitive content MUST use blocks, not numbered settings (`feature_1`, `feature_2`).

### Pages (V1)

| Page | Template | Notes |
| --- | --- | --- |
| Homepage | `index.json` | Hero → Trust Bar → Featured Product → How It Works → Why Lien → Reviews → CTA Banner |
| Product | `product.json` | Dynamic product with variants, add-to-cart |
| Collection | TBD | Future expansion |

### Key Sections (Homepage)

- `lien-hero` — Split layout, cinematic imagery left, strong typography + dual CTAs + social proof right. Responsive stacking.
- `lien-trust-bar` — Block-based icon + text pairs (free shipping, guarantee, secure checkout, couple-focused trust cues). Reorderable.
- `lien-featured-product` — Dynamic Shopify product selector, variant pricing, compare-at price, feature bullets as blocks, add-to-cart, urgency badge.
- `lien-how-it-works` — Numbered step cards as blocks. Icon support. Add/remove/reorder/duplicate.
- `lien-why-lien` — Dark premium section. Card-based layout with hover interactions. Cards as blocks.
- `lien-reviews` — Review cards as blocks. Star ratings, verified purchase badges, avatars. Add/delete/reorder.
- `lien-cta-banner` — Oversized typography, luxury spacing, strong CTA button, premium contrast.

### Key Snippets

- Extract reusable patterns (buttons, badges, cards, icons) into snippets as sections are built.

## Design System

**Typography:** Large elegant type, thick sans-serif. Two fonts:
- **Headings:** Outfit (bold, geometric, modern)
- **Body:** Inter (clean, modern readability)
Loaded via Google Fonts. Generous spacing, strong hierarchy.

**CSS:** `lien-base.css` (tokens + utilities), per-section CSS files (`lien-hero.css`, etc.). Vanilla CSS, custom properties, `lien-` prefix. No framework.

**Tokens:**

```css
/* Colors */
--lien-accent: #7B8FA6;        /* Cool blue-slate — accents, highlights, CTA */
--lien-accent-hover: #6B7E95;
--lien-accent-light: #9AAFC2;
--lien-cream: #EEF1F5;         /* Cool off-white backgrounds */
--lien-dark: #1A1C22;          /* Cool near-black — typography, dark sections */
--lien-offwhite: #F7F9FC;      /* Cool page background */
--lien-text-secondary: #4A5568;
--lien-text-muted: #8896A8;
--lien-border: #DDE3EB;

/* Spacing */
--lien-section-padding-desktop: 100px;
--lien-section-padding-mobile: 60px;
--lien-container-max: 1400px;
```

**Responsive:** Mobile-first. Primary breakpoints: 768px and 1024px. Mobile must feel premium and spacious. Large tap targets, clean stacking, readable type.

**Interactions:** Subtle hover effects, smooth transitions (150–300ms). No flashy gradients, aggressive motion, or excessive shadows. Calm and modern.

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

Modern, romantic, minimal. The store should emotionally communicate: "This is a real brand for real couples."

**Tone:** Clean and confident. Romantic without being cheesy. Editorial and cinematic.

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

- `lien_shopify_theme_prd.md` — Full PRD with section specs, visual direction, technical philosophy
