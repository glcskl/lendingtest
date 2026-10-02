# lendingtest — workdo landing

A landing page for the workdo ERP platform that presents one product across several verticals without duplicating the page for each of them. The marketing copy, the sections and the vertical-specific content live in one place, and the routes are generated from that data.

Built as a personal project between 26 June and 30 August 2026.

## Features

- One landing page reused by every vertical, driven by a single data module
- Vertical-specific pages under `/verticals/[vertical]`, currently covering security services
- Catch-all route that resolves slugs to page content
- Pricing section rendered from data rather than markup
- Motion handled centrally so animation behaviour stays consistent between sections
- SEO support: generated robots file and sitemap
- Minimal dependency footprint

## Tech stack

| Layer | Technology |
| --- | --- |
| Framework | Next.js with App Router |
| Language | TypeScript |
| UI | React |
| Animation | Framer Motion |
| Icons | lucide-react |
| Styling | Global CSS with PostCSS |

## Getting started

### Requirements

- Node.js 20 or newer
- npm or any compatible package manager

### Environment variables

None. The project has no external services and no build-time secrets.

### Installation

```bash
git clone https://github.com/glcskl/lendingtest.git
cd lendingtest
npm install
```

### Running

Start the development server:

```bash
npm run dev
```

Production build and local run:

```bash
npm run build
npm start
```

The production server listens on port `8000`, so open `http://localhost:8000`.

## Project structure

```
src/app/
  layout.tsx           root layout
  page.tsx             main landing page
  globals.css          global styles
  robots.ts            generated robots.txt
  sitemap.ts           generated sitemap
  [...slug]/           catch-all page routes
  verticals/security/  security services vertical
src/components/
  Site.tsx             shared site layout
  motion.tsx           shared animation primitives
  pricing-section.tsx  pricing block
src/lib/
  site-data.ts         all copy and content in one place
```

## Content

Everything a visitor reads comes from `src/lib/site-data.ts`. To change wording, add a vertical or reorder sections, edit that file rather than the components. The catch-all route picks up new slugs without new files.

## Notes

This project is personal and is not affiliated with any of the companies whose verticals it presents.