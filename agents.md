# Project Guide

## Architecture

This is a dependency-free static website. Each customer-facing route is a standalone HTML document and shares a single stylesheet and JavaScript file.

## Key Directories

- `css/styles.css` contains the complete visual system, layout, components, animations, and responsive breakpoints.
- `js/site.js` contains mobile navigation, estimator behavior, and quantity-aware WhatsApp order links.
- Root-level HTML files contain individual page content.
- `images/` contains local product, factory and delivery photography.
- `sitemap.xml` and `robots.txt` support Google indexing; update both when adding pages.
- `.netlify/` contains platform-generated metadata and completion summaries.

## Conventions

- Reuse existing component classes before adding page-specific CSS.
- Keep page navigation and footer links consistent across all documents.
- Use semantic elements, explicit form labels, and accessible button text.
- Preserve the industrial palette and typography variables defined in `:root`.
- Keep JavaScript progressive: core content and navigation remain available without it.

## Netlify Forms

The `project-enquiry` form in `contact.html` is detected directly from static HTML. Its `name`, hidden `form-name`, honeypot field, and submitted field names must remain aligned. Successful submissions redirect to `/thank-you`.

## Non-obvious Decisions

- Product prices are explicitly described as indicative guides rather than guaranteed transaction prices.
- The estimator is a preliminary budgeting aid and displays a disclaimer because final material quantities require project-specific engineering and mix information.
- Google Fonts are loaded remotely; all photography is self-hosted in `images/`.
- There is no online checkout: every purchase CTA opens WhatsApp (`wa.me/254755340004`, prefilled message) or `tel:+254755340004`. Keep the phone number identical across all pages and structured data.
- Canonical URLs, Open Graph tags and JSON-LD assume `https://simbacement-ltd.netlify.app`.
