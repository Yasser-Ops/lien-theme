# Lien — Shopify Theme Product Requirements Document (PRD)

## Vision

Lien is a modern romantic accessories brand designed to feel:

- clean and minimal
- romantic without being cheesy
- editorial and cinematic
- conversion-focused without looking "dropshippy"
- modern and couple-oriented

The store should emotionally communicate:

> "This is a real brand made for couples."

The experience should feel closer to:

- modern minimalist jewelry brands
- couple lifestyle editorial content
- clean DTC accessories campaigns

rather than:

- generic Shopify templates
- aggressive TikTok-style dropshipping stores
- cluttered ecommerce layouts

---

# Core Brand Identity

## Brand Name

Lien

## Brand Personality

- modern
- romantic
- minimal
- clean
- confident
- calm
- editorial

## Emotional Goal

Users should feel:

- connection
- love
- trust
- modern elegance
- gifting intent
- "this is made for us"

---

# Visual Direction

## Design Language

The theme should use:

- large clean typography
- cool-toned color palette
- generous whitespace
- cinematic product imagery
- asymmetrical editorial layouts
- premium micro-interactions
- minimal decoration

The site should never feel:

- overcrowded
- flashy
- cheap
- gimmicky
- "AliExpress"
- over-animated

---

# Color System

## Core Palette

### Accent (Blue-Slate)

```css
#7B8FA6
```

Used for:
- CTA buttons
- highlights
- accent elements
- hover states

### Cool Off-White

```css
#EEF1F5
```

Used for:
- section backgrounds
- card fills

### Dark

```css
#1A1C22
```

Used for:
- typography
- dark sections
- premium contrast

### Page Background

```css
#F7F9FC
```

Used for:
- main page background
- cleanliness
- modern minimalism

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

Create immediate emotional impact for couples.

### Requirements

- split layout
- cinematic product imagery
- strong typography
- elegant CTA buttons
- social proof
- minimal but romantic copywriting

### Features

- editable image
- editable title
- editable subtitle
- dual CTA buttons
- optional proof area
- responsive layout

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
- ships as a gift set

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

---

# 5. Why Lien

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

Provide emotional social proof from real couples.

### Requirements

- review cards
- verified purchase cues
- star ratings
- elegant avatars
- strong readability

### Architecture

Reviews MUST use blocks.

---

# 7. CTA Banner

### Purpose

Drive final conversion intent.

### Requirements

- oversized typography
- generous spacing
- strong CTA button
- premium contrast
- simple focused layout

---

# Shopify Editor Experience

## Core Requirement

Everything repetitive should use blocks, not numbered settings.

---

# Coding Standards

## Liquid

Use:

- modern Shopify syntax
- `image_url`
- `render`
- schema-driven settings
- dynamic objects

---

# CSS Standards

Use:

- CSS variables
- responsive-first design
- minimal animation
- premium transitions

Avoid:

- flashy gradients
- excessive shadows
- aggressive motion

---

# JavaScript Standards

JS should enhance UX, not dominate it. Vanilla JS preferred. No bloated libraries.

---

# Performance Goals

- lazy loading
- optimized images via `image_url`
- minimal JS payload
- low cumulative layout shift

---

# Mobile Experience

Mobile must feel premium, spacious, and intentional. Large tap targets, clean stacking, readable type.

---

# Primary Goal

Build a Shopify storefront that looks custom, feels modern and romantic, converts effectively, and avoids generic theme aesthetics — while remaining modular, Shopify-native, and editor-friendly.
