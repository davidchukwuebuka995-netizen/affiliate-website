# AffiliateReviews UK - Affiliate Marketing Website

A professional, fast, and mobile-friendly affiliate marketing website built with pure HTML + CSS (no frameworks). Ready to deploy on GitHub Pages.

## 📁 Project Structure

```
affiliate-website/
├── index.html                    # Homepage with hero & featured reviews
├── blog.html                     # Blog listing page
├── about.html                    # About us & affiliate disclosure
├── contact.html                  # Contact form page
├── css/
│   └── style.css                # Complete responsive stylesheet
├── posts/
│   ├── best-airfryers-uk.html    # Sample review article
│   └── wireless-earbuds-under-50-uk.html  # Sample review article
├── assets/
│   └── images/                  # Empty folder for your images
└── README.md                      # This file
```

## ✨ Features

- ✅ **Fully Responsive** — Works perfectly on mobile, tablet, and desktop
- ✅ **Fast Loading** — Pure HTML + CSS, no JavaScript frameworks
- ✅ **SEO-Friendly** — Proper meta tags, semantic HTML, structured content
- ✅ **Accessibility** — WCAG compliant with proper heading hierarchy
- ✅ **Production-Ready** — Professional design suitable for immediate deployment
- ✅ **Easy to Customize** — Well-organized CSS with CSS variables for theming
- ✅ **Affiliate-Focused** — Built-in disclosure and affiliate link templates
- ✅ **GitHub Pages Compatible** — No build process required

## 🎨 Design Features

### Layout System
- **Responsive Grid** — Auto-fitting grid for products (1, 2, or 3 columns)
- **Sticky Header** — Navigation follows you as you scroll
- **Mobile-First** — Optimized for small screens first, scales up beautifully

### Components
- Product cards with hover effects
- Call-to-action buttons (primary & secondary)
- Newsletter signup forms
- Contact forms
- Affiliate disclosure banner
- Footer with multiple sections

### Colors & Theming
All colors are defined as CSS variables at the top of `style.css`:
- Primary: `#0066cc` (Professional blue)
- Text Dark: `#1a1a1a`
- Background: Light gray secondary sections

## 🚀 Quick Start

### 1. Download or Clone
```bash
git clone https://github.com/yourusername/affiliate-website.git
cd affiliate-website
```

Or download the ZIP file and extract it.

### 2. Open Locally
Simply open `index.html` in your browser. No build process needed!

Or use a local server:
```bash
# Using Python 3
python -m http.server 8000

# Using Python 2
python -m SimpleHTTPServer 8000

# Using Node.js (if you have http-server installed)
http-server
```

Then visit `http://localhost:8000` in your browser.

### 3. Deploy to GitHub Pages

#### Option A: Using GitHub Web Interface
1. Create a new GitHub repository called `username.github.io` (replace username with your GitHub username)
2. Upload all files to the main branch
3. Your site will be live at `https://username.github.io`

#### Option B: Using Git Command Line
```bash
git init
git add .
git commit -m "Initial commit: affiliate website"
git branch -M main
git remote add origin https://github.com/yourusername/affiliate-website.git
git push -u origin main
```

Then enable GitHub Pages in your repository settings.

## 📝 Customization Guide

### Change Site Name & Branding

**Edit in all HTML files:**
- Replace `AffiliateReviews UK` with your site name
- Update `mailto:hello@affiliatereviews.co.uk` with your email

**Edit in CSS (`style.css`):**
- Update color variables at the top:
  ```css
  :root {
    --primary-color: #YOUR-COLOR;
    --primary-dark: #YOUR-DARK-COLOR;
  }
  ```

### Add Your Own Product Reviews

Create a new file in `posts/` folder (copy one of the sample posts):

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Your Product Review Title</title>
  <meta name="description" content="Your description">
  <link rel="stylesheet" href="../css/style.css">
</head>
<body>
  <!-- Copy header & footer from sample posts -->
  <!-- Write your content -->
</body>
</html>
```

Then link to it from `blog.html` in the grid section.

### Add Images

1. Add images to `assets/images/` folder
2. Reference them in your HTML:
```html
<img src="../assets/images/your-image.jpg" alt="Description">
```

**Optimize images:**
- Keep images under 100KB when possible
- Use JPG for photos, PNG for graphics
- Tools: TinyPNG, ImageOptim, or Squoosh

### Update Navigation

Edit the navigation in `header` section of each HTML file:

```html
<nav>
  <a href="index.html">Home</a>
  <a href="blog.html">Blog</a>
  <a href="your-page.html">Your Page</a>
</nav>
```

## 🔗 Adding Affiliate Links

### Format for affiliate links:

```html
<a href="https://www.amazon.co.uk/dp/PRODUCT-ID" class="btn btn-primary">
  View on Amazon UK
</a>
```

Always include affiliate disclosure:

```html
<div class="disclosure">
  <strong>⚠️ Affiliate Disclosure:</strong> We earn commissions from products recommended. This doesn't affect your price.
</div>
```

## 📱 Mobile Optimization

The site is fully mobile-responsive:
- **Mobile**: Single column layout, stacked elements
- **Tablet**: 2-column grid layouts
- **Desktop**: Full 3-column layouts

Test on mobile:
```bash
# Use Chrome DevTools (F12) → Toggle Device Toolbar
# Or test on real phone by using local IP address
# Find your IP: ipconfig (Windows) or ifconfig (Mac/Linux)
# Visit: http://YOUR-IP:8000
```

## 🔍 SEO Tips

1. **Meta Descriptions** — Edit the `<meta name="description">` tag in each page
2. **Headings** — Use H1 once per page, H2 for sections, H3 for subsections
3. **Keywords** — Include relevant keywords naturally in content
4. **Images** — Always add descriptive `alt` text
5. **Links** — Internal linking between related articles helps SEO
6. **URL Structure** — Use descriptive filenames like `best-airfryers-uk.html`

## 📊 Affiliate Networks to Join

- Amazon Associates (Amazon UK)
- John Lewis Partnership
- Currys Affiliate Program
- Argos
- Scan Affiliate
- Overclockers UK

## 💡 Content Tips

### For Effective Reviews:
1. Test products yourself (or thoroughly research them)
2. Include pros and cons
3. Compare with alternatives
4. Provide genuine recommendations (not just commission-chasing)
5. Update reviews regularly as products change
6. Include affiliate links naturally in the text

### For Growth:
- Post consistently (1-2 articles per week is good)
- Share on social media
- Engage with readers (respond to comments/emails)
- Focus on trending products
- Build an email list early

## 🛡️ Legal Compliance

✅ **This template includes:**
- Affiliate disclosure banner on homepage
- Full affiliate disclosure page (`about.html#affiliate`)
- Privacy policy section (ready for you to complete)
- Terms section (ready for you to complete)

**You must:**
1. Review and update affiliate disclosure to match your actual partnerships
2. Add your Privacy Policy (based on your data handling)
3. Add Terms of Service (covering your site)
4. Display cookies notice if using analytics (recommended: Google Analytics)

## 🚫 Common Mistakes to Avoid

1. ❌ Don't hide affiliate links — Always disclose them clearly
2. ❌ Don't recommend products you haven't researched — It damages credibility
3. ❌ Don't use auto-generated content — Quality beats quantity
4. ❌ Don't ignore mobile users — Test on phones before publishing
5. ❌ Don't forget images — They improve engagement
6. ❌ Don't ignore SEO basics — Proper titles and descriptions matter

## 📈 Next Steps

After deployment:

1. **Add Google Analytics**
   ```html
   <!-- Add to <head> of every page -->
   <script async src="https://www.googletagmanager.com/gtag/js?id=GA_ID"></script>
   <script>
     window.dataLayer = window.dataLayer || [];
     function gtag(){dataLayer.push(arguments);}
     gtag('js', new Date());
     gtag('config', 'GA_ID');
   </script>
   ```

2. **Submit to Google Search Console** — Helps your site appear in Google results

3. **Create Social Media Accounts** — Promote your reviews on Twitter, Instagram, etc.

4. **Start Writing** — Publish 5-10 quality reviews before trying to monetize

5. **Build Email List** — This is your most valuable asset for long-term growth

## 🆘 Troubleshooting

**Links not working?**
- Check file paths are correct (use `../` to go up directories)
- Make sure filenames match exactly (case-sensitive on some servers)

**Page looks broken on mobile?**
- Open DevTools (F12) and toggle device toolbar
- Check that CSS file is loading (should say 200 in Network tab)

**Not appearing in Google?**
- Wait 2-4 weeks for indexing
- Submit sitemap to Google Search Console
- Ensure pages have good content (200+ words minimum)

## 📞 Support

- Need help? Check the comments in `style.css` for class explanations
- Review the HTML comments for content structure examples
- Compare your code to the sample blog posts for formatting

## 📄 License

Free to use and modify for your own projects. No attribution required, but appreciated!

---

**Ready to launch?** Make your first commit and deploy to GitHub Pages. Your affiliate website is ready to go! 🚀
