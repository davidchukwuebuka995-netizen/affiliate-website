
# Affiliate Website Copilot Instructions

This is a pure HTML5 + CSS3 affiliate marketing website for UK product reviews—zero frameworks, zero build process.

## Architecture Overview

**Tech Stack:** Static HTML5 + CSS3 (Mobile-first responsive design)
- **Pages:** `index.html` (home), `blog.html` (all reviews), `category-*.html` (filtered views), `about.html`, `contact.html`, `privacy.html`, `terms.html`
- **Content:** `posts/` directory (individual review articles with relative paths back to root)
- **Styling:** Single `css/style.css` (all responsive breakpoints: mobile-first base → 768px+ → 1200px+)
- **Assets:** `assets/images/` placeholder directory (uses CSS gradients for demo card images)

**Deployment:** Drops directly on GitHub Pages—no build step, no bundling. All pages reference `GA_MEASUREMENT_ID` placeholder in GA4 script.

## Critical Conventions & Patterns

### 1. Relative Paths (Non-Negotiable)
**From root pages** (e.g., `index.html`, `blog.html`):
```html
<link rel="stylesheet" href="css/style.css">
<a href="about.html">About</a>
<a href="posts/best-airfryers-uk.html">Review</a>
```

**From `posts/` subdirectory** (e.g., `posts/best-airfryers-uk.html`):
```html
<link rel="stylesheet" href="../css/style.css">
<a href="../index.html">Home</a>
<a href="../blog.html">Reviews</a>
<a href="../about.html#affiliate">Affiliate Disclosure</a>
```

**Category pages are at root level** (`category-kitchen.html`), so they use root-relative paths like `index.html`.

**Golden rule:** Each `../` moves up one directory. Blog posts live in `posts/`, so they always start with `../`.

### 2. Header & Footer Duplication Pattern
Every HTML file contains:
- **Identical `<header>` block** with navigation (differs only in `.active` class on current page)
- **Identical `<footer>` block** with social links, newsletter form, and legal links

When updating branding (logo, nav links, footer email), search/replace across **all `.html` files**. Example:
```bash
# Replace brand name in all files
"AffiliateReviews UK" → "Your Brand Name"

# Update footer email
mailto:hello@affiliatereviews.co.uk → mailto:your-email@domain.com
```

### 3. Affiliate Link Pattern & Legal Compliance
Every product recommendation **must** follow this exact structure:

```html
<!-- At top of article, right after title -->
<section class="section">
  <div class="container">
    <div class="disclosure">
      <strong>⚠️ Affiliate Disclosure:</strong> We earn commissions from products recommended in this review. This doesn't affect your price. <a href="../about.html#affiliate">Full disclosure</a>.
    </div>
  </div>
</section>

<!-- In article content, for each product -->
<a href="https://www.amazon.co.uk/dp/PRODUCT-ID" target="_blank" class="btn btn-primary">
  View on Amazon UK
</a>
```

**Non-negotiable rules:**
- Every review article **starts with `.disclosure` banner**
- Always `target="_blank"` for external affiliate links
- Always `class="btn btn-primary"` for consistency
- Use UK Amazon links (`amazon.co.uk`)
- Link text includes arrow: "View on Amazon UK →" (arrow in text or button class)
- `about.html#affiliate` section has legal compliance language (FTC/ASA required for UK)

### 4. CSS Architecture: Root Variables + Mobile-First
**Color theming** — Edit `:root` at top of `style.css` (lines 1-12):
```css
:root {
  --primary-color: #0066cc;        /* Main brand blue */
  --primary-dark: #0052a3;          /* Hover state */
  --secondary-color: #f0f4f8;       /* Light backgrounds */
  --text-dark: #1a1a1a;             /* Body text */
  --text-light: #666;               /* Secondary text */
  --border-color: #e0e0e0;
  --success-color: #10b981;
  --max-width: 1200px;
}
```

**Responsive breakpoints** — Mobile-first architecture:
- **Base styles** (mobile): `16px` font, `gap: 2rem`, `padding: 1rem`
- **`@media (min-width: 768px)`**: Tablet layout, 2-column grids
- **`@media (min-width: 1200px)`**: Desktop, 3-column grids, wider containers

**Grid system** — Simple, no BEM naming:
```html
<div class="grid grid-2">  <!-- Auto-responsive 2 columns on desktop, 1 on mobile -->
  <article class="card">...</article>
</div>

<div class="grid grid-3">  <!-- Auto-responsive 3 columns on desktop, 1 on mobile -->
  <article class="card">...</article>
</div>
```

### 5. Card Component (Reusable Pattern)
Used everywhere: featured products (homepage), blog listings, categories, team profiles.

```html
<div class="card">
  <!-- Card image: use gradient or replace with <img> -->
  <div class="card-image" style="background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);"></div>
  
  <div class="card-body">
    <div class="text-muted small-text">Category • Read time</div>
    <h3 class="card-title">Product Name</h3>
    <p class="card-text">Brief description 1-2 sentences max.</p>
    
    <!-- Optional rating -->
    <div style="display: flex; justify-content: space-between; align-items: center;">
      <span class="product-rating">★★★★★</span>
      <a href="posts/article.html" class="btn btn-primary">Read Article →</a>
    </div>
  </div>
</div>
```

**Card hover behavior:** `transform: translateY(-2px)` + shadow lift (built-in via CSS)

### 6. Blog Post Template Structure
All review articles follow `posts/best-airfryers-uk.html` pattern:
1. HTML boilerplate with unique `<title>`, `<meta name="description">`, canonical URL
2. Header with `../` relative paths
3. Breadcrumb section (optional but recommended)
4. `.page-hero` section with title + rating
5. Affiliate disclosure banner (critical)
6. `.article` wrapper with H2/H3 hierarchy
7. Product recommendations with affiliate links
8. Newsletter signup CTA
9. Footer (identical to all pages)

Example meta tags (update per article):
```html
<title>Best Air Fryers UK 2025 - Reviews & Comparisons</title>
<meta name="description" content="We tested 15 air fryers to find the best models for UK kitchens. Compare features, prices, and performance.">
<link rel="canonical" href="https://YOUR-LIVE-URL-HERE/posts/best-airfryers-uk.html">
```

### 7. Category Pages Structure
Files like `category-kitchen.html` are **root-level** pages that filter blog content. They:
- Have category-specific header (`<h1>Kitchen Appliances & Gadgets</h1>`)
- Include same `.category-bar` chip navigation as `blog.html` (with one `.active` class)
- Display relevant blog post cards in same grid layout
- Use root-relative paths (no `../`)

### 8. Legal Pages Checklist
- **`about.html`** → Contains full affiliate disclosure, review process, brand mission (non-negotiable for ASA/FTC)
- **`privacy.html`** → Data collection, cookies, GDPR basics
- **`terms.html`** → Liability disclaimers, usage rights
- **Footer links** → All pages link to these three + contact form

These pages are **not optional** for UK affiliate marketing (ASA compliance required).

## Essential Developer Workflows

### Adding a New Blog Post
1. **Copy template:** Duplicate `posts/best-airfryers-uk.html` as `posts/your-slug.html`
2. **Update SEO metadata** (lines 1-16):
   ```html
   <title>Your Topic UK [Year] - Reviews & Comparisons</title>
   <meta name="description" content="We tested X products...">
   <meta property="og:url" content="https://YOUR-LIVE-URL-HERE/posts/your-slug.html">
   <link rel="canonical" href="https://YOUR-LIVE-URL-HERE/posts/your-slug.html">
   ```
3. **Update navigation links** (lines 38-43) — All use `../` prefix:
   ```html
   <a href="../index.html" class="logo">AffiliateReviews UK</a>
   <a href="../blog.html">Reviews</a>
   ```
4. **Add article header** in `.page-hero` (update title, rating, publish date)
5. **Add affiliate disclosure** (mandatory):
   ```html
   <div class="disclosure">
     <strong>⚠️ Affiliate Disclosure:</strong> We earn commissions...
     <a href="../about.html#affiliate">Full disclosure</a>.
   </div>
   ```
6. **Write article content** in `.article` wrapper with proper heading hierarchy (H2 for sections, H3 for subsections)
7. **Include affiliate links** for each product:
   ```html
   <a href="https://www.amazon.co.uk/dp/PRODUCT-ID" target="_blank" class="btn btn-primary">
     View on Amazon UK
   </a>
   ```
8. **Link from blog.html** — Add card to grid (line ~60):
   ```html
   <article class="card">
     <div class="card-image" style="background: linear-gradient(...);">
     <div class="card-body">
       <div class="text-muted small-text">Category • 8 min read</div>
       <h3 class="card-title">Your Product Review</h3>
       <p class="card-text">Brief teaser...</p>
       <a href="posts/your-slug.html" class="btn btn-primary">Read Article →</a>
     </div>
   </article>
   ```
9. **Update category page** (e.g., `category-kitchen.html`) with same card
10. **Test relative paths:** Open in browser, click all links. Paths must resolve correctly.

### Updating Brand Identity (Affects All Files)
Use find-and-replace across **entire workspace**:
1. **Brand name:** "AffiliateReviews UK" → Your brand (appears in all headers/footers)
2. **Primary color:** Update `:root` in `css/style.css` line 7: `--primary-color: #NEW-HEX`
3. **Email address:** `hello@affiliatereviews.co.uk` → Your email (footer, contact form)
4. **Live URL placeholder:** `https://YOUR-LIVE-URL-HERE/` → Your actual domain (meta tags, canonicals)
5. **Google Analytics ID:** `GA_MEASUREMENT_ID` → Your actual ID (appears in `<head>` of every page)
6. **Social links:** Update href in footer (LinkedIn, Twitter, etc.)

**Pro tip:** Search/replace in root folder, then verify by opening each page type (root, post, category) in browser.

### Adding a New Category Page
1. Copy `category-kitchen.html` as `category-your-category.html`
2. Update the category name in `<h1>` and page meta tags
3. Update `.category-bar` to reflect new category (keep all chips)
4. Add product cards for this category from blog posts
5. Link from `blog.html` in category filter chips
6. Test that all links work (use root-relative paths)

### Testing & Validation
- **Mobile responsive:** Open DevTools (F12), toggle device toolbar, test at 480px, 768px, 1200px
- **Relative paths:** Click every navigation link from root and post pages—verify they all resolve
- **Affiliate disclosure:** Search for "Disclosure" on every review article—must appear before product links
- **SEO basics:** Verify each page has unique `<title>`, `<meta name="description">`, only one `<h1>`
- **No JavaScript errors:** Open console (DevTools) on every page—should be clean (GA script warnings are OK)

### Local Testing (No Build Step)
1. Open any `.html` file directly in browser (File → Open)
2. OR run a local server: `python -m http.server 8000` (Python 3) or `python -m SimpleHTTPServer` (Python 2)
3. Visit `http://localhost:8000` and click through pages
4. Test on mobile: Use DevTools device emulation

### Deploying to GitHub Pages
```bash
# Initialize git (one time)
git init
git add .
git commit -m "Initial affiliate website"
git remote add origin https://github.com/USERNAME/repo-name.git
git push -u origin main

# In GitHub repo settings:
# 1. Go to Settings → Pages
# 2. Set source to "main branch"
# 3. Site live at https://USERNAME.github.io/repo-name (or custom domain)
```

**Important:** Before pushing, search/replace `GA_MEASUREMENT_ID` with your actual Google Analytics ID.

## Key Technical Patterns & How They Work

### Grid Responsiveness (CSS auto-fit)
The grid system uses `auto-fit` with `minmax()` to handle responsive layouts without media queries:
```css
.grid-2 {
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
}

.grid-3 {
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
}
```
- **On mobile** (< 300px width): Stacks to 1 column
- **On tablet** (600-900px): 2 columns naturally
- **On desktop** (1200px+): 3 columns naturally
- No media queries needed—CSS handles it

### Button Hover Effects
All buttons have built-in elevation and color transitions (lines 157-170 of `style.css`):
```css
.btn-primary:hover {
  background: var(--primary-dark);
  transform: translateY(-1px);          /* Lifts button 1px on hover */
  box-shadow: 0 4px 12px rgba(...);     /* Adds shadow */
}
```
Keep this pattern consistent—don't add custom button styles without this hover behavior.

### Card Hover & Shadow (3D Lift Effect)
Cards also lift on hover (lines 206-211):
```css
.card:hover {
  box-shadow: 0 8px 24px rgba(0, 0, 0, 0.1);  /* Stronger shadow */
  transform: translateY(-2px);                  /* Lifts 2px */
}
```
This creates a "floating" effect—never modify card hover without this pattern.

### Affiliate Link Styling
Affiliate links always use `.btn btn-primary` class—there is **no `.btn-tertiary`** or special "affiliate link" styling. This ensures consistency across all CTAs.

### Hero Section Gradient
Hero sections use CSS gradients (lines 286-301):
```css
.hero {
  background: linear-gradient(135deg, var(--primary-color) 0%, var(--primary-dark) 100%);
}
```
Card images use inline gradients for demo purposes:
```html
<div class="card-image" style="background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);"></div>
```
When images are added, replace inline styles with `<img>` tags and remove gradient.

### Sticky Header Positioning
Header is sticky (stays at top on scroll) via `position: sticky; top: 0; z-index: 100;` (lines 87-92). This works automatically—don't change unless you need different header behavior.

### Disclosure Box Styling
Disclosure boxes have distinct styling (`.disclosure` class) with warning icon and light background. Always place these **immediately after article title** and before product links (see `best-airfryers-uk.html` lines 61-68 for example).

## Integration Points & External Services (Not Yet Implemented)

### Contact Form (Currently Alert-Only)
The contact form in `contact.html` shows a JavaScript alert on submit. For production, integrate with:
- **Formspree** — Free tier (100 submissions/month), easy setup: `<form action="https://formspree.io/f/YOUR-ID" method="POST">`
- **EmailJS** — Client-side service, no backend required
- **Netlify Forms** — If deploying to Netlify instead of GitHub Pages (automatic submission handling)

### Newsletter Signup (Currently No Backend)
Footer newsletter form exists but doesn't capture emails. Add service:
- **Mailchimp** — Free tier, embed signup form script
- **Substack** — Ideal for affiliate sites, embeds form directly
- **ConvertKit** — Creator-focused, good for building email lists

### Google Analytics 4 Setup
Current code has `GA_MEASUREMENT_ID` placeholder in every `<head>` tag. To activate:
1. Create Google Analytics 4 property at [analytics.google.com](https://analytics.google.com)
2. Get Measurement ID (format: `G-XXXXXXXXXX`)
3. Search/replace `GA_MEASUREMENT_ID` with your actual ID in all `.html` files
4. Code already includes gtag.js script—no additional setup needed

### Missing Patterns to Add
- **Image optimization** — Currently using gradient placeholders. When adding real images:
  - Store in `assets/images/`
  - Use relative paths: `src="../assets/images/product.jpg"`
  - Add `alt` text for accessibility
  - Consider lazy loading for hero images
  
- **Social sharing meta tags** — All pages have Open Graph tags (`og:title`, `og:description`, `og:url`). Ensure these match actual content when publishing.

## Conventions Different from Typical Projects

1. **No JavaScript** — Stateless site. Form submissions show alert only.
2. **No CSS preprocessing** — Pure CSS with `:root` variables (not SCSS/LESS)
3. **No components library** — Reuse via copy-paste + modify (not imports)
4. **No bundling** — Files serve as-is, no build step
5. **Inline styles only in grids** — Most styling in stylesheet; only `style="background: gradient"` used for gradient backgrounds in card images
6. **No backend dependencies** — Everything works offline (except GA tracking and external links)

## Quality Checklist Before Publishing Content

- [ ] **Relative paths:** All navigation links work from root and post pages
- [ ] **Affiliate disclosure:** Present at top of every review article
- [ ] **Unique meta tags:** Each page has unique `<title>`, `<meta name="description">`
- [ ] **Only one H1:** No multiple H1s on single page (SEO requirement)
- [ ] **Heading hierarchy:** H1 → H2 → H3, no skipping levels
- [ ] **Mobile test:** DevTools at 480px, 768px, 1200px—all content readable
- [ ] **Link validation:** Every internal link resolves correctly
- [ ] **Affiliate links:** All external product links use `target="_blank"`
- [ ] **Legal pages:** Links to `about.html#affiliate`, `privacy.html`, `terms.html` exist in footer

---

**TL;DR:** Pure HTML + CSS affiliate site. Copy blog post template for new content. Update CSS root variables for branding. Deploy to GitHub Pages directly. All relative paths pre-configured. No build step—files serve as-is.
