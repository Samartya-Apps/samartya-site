# Samartya Apps Website — Walkthrough & Technical Implementation

This document provides a summary of the site architecture, components, and technical decisions made when building the Samartya Apps website based on the provided marketing strategy and sitemap.

## 1. Project Overview

The website is built using **Astro**, taking advantage of its lightweight, highly performant static-site generation capabilities. The structure follows the organizational plan of the sitemap and implements a cohesive, friendly, and accessible design system based on the FreeSpeech brand colors.

## 2. Technical Stack & Styling

- **Framework:** Astro (Static HTML/CSS delivery with minimal JS)
- **Styling Architecture:** Vanilla CSS. We avoided Utility-First CSS (like Tailwind) in favor of a global root variable file (`src/styles/global.css`) and scoped `<style>` blocks in Astra components. 
- **Typography:** 
  - *Headings:* `Outfit`
  - *UI & Body:* `Inter`
- **Color Palette:** Derived from the FreeSpeech logo.
  - Primary (Teal): `#46B5BA`
  - Accent (Yellow): `#FBD452`

## 3. Directory Structure & Key Files

The project files are mapped under the `src/` directory as follows:

```
src/
├── components/          # Reusable UI elements
│   ├── Button.astro     # Flexible CTA buttons (primary, secondary, outline)
│   ├── Card.astro       # Feature / Product cards
│   ├── Footer.astro     # Global footer
│   ├── Header.astro     # Global navigation
│   ├── Hero.astro       # Hero section with flexible alignment and variants
│   └── Testimonial.astro# Styled quote cards
├── layouts/             
│   └── Layout.astro     # The base HTML shell linking the CSS and web fonts
├── pages/               # File-based routing corresponding to the sitemap
│   ├── index.astro
│   ├── about.astro
│   ├── contact.astro
│   ├── research.astro
│   ├── blog/
│   │   └── index.astro
│   ├── dyslexia-reader/
│   │   └── index.astro
│   ├── for-schools/
│   │   ├── index.astro
│   │   ├── pricing.astro
│   │   └── request-trial.astro
│   └── freespeech/
│       ├── index.astro
│       ├── for-parents.astro
│       └── for-therapists.astro
└── styles/
    └── global.css       # CSS Variables (Colors, Typography, Spacing, Buttons)
```

## 4. Key Implementation Details

1. **Global CSS Variables:** We declared design tokens in `:root` inside `global.css`. By defining spacing (`--spacing-4`, `--spacing-8`), borders, and shadows globally, standardizing padding and card layouts became simple without duplicating hardcoded pixel counts.
2. **Accessible Form Construction:** Pages like `/contact` and `/for-schools/request-trial` utilize native `<form>` elements structured for screen readers, clearly demarcating `label` parameters mapping directly to `input id` fields.
3. **Responsive Grid Systems:** Standard CSS Grid was utilized with specific `@media (min-width: 768px)` breakpoints within page specific scopes and global helpers (such as the `.container` constraints) to ensure layout shifts correctly on mobile versus desktop.
4. **Placeholders:** Generic dashed rectangles were implemented for complex UI screenshots and TED Talk embeds, ready to be hot-swapped for actual image/video assets. We utilized AI to generate initial representations of the App Icons which sit within the `public/img` directory.

## 5. Running the Application

To ensure your dependencies are installed, from the root folder run:
```bash
npm install
```

To run the application locally with HMR (Hot Module Replacement) and network accessibility (so you can view it on your mobile device on the same Wifi network):
```bash
npm run dev -- --host
```

To build for production:
```bash
npm run build
```
