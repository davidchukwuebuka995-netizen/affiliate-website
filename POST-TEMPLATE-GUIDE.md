# Post Template Guide

## Using the Professional Post Template

Located at: `posts/POST-TEMPLATE.html`

### Step-by-Step Instructions

1. **Copy the template file**
   ```
   Copy posts/POST-TEMPLATE.html → posts/your-product-name-uk.html
   ```

2. **Fill in the placeholders** (search & replace in your editor):
   - `[PRODUCT NAME]` → Your product category (e.g., "Best Blenders")
   - `[filename]` → Your new filename (for canonical URL)
   - `[MONTH YEAR]` → Publication date
   - `[X] min read` → Estimated reading time (multiply word count by 200 for rough estimate)
   - `[ASIN]` → Amazon product ID from Amazon URL
   - `[PRICE]` → Current price in £

3. **Key sections to customize:**

   **Intro (First paragraph)**
   - Hook: Start with a strong statement about why this product matters
   - Promise: Tell reader what they'll learn
   - Authority: Mention how many products tested (builds trust)

   **Top 3 Picks**
   - Always include a "What We Like" + "What to Consider" section
   - Each gets its own Amazon affiliate link
   - Use ★★★★★ ratings (5 stars for best pick, 4 for alternatives)

   **Comparison Table**
   - Google loves structured comparison data
   - Shows you've done real testing
   - Improves SEO for "vs" searches

   **How to Choose Section**
   - Answer "Which one should I buy?" for different situations
   - Drives more qualified traffic
   - Helps users self-select which product is right

   **FAQ Section**
   - Most important SEO section - targets long-tail searches
   - Users ask these Qs on Google
   - Answer honestly (builds trust, improves affiliate conversions)

### Affiliate Link Best Practices

✅ **DO:**
- Use real product ASIN codes from Amazon UK
- Include 2-4 affiliate links per article (not every mention)
- Link from comparison tables and "View on Amazon" CTAs
- Use descriptive text: "View on Amazon UK →"

❌ **DON'T:**
- Link every mention of a product (looks spammy)
- Use short/ugly affiliate URLs
- Hide affiliate links in generic "click here" text
- Forget the disclosure banner at top

### SEO Checklist

- [ ] **Title tag** (H1) — Includes main keyword + "UK 2025"
- [ ] **Meta description** — 150-160 chars, includes keyword, has clear benefit
- [ ] **Heading hierarchy** — H1 > H2 > H3 (no skipping levels)
- [ ] **Comparison table** — Helps "best [product] vs [product]" searches
- [ ] **FAQ section** — 5-7 questions people actually search
- [ ] **Internal links** — Link to relevant posts and category pages
- [ ] **Canonical URL** — Points to your live domain (update placeholder)
- [ ] **Affiliate disclosure** — Visible early in article

### Structure Summary

```
1. Header/Nav (consistent across all pages)
2. Breadcrumb (for user navigation + Google crawl)
3. Title + Meta (clear what article is about)
4. Disclosure (legal + trust)
5. Intro (hook + promise + authority)
6. Why This Category Matters (build desire)
7. Top 3 Picks (★★★★★ ratings + links)
8. Comparison Table (structured data)
9. How to Choose (help user decide)
10. FAQ (long-tail SEO + answers)
11. Newsletter CTA (grow email list)
12. Footer (consistent, legal links)
```

### Examples of Good Product Articles

This template is modeled after [posts/best-airfryers-uk.html](posts/best-airfryers-uk.html) and [posts/wireless-earbuds-under-50-uk.html](posts/wireless-earbuds-under-50-uk.html) — check them for real-world examples.

### Publishing Checklist

Before publishing, verify:

- [ ] All [PLACEHOLDERS] replaced
- [ ] Amazon links use correct ASIN and target="_blank"
- [ ] Affiliate disclosure is prominent
- [ ] Heading hierarchy is correct (H1 once, H2 for sections, H3 for subsections)
- [ ] Links to blog.html use correct relative path
- [ ] Breadcrumb links work
- [ ] Newsletter form has proper styling
- [ ] Footer links all work
- [ ] Canonical URL updated to your domain
- [ ] Meta description is unique and compelling (155 chars max)
- [ ] og:url in head matches canonical
- [ ] Reading time is accurate
- [ ] Tested on mobile (DevTools)

### Questions?

Check the existing articles in `posts/` directory for real-world examples of structure and formatting.
