# Aurelle — Shopify Theme Product Requirements Document (PRD)

## Vision

Aurelle is a premium modern beauty brand designed to feel:

- luxurious but minimal
- feminine without being cliché
- elegant without being cold
- conversion-focused without looking “dropshippy”
- editorial and cinematic rather than template-based

The store should emotionally communicate:

> “This is a real premium beauty brand.”

The experience should feel closer to:

- modern luxury skincare brands
- high-end cosmetics campaigns
- fashion editorial landing pages

rather than:

- generic Shopify templates
- aggressive TikTok-style dropshipping stores
- cluttered ecommerce layouts

---

# Core Brand Identity

## Brand Name

Aurelle

## Brand Personality

- refined
- confident
- feminine
- modern
- soft luxury
- calm sophistication
- premium simplicity

## Emotional Goal

Users should feel:

- trust
- aspiration
- elegance
- self-care
- exclusivity
- confidence

---

# Visual Direction

## Design Language

The theme should use:

- large elegant typography
- soft spacing
- asymmetrical layouts
- cinematic product imagery
- minimal clutter
- generous whitespace
- premium micro-interactions

The site should never feel:

- overcrowded
- flashy
- cheap
- gimmicky
- “AliExpress”
- over-animated

---

# Color System

## Core Palette

### Gold

```css
#B8956A
```

Used for:
- highlights
- accents
- premium cues
- luxury contrast

### Cream

```css
#F5F0EB
```

Used for:
- soft backgrounds
- warmth
- elegance

### Dark

```css
#1C1C1C
```

Used for:
- typography
- premium contrast
- CTA grounding

### Off White

```css
#FAFAF8
```

Used for:
- page backgrounds
- cleanliness
- minimalism

---

# Technical Philosophy

## IMPORTANT

The theme must NOT be built as:

- one giant homepage file
- one mega Liquid section
- hardcoded content

The theme MUST use:

- Shopify Online Store 2.0 architecture
- modular sections
- reusable snippets
- dynamic blocks
- schema-driven content

---

# Theme Architecture

## Folder Structure

```text
assets/
sections/
snippets/
layout/
templates/
config/
```

---

# Section Philosophy

Every major homepage area should be:

- independent
- movable
- removable
- duplicatable
- configurable

Sections should be individually manageable from the Shopify editor.

---

# Homepage Structure

## 1. Hero Section

### Purpose

Create immediate emotional impact.

### Requirements

- split layout
- cinematic imagery
- strong typography
- elegant CTA buttons
- social proof
- minimal but premium copywriting

### Features

- editable image
- editable title
- editable subtitle
- dual CTA buttons
- optional proof area
- responsive layout

### UX Goal

User should immediately understand:

- this is a premium beauty brand
- products are luxurious
- the experience feels trustworthy

---

# 2. Trust Bar

### Purpose

Reinforce trust and purchase confidence.

### Requirements

- block-based system
- reorderable items
- icon + text pairs
- responsive wrapping

### Examples

- free shipping
- money-back guarantee
- secure checkout
- dermatologist tested

---

# 3. Featured Product Spotlight

### Purpose

Push the hero product as the centerpiece.

### Requirements

- dynamic Shopify product
- variant pricing
- compare-at pricing
- dynamic features list
- add-to-cart support
- urgency badge

### Architecture

Feature bullets MUST use blocks.

---

# 4. How It Works

### Purpose

Simplify the customer journey.

### Requirements

- step cards
- icon support
- numbered layout
- responsive stacking
- editable steps

### Architecture

Each step must be a block.

Merchant should be able to:

- add steps
- remove steps
- reorder steps
- duplicate steps

---

# 5. Why Aurelle

### Purpose

Differentiate the brand from competitors.

### Requirements

- premium dark section
- card-based layout
- elegant hover interactions
- strong copy hierarchy

### Architecture

Cards MUST be blocks.

---

# 6. Reviews Section

### Purpose

Provide emotional social proof.

### Requirements

- review cards
- verified purchase cues
- star ratings
- elegant avatars
- strong readability

### Architecture

Reviews MUST use blocks.

Merchant must be able to:

- add reviews
- delete reviews
- reorder reviews

---

# 7. CTA Banner

### Purpose

Drive final conversion intent.

### Requirements

- oversized typography
- luxury spacing
- strong CTA button
- premium contrast
- simple focused layout

---

# Shopify Editor Experience

## Core Requirement

Everything repetitive should use blocks.

Avoid:

```json
feature_1
feature_2
feature_3
```

Prefer:

```json
blocks
```

because blocks allow:

- add
- delete
- duplicate
- reorder
- insert between

which is central to Shopify 2.0.

---

# Coding Standards

## Liquid

Use:

- modern Shopify syntax
- `image_url`
- `render`
- schema-driven settings
- dynamic objects

Avoid:

- outdated filters
- massive inline logic
- repeated code
- hardcoded repetitive settings

---

# CSS Standards

## Requirements

Use:

- CSS variables
- utility-like consistency
- responsive-first design
- minimal animation
- premium transitions

Avoid:

- flashy gradients
- excessive shadows
- aggressive motion
- cluttered spacing

---

# JavaScript Standards

## Philosophy

JavaScript should enhance UX, not dominate it.

### Use JS for:

- quick add
- sliders
- animations
- sticky CTA
- dynamic interactions

### Avoid:

- bloated libraries
- unnecessary frameworks
- excessive frontend complexity

---

# Performance Goals

## Theme Must Feel:

- fast
- lightweight
- premium
- smooth

### Requirements

- lazy loading
- optimized images
- minimal JS
- reusable CSS
- low layout shift

---

# Mobile Experience

## CRITICAL

The mobile version must feel:

- premium
- spacious
- intentional
- not compressed

### Mobile Goals

- large tap targets
- clean stacking
- readable typography
- smooth scrolling
- no cramped layouts

---

# Future Expansion

The architecture should support future sections such as:

- FAQ accordions
- bundles
- collection showcases
- TikTok/video embeds
- before/after sliders
- comparison tables
- announcement bars
- influencer testimonials
- UGC galleries
- sticky add-to-cart
- metafields/metaobjects

without requiring major rewrites.

---

# Development Workflow

## Preferred Workflow

### Step 1

Design section in:

- HTML
- CSS
- JS

### Step 2

Refine:

- responsiveness
- spacing
- aesthetics
- interactions

### Step 3

Convert into Shopify Liquid section.

### Step 4

Add:

- schema
- blocks
- dynamic settings

### Step 5

Integrate into Dawn-based architecture.

---

# Primary Goal

Build a Shopify storefront that:

- looks custom
- feels premium
- converts effectively
- scales cleanly
- avoids generic theme aesthetics
- creates a believable luxury beauty identity

while remaining:

- modular
- maintainable
- Shopify-native
- editor-friendly
- performant
.

