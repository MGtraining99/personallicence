# PersonalLicence.Training

Static site for PersonalLicence.Training — part of MG Training Ltd.

## Deploying via GitHub Pages

1. **Create a repository**
   - Go to github.com → New repository
   - Name it anything (e.g. `personallicence-training`)
   - Public repos get free GitHub Pages hosting

2. **Upload these files**
   - Easiest: on the repo's main page, click "Add file" → "Upload files", drag in everything from this folder (keep the `assets/img/` folder structure intact)
   - Or via git:
     ```
     git init
     git add .
     git commit -m "Initial site"
     git branch -M main
     git remote add origin https://github.com/YOUR-USERNAME/YOUR-REPO.git
     git push -u origin main
     ```

3. **Enable GitHub Pages**
   - Repo → Settings → Pages
   - Source: "Deploy from a branch"
   - Branch: `main`, folder: `/ (root)`
   - Save. GitHub will build a URL like `https://YOUR-USERNAME.github.io/YOUR-REPO`

4. **Connect personallicence.training**
   - The `CNAME` file in this repo already tells GitHub Pages which domain to serve
   - In repo → Settings → Pages → Custom domain, enter `personallicence.training` and save
   - At your domain registrar (wherever you bought personallicence.training), add these DNS records:
     - **A records** for the apex domain (`personallicence.training`), pointing to GitHub's IPs:
       ```
       185.199.108.153
       185.199.109.153
       185.199.110.153
       185.199.111.153
       ```
     - **CNAME record** for `www` pointing to `YOUR-USERNAME.github.io`
   - DNS changes can take a few hours to propagate
   - Once live, tick "Enforce HTTPS" in the Pages settings (may take a little while to become available after DNS is detected)

## SEO notes

- Each page has a unique `<title>`, meta description, canonical URL, and Open Graph tags
- `sitemap.xml` and `robots.txt` are included at the root — once live, submit the sitemap in Google Search Console (`https://personallicence.training/sitemap.xml`)
- The homepage includes JSON-LD structured data describing the organisation and qualification
- Logos are real optimized image files (not embedded base64), so pages load fast — a direct ranking factor
- Consider adding Google Search Console + Google Analytics (or a privacy-friendly alternative) once live, to track indexing and traffic

## Updating content

All four pages share styling inline in each file's `<style>` block. If you want a shared stylesheet instead (one CSS file all pages link to, easier to maintain), that's a quick follow-up — just ask.

## File structure

```
/
├── index.html          → Home page
├── about-us.html        → About Us
├── faqs.html            → FAQs
├── contact-us.html      → Contact (Zoho form embedded)
├── robots.txt
├── sitemap.xml
├── CNAME                → tells GitHub Pages your custom domain
└── assets/img/           → all logos + favicon
```
