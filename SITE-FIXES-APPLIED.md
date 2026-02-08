# Site Configuration Notes

## Items Requiring Manual Configuration

These items are **placeholders** that need to be configured by the site owner, but are not code bugs:

### 1. Google Analytics (G-JYNJV9DKTH)
**Status:** ⚠️ Needs Configuration  
**Location:** All HTML files (search for `G-JYNJV9DKTH`)  
**Action Required:** Replace `G-JYNJV9DKTH` with your actual Google Analytics 4 measurement ID

**How to fix:**
1. Get your GA4 measurement ID from Google Analytics (format: G-XXXXXXXXXX)
2. Run a find & replace across all HTML files:
   ```bash
   find . -name "*.html" -type f -exec sed -i 's/G-JYNJV9DKTH/G-XXXXXXXXXX/g' {} +
   ```

### 2. Form Handlers
**Status:** ⚠️ Needs Backend Configuration  
**Location:** Newsletter subscription forms throughout the site  
**Current State:** Forms have `action="#"` which means they don't submit anywhere

**Action Required:**
- Option A: Use a service like Formspree, ConvertKit, or Mailchimp
- Option B: Set up a backend endpoint to handle form submissions
- Option C: Use Netlify Forms (if hosting on Netlify)

**Example with Formspree:**
```html
<form action="https://formspree.io/f/YOUR_FORM_ID" method="POST">
  <input type="email" name="email" placeholder="your.email@example.com" required>
  <button type="submit" class="btn btn-primary">Subscribe</button>
</form>
```

### 3. Social Media Links
**Status:** ✅ Already Configured  
**Location:** Footer sections  
All social media links point to existing accounts (Pinterest, X/Twitter, TikTok, YouTube, Instagram)

## Summary of Fixes Applied

### ✅ Fixed Issues:
1. **CSS Duplication** - Removed 644 duplicate lines from style.css (50% file size reduction)
2. **Incomplete Sitemap** - Added 5 missing posts to sitemap.xml
3. **Brand Inconsistency** - Fixed "Alright Mate Reviews" → "Alright Mate Reviews" in best-smart-scale-uk-2026.html
4. **best-kettles-uk.html Structure** - Completely rewrote to match proper template with:
   - Full header with navigation
   - Proper meta tags and structured data
   - Breadcrumb navigation
   - Prominent affiliate disclosure
   - Professional footer
   - Skip link for accessibility
   - Google Analytics integration (placeholder)
5. **Blog Navigation** - Added hash anchor targets for category links from index.html

### 📝 Notes:
- Footer structure is consistent across all category pages (no changes needed)
- All affiliate links use proper Amazon UK format with affiliate tag
- All post files use correct relative paths (../ prefix)
- Site is fully functional except for GA tracking and form submissions which need configuration


