
# Copilot Instructions (Affiliate Website)

## Big picture
- Static HTML/CSS site for UK affiliate reviews; no build system, no framework, no JS app layer.
- Root pages: index.html, blog.html, category-*.html, about.html, contact.html, privacy.html, terms.html.
- Review articles live in posts/ and are linked from blog.html + category pages.
- Styling is centralized in css/style.css; header/footer are duplicated across all HTML files.

## Project-specific conventions
- Relative paths are strict:
  - Root pages use css/style.css and posts/... directly.
  - Posts always use ../ prefixes (e.g., ../css/style.css, ../index.html).
- Review articles must include the affiliate disclosure block immediately after the title and before product links.
- Affiliate links use amazon.co.uk with target="_blank" and class="btn btn-primary" with “View on Amazon UK →”.

## Patterns to copy
- Post template: posts/best-airfryers-uk.html (meta tags, disclosure, article layout).
- Card layout: index.html and blog.html (.card + .card-image + .card-body).
- Category chip bar: blog.html and category-kitchen.html.
- Grids: .grid.grid-2 and .grid.grid-3 (auto-fit defined in css/style.css).

## CSS & theming
- Update colors via :root variables in css/style.css (primary, dark, text, border, max width).
- Mobile-first breakpoints at 768px and 1200px; keep existing hover effects for .btn-primary and .card.

## Content workflows (no build)
- Add a review: duplicate posts/best-airfryers-uk.html → posts/your-slug.html, update meta/content, then add a card to blog.html and the relevant category-*.html.
- Brand changes (site name, email, GA ID) must be search/replaced across all HTML files.
- Local preview: open HTML directly or run a simple static server (python -m http.server 8000).

## Integrations & placeholders
- GA4 uses GA_MEASUREMENT_ID in every page head; replace in all HTML when activating.
- Contact form currently shows an alert (no backend integration).
