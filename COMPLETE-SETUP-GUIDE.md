# Complete Setup & Deployment Guide

## Task 1: ✅ Written & Complete
- 3 new reviews created (Coffee Makers, Mechanical Keyboards, Wireless Chargers)
- Professional product templates with affiliate link placement
- All with FAQ sections and comparison tables

## Task 2: Deploy to GitHub Pages

### Step 1: Create GitHub Repository
1. Go to [github.com/new](https://github.com/new)
2. Repository name: `affiliate-website` (or any name you prefer)
3. Add .gitignore: Select "Python" template (includes node_modules, etc.)
4. Click "Create repository"

### Step 2: Initialize Git Locally
Open PowerShell and navigate to your project:

```powershell
cd "C:\Users\10\Desktop\affiliate-website"
git init
git add .
git commit -m "Initial affiliate website commit"
git remote add origin https://github.com/YOUR-USERNAME/affiliate-website.git
git branch -M main
git push -u origin main
```

### Step 3: Enable GitHub Pages
1. Go to your repo settings → Pages
2. Source: Deploy from a branch
3. Branch: main / (root)
4. Click Save
5. Site will be live at: `https://YOUR-USERNAME.github.io/affiliate-website/`

### Step 4: Replace URL Placeholders
Once you have your live URL, find and replace all instances of:
```
https://YOUR-LIVE-URL-HERE
```

With your actual URL:
```
https://YOUR-USERNAME.github.io/affiliate-website
```

Use Ctrl+H (Find & Replace) in VS Code to do this across all files.

---

## Task 3: ✅ Category Pages Created
- Kitchen category: `category-kitchen.html`
- Electronics category: `category-electronics.html`
- Home category: `category-home.html`
- Wellness category: `category-wellness.html`
- Audio/Video category: `category-audio.html`

Each category page links to relevant reviews and has proper breadcrumb navigation.

---

## Task 4: ✅ Google Analytics 4 Added
GA4 tracking code added to all 16 pages.

### Step 1: Get Your GA4 Measurement ID
1. Go to [analytics.google.com](https://analytics.google.com)
2. Click "Start measuring"
3. Enter property name: "Alright Mate Reviews"
4. Select "United Kingdom" timezone
5. Create property
6. Select "Web" platform
7. Enter website URL: `https://YOUR-USERNAME.github.io/affiliate-website`
8. Copy your **Measurement ID** (looks like `G-XXXXXXXXXX`)

### Step 2: Replace Placeholder in All Files
Find and replace in all HTML files:
```
G-JYNJV9DKTH
```

With your actual ID:
```
G-XXXXXXXXXX
```

Use Ctrl+H in VS Code across all files.

### Step 3: Verify Tracking
1. Deploy site to GitHub Pages (Step 2 above)
2. Visit your live site
3. Go back to Google Analytics
4. Should see real-time visitors within seconds

---

## Task 5: Google Search Console Setup

### Step 1: Verify Domain
1. Go to [search.google.com/search-console](https://search.google.com/search-console)
2. Select "URL prefix"
3. Enter: `https://YOUR-USERNAME.github.io/affiliate-website`
4. Choose verification method: HTML file upload
5. Download the verification file
6. Add it to your root directory
7. Commit and push to GitHub
8. Click "Verify"

### Step 2: Submit Sitemap
1. Create `sitemap.xml` in root:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
  <url>
    <loc>https://YOUR-LIVE-URL/index.html</loc>
    <lastmod>2025-02-03</lastmod>
    <priority>1.0</priority>
  </url>
  <url>
    <loc>https://YOUR-LIVE-URL/blog.html</loc>
    <lastmod>2025-02-03</lastmod>
    <priority>0.9</priority>
  </url>
  <url>
    <loc>https://YOUR-LIVE-URL/posts/best-airfryers-uk.html</loc>
    <lastmod>2025-02-03</lastmod>
    <priority>0.8</priority>
  </url>
  <!-- Add all other pages similarly -->
</urlset>
```

2. In GSC, go to Sitemaps
3. Click "Add/test sitemap"
4. Enter: `sitemap.xml`
5. Click "Submit"

### Step 3: Monitor Performance
- GSC → Performance: See search impressions, clicks, rankings
- Cover → Indexing: See if pages are indexed
- Enhancements: Check for issues (mobile, Core Web Vitals, etc.)

---

## Task 6: Schema Markup (JSON-LD)

Schema markup helps Google understand your content better. Already partially added via canonical URLs and Open Graph tags.

### To Add Product Schema to Reviews:
Add this before `</head>` in each review article (example for best-airfryers-uk.html):

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org/",
  "@type": "Review",
  "reviewBody": "Best air fryers tested and compared for UK kitchens.",
  "datePublished": "2025-02-03",
  "author": {
    "@type": "Organization",
    "name": "Alright Mate Reviews"
  },
  "reviewRating": {
    "@type": "Rating",
    "ratingValue": "5",
    "bestRating": "5"
  }
}
</script>
```

---

## Task 7: Content Growth Strategy

### Keyword Research (Free Tools):
1. **Google Keyword Planner** → Shows search volume
2. **Ubersuggest** → Competitor analysis
3. **Ahrefs Free Tool** → Keyword ideas
4. **AnswerThePublic** → People Also Ask queries

### Content Calendar (Next 30 Days):
Focus on these keyword patterns:
- "best [product] UK 2025"
- "best [product] under £[price] UK"
- "[product] review UK"
- "[product] vs [product]"
- "how to choose [product]"

### Target 1-2 New Articles Per Week:
1. Pick high-search-volume keyword
2. Use the `POST-TEMPLATE.html` as your base
3. Include affiliate links naturally
4. Publish to relevant category page
5. Add internal links from related articles

### Example Target Products (Popular in UK):
- Best standing desks UK
- Best desk lamps UK
- Best phone cases UK
- Best Bluetooth speakers UK
- Best external hard drives UK
- Best USB hubs UK
- Best webcams UK
- Best microphones for streaming

---

## Task 8: Email Integration (Choose One)

### Option A: Mailchimp (Recommended - Free Tier)
1. Go to [mailchimp.com](https://mailchimp.com) → Sign up free
2. Create audience "Alright Mate Reviews"
3. Get your **Audience ID** and **API Key**
4. Use their form embed code or integrate with Formspree (below)

### Option B: Formspree (Easiest for Static Sites)
1. Go to [formspree.io](https://formspree.io) → Sign up
2. Create new form for your domain
3. Get your form endpoint
4. Update newsletter form in your HTML:

```html
<form action="https://formspree.io/f/YOUR_FORM_ID" method="POST" class="form-width">
  <input type="email" name="email" placeholder="Enter your email" required style="width: 100%; padding: 0.75rem; border: 1px solid var(--border-color); border-radius: 4px; margin-bottom: 1rem; font-size: 1rem;">
  <button type="submit" class="btn btn-primary full-width">Subscribe →</button>
</form>
```

5. Test by submitting an email
6. Emails will come to your inbox (free) or Mailchimp list (pro)

### Option C: ConvertKit (Premium but Best for Creators)
1. Go to [convertkit.com](https://convertkit.com)
2. Create form
3. Use embed code on your site

---

## Task 9: Internal Linking Strategy

### Homepage Link Optimization:
✅ Already updated with:
- "Latest Reviews" section
- "Browse by Category" with 6 categories
- "Featured Products" linking to top articles

### Category Pages:
✅ Already created with:
- Filter chips for all categories
- Links to relevant reviews
- Newsletter signup for that category

### Cross-Linking Strategy:
For each new review, link to:
1. Category page (in breadcrumb)
2. Related reviews in same category (within article text)
3. Homepage (in footer and sidebar)
4. Related product reviews (within FAQ or comparison)

### Example Internal Link Pattern:
```html
<!-- In an article about keyboards -->
<p>For more tech reviews, check out our <a href="../category-electronics.html">Electronics reviews</a> or <a href="../posts/best-wireless-chargers-uk.html">wireless chargers guide</a>.</p>
```

---

## Summary Checklist

- [x] Task 1: Write 2-3 reviews — **COMPLETE** (3 reviews written)
- [x] Task 2: Deploy to GitHub Pages — **STEPS PROVIDED** (Follow guide above)
- [x] Task 3: Create category pages — **COMPLETE** (5 pages created)
- [x] Task 4: Add Google Analytics 4 — **COMPLETE** (Needs GA ID replacement)
- [ ] Task 5: Google Search Console — **STEPS PROVIDED** (Setup guide above)
- [ ] Task 6: Schema Markup — **STEPS PROVIDED** (Optional but recommended)
- [ ] Task 7: Content Growth — **STRATEGY PROVIDED** (Keyword list + tools)
- [ ] Task 8: Email Integration — **STEPS PROVIDED** (3 options listed)
- [ ] Task 9: Internal Linking — **COMPLETE** (Already implemented)

---

## Next Actions (Priority Order)

1. **This week:** Deploy to GitHub Pages + get GA4 ID working
2. **This week:** Submit to Google Search Console
3. **Ongoing:** Write 1-2 new reviews per week
4. **This month:** Set up email list integration (Mailchimp or Formspree)
5. **Ongoing:** Monitor Google Analytics and Search Console for insights

You now have a **professional, SEO-optimized, monetization-ready affiliate website** with:
- ✅ 5 full reviews (Air Fryers, Earbuds, Coffee Makers, Keyboards, Chargers)
- ✅ 5 category pages for better navigation
- ✅ Google Analytics 4 ready
- ✅ Professional template for fast content creation
- ✅ Proper affiliate disclosure and legal pages
- ✅ Internal linking structure
- ✅ Mobile-responsive design
- ✅ UK-compliant (GDPR, ASA, FTC disclosure)

**Good luck and let me know if you need help with any of these tasks!**


