# QUICK START GUIDE

## 30-Second Setup

1. **Open in Browser**
   ```
   Double-click index.html
   ```
   Your site is now live locally! ✅

2. **Test Navigation**
   - Click Home, Blog, About, Contact
   - All links should work
   - Click product links (they go to Amazon UK)

3. **Check Mobile View**
   - Press **F12** (Windows) or **Cmd+Option+I** (Mac)
   - Click device icon (top-left of DevTools)
   - Try mobile, tablet, desktop sizes
   - Everything should look great

## First Changes (Next 5 Minutes)

### Change Your Site Name
1. Open `index.html` in a text editor (VS Code, Notepad, etc.)
2. Find: `AffiliateReviews UK`
3. Replace with: Your site name
4. Do the same in: `blog.html`, `about.html`, `contact.html`, `posts/` files

### Change Brand Colors
1. Open `css/style.css`
2. Find the top section with `:root { --primary-color:`
3. Change `#0066cc` to your preferred color
4. Change `#0052a3` to a darker version
5. Refresh browser—whole site updates! 🎨

### Change Contact Email
1. Find: `hello@affiliatereviews.co.uk`
2. Replace with your email address
3. Update in: `contact.html` + `footer` of other pages

## File Structure Explained

```
📦 affiliate-website/
├── 📄 index.html          ← Homepage (start here!)
├── 📄 blog.html           ← Blog listing
├── 📄 about.html          ← About & legal disclosure
├── 📄 contact.html        ← Contact form
│
├── 📁 posts/              ← Individual blog articles
│   ├── best-airfryers-uk.html        (sample #1)
│   └── wireless-earbuds-under-50-uk.html  (sample #2)
│
├── 📁 css/
│   └── style.css          ← All the styling (change colors here!)
│
├── 📁 assets/images/      ← Add your product images here
│
├── 📄 README.md           ← Full documentation
├── 📄 DEPLOYMENT.md       ← How to launch online
└── 📁 .github/
    └── copilot-instructions.md  ← AI agent guide
```

## Common Tasks

### 📝 Add Your First Review

1. Copy `posts/best-airfryers-uk.html`
2. Rename to `posts/your-product-name.html`
3. Edit:
   - `<title>` - Change to your product
   - `<h1>` - Your review title
   - Replace content in `.article` section
   - Keep `<div class="disclosure">` (legal requirement!)

4. Link it from `blog.html`:
   ```html
   <article class="card">
     <div class="card-body">
       <h3 class="card-title">Your Product</h3>
       <p>Description...</p>
       <a href="posts/your-product.html" class="btn btn-primary">Read →</a>
     </div>
   </article>
   ```

5. Refresh browser to see it live

### 🖼️ Add Product Images

1. Download/prepare your image (JPG or PNG)
2. Save to `assets/images/my-image.jpg`
3. In HTML, reference it:
   ```html
   <img src="../assets/images/my-image.jpg" alt="Product description">
   ```
4. To replace gradient in card:
   ```html
   <div class="card-image">
     <img src="../assets/images/product.jpg" alt="Product">
   </div>
   ```

### 🎨 Customize Colors

Edit `css/style.css` top section:

```css
:root {
  --primary-color: #0066cc;        ← Main color (blue)
  --primary-dark: #0052a3;         ← Darker version
  --secondary-color: #f0f4f8;      ← Light gray
  --text-dark: #1a1a1a;            ← Dark text
  --text-light: #666;              ← Gray text
}
```

Try color combinations:
- **Blue site:** `#0066cc` / `#0052a3` ✅ (current)
- **Green site:** `#10b981` / `#059669`
- **Purple site:** `#8b5cf6` / `#7c3aed`
- **Red site:** `#ef4444` / `#dc2626`

### 🚀 Deploy Online (GitHub Pages)

1. Create free account at [github.com](https://github.com)
2. Create new repository called `yourusername.github.io`
3. Upload all your files
4. Your site is live at `yourusername.github.io` (usually 1-2 min)

**See DEPLOYMENT.md for detailed steps**

### 📧 Add Email Signup

Currently forms just show "Thank you" message. To capture emails:

1. Sign up at [mailchimp.com](https://mailchimp.com) (free!)
2. Create audience/form
3. Get the form code
4. Replace the `<form>` in `index.html` with Mailchimp form

## Content Tips

### What to Review
- Trending products on Amazon
- Products in your niche
- Things you genuinely use
- Products with good commission rates

### How Long Should Reviews Be?
- Minimum: 800 words
- Ideal: 1,500-2,000 words
- Structure: Problem → Solutions → Comparison → Winner

### When to Update
- New product versions come out
- Prices change
- Reviews get outdated (set calendar reminder)
- Better alternatives emerge

## Testing Checklist

Before going live online:
- [ ] All links work (click every link)
- [ ] Mobile looks good (F12 → Device mode)
- [ ] Images load correctly
- [ ] Forms work (contact form shows thank you)
- [ ] No spelling mistakes
- [ ] Affiliate disclosure is visible
- [ ] Navigation is clear
- [ ] Load time is fast (should be <1 second)

## Common Questions

**Q: Can I use this on multiple sites?**
A: Yes! Each copy is independent.

**Q: Do I need a domain name?**
A: No, `username.github.io` is free. But a domain ($10-15/year) looks more professional.

**Q: Will this show ads automatically?**
A: No. You only earn money through affiliate links you add manually.

**Q: Can I sell products on this site?**
A: This template is affiliate-focused. For selling, you'd need Shopify or similar.

**Q: Is it SEO optimized?**
A: Yes! The structure is SEO-friendly. Results take 3-6 months.

**Q: Can I use WordPress instead?**
A: Sure, but this HTML version is simpler, faster, and free to host.

## Next Steps (After Launch)

1. **Write 5-10 reviews** before expecting traffic
2. **Share on social media** (Twitter, Reddit, relevant communities)
3. **Build email list** (start from day 1)
4. **Be consistent** (1-2 articles per week)
5. **Monitor Google Search Console** (see what people search)
6. **Update reviews** as products change

## Support Resources

- **CSS Help:** Check comments in `style.css`
- **HTML Structure:** Compare with sample blog posts
- **Deployment:** See `DEPLOYMENT.md`
- **Full Guide:** See `README.md`

---

## You're All Set! 🎉

Your affiliate website is ready. Now go write great reviews and build an audience!

**Remember:** Most successful affiliate sites took 6-12 months to make real money. Focus on quality content and genuine recommendations.

**Good luck!** 🚀
