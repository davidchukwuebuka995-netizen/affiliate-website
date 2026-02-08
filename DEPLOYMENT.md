# DEPLOYMENT GUIDE

## Quick GitHub Pages Deployment

### 1. Create GitHub Repository

Go to [github.com/new](https://github.com/new) and create a new repository named:
- `affiliate-website` (or any name you want)

**OR** for immediate deployment at `username.github.io`:
- Create repo named exactly: `yourusername.github.io`

### 2. Push Your Files

```bash
# Navigate to your project folder
cd affiliate-website

# Initialize git
git init

# Add all files
git add .

# Commit
git commit -m "Initial commit: professional affiliate website"

# Add remote (replace with your repo URL from GitHub)
git remote add origin https://github.com/yourusername/affiliate-website.git

# Rename branch to main
git branch -M main

# Push to GitHub
git push -u origin main
```

### 3. Enable GitHub Pages

In your repository on GitHub:
1. Go to **Settings**
2. Scroll to **Pages** section
3. Under "Build and deployment"
4. Select **Source**: `Deploy from a branch`
5. Select **Branch**: `main`
6. Click **Save**

Your site will be live in 1-2 minutes at:
- `https://yourusername.github.io/affiliate-website` (if repo is not named `.github.io`)
- `https://yourusername.github.io` (if repo is named `yourusername.github.io`)

## Alternative: Deploy to Netlify (Recommended for Beginners)

Netlify has a simpler drag-and-drop interface:

1. Visit [netlify.com](https://netlify.com)
2. Click **Add new site** → **Deploy manually**
3. Drag and drop your entire `affiliate-website` folder
4. Your site is live instantly!

**Advantage:** Gets a free URL like `yoursite.netlify.app` (no GitHub account needed)

## Custom Domain

Once deployed:

### GitHub Pages
1. Buy a domain (GoDaddy, Namecheap, etc.)
2. In repo **Settings** → **Pages**
3. Enter custom domain under "Custom domain"
4. Point your domain's DNS to GitHub's nameservers (instructions provided)

### Netlify
1. Buy domain or transfer existing
2. In Netlify dashboard → **Site settings** → **Domain management**
3. Add custom domain
4. Netlify handles DNS automatically

## Testing Before Deployment

### Locally
```bash
# Using Python 3
python -m http.server 8000

# Then visit: http://localhost:8000
```

### On Network
Get your local IP address and test on phone:
```bash
# Windows
ipconfig

# Mac/Linux
ifconfig
```
Then visit `http://YOUR-IP:8000` from your phone.

## Pre-Launch Checklist

- [ ] All affiliate links point to correct products
- [ ] Email in contact form is correct
- [ ] Social media links in footer are updated
- [ ] Site name is updated (not "Alright Mate Reviews")
- [ ] Mobile responsiveness tested
- [ ] No broken links (test all navigation)
- [ ] Meta descriptions are compelling
- [ ] Affiliate disclosure is present on every review
- [ ] Contact form works (shows confirmation)

## After Deployment

1. **Add to Google Search Console**
   - Visit [search.google.com/u/1/search-console](https://search.google.com/u/1/search-console)
   - Add property → Enter your domain
   - Verify ownership

2. **Submit Sitemap**
   - Add this to your `<head>` in every page (optional but recommended):
   ```html
   <link rel="sitemap" type="application/xml" href="/sitemap.xml">
   ```

3. **Monitor Performance**
   - Google Search Console shows search appearance
   - Add Google Analytics to track visitors

## Troubleshooting

### Site shows 404
- Make sure `index.html` exists in root folder
- GitHub Pages defaults to `index.html`

### Pages load but links are broken
- Check relative paths use `../` correctly
- From `/posts/article.html` → `../index.html` (go up one level)

### Changes don't appear after push
- GitHub Pages can take 1-2 minutes to rebuild
- Hard refresh browser (Ctrl+Shift+R on Windows, Cmd+Shift+R on Mac)
- Check deployment status in repo Settings → Pages

### Custom domain not resolving
- DNS changes can take 24-48 hours to propagate
- Check DNS records are pointing to GitHub's IPs

## Next Level: Adding Backend Services

For production features, integrate these free/cheap services:

### Contact Form Backend
```html
<form action="https://formspree.io/f/YOUR_ID" method="POST">
  <input type="email" name="email" required>
  <!-- etc -->
</form>
```
Visit [formspree.io](https://formspree.io) → get ID → integrate

### Email Newsletter
- **Mailchimp:** Free for up to 500 contacts
- **Substack:** Free + built-in audience growth
- **ConvertKit:** Paid but feature-rich

### Analytics
Add to `<head>` of every page:
```html
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'G-XXXXXXXXXX');
</script>
```
Get ID from [analytics.google.com](https://analytics.google.com)

## Ongoing Maintenance

- **Update reviews** monthly with new products
- **Check broken links** weekly
- **Monitor analytics** to see popular content
- **Respond to emails** within 2 days
- **Back up your site** (git repo is your backup!)

## Support

If deployment fails:
1. Check GitHub status: [githubstatus.com](https://githubstatus.com)
2. Verify all files are UTF-8 encoded (not ANSI)
3. Check file permissions (should be public for Pages)
4. Try redeploying: `git push origin main`

---

**Your site is now live! 🚀**

Start creating content and promoting on social media. Most affiliate sites take 3-6 months to see meaningful traffic, so be patient and consistent.

