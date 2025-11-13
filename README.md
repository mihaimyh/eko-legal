# Eko Legal Website - Deployment Guide

This directory contains the legal website for Eko, including privacy policy, terms of service, account deletion instructions, and support pages required for Google Play Store compliance.

## 📁 Contents

- `index.html` - Landing page with app description and navigation
- `privacy-policy.html` - Comprehensive privacy policy (GDPR compliant)
- `terms-of-service.html` - Terms of service and usage agreements
- `account-deletion.html` - Step-by-step account deletion guide
- `support.html` - Support center with FAQ and contact information
- `styles.css` - Shared stylesheet for all pages
- `README.md` - This file

## 🚀 Deployment Options

### Option 1: GitHub Pages (from this repository)

Deploy directly from this Eko-Flutter repository:

1. **Push to GitHub:**
   ```bash
   git add legal-site/
   git commit -m "Add legal website for Google Play compliance"
   git push origin main
   ```

2. **Enable GitHub Pages:**
   - Go to your repository on GitHub
   - Navigate to **Settings** → **Pages**
   - Under "Source", select **Deploy from a branch**
   - Select branch: `main`
   - Select folder: `/legal-site` (or `/ (root)` if you move files to root)
   - Click **Save**

3. **Wait for deployment** (2-5 minutes)

4. **Access your site:**
   - URL: `https://[your-username].github.io/Eko-Flutter/`
   - Or: `https://[your-username].github.io/Eko-Flutter/index.html`

### Option 2: Separate Repository (Recommended for custom domain)

Create a dedicated repository for the legal site:

1. **Create new repository:**
   - Repository name: `eko-legal` or `eko-app`
   - Make it public
   - Don't initialize with README (we have one)

2. **Copy files to new repository:**
   ```bash
   # From your Eko-Flutter directory
   cd ..
   git clone https://github.com/[your-username]/eko-legal.git
   cd eko-legal
   
   # Copy all files from legal-site
   cp ../Eko-Flutter/legal-site/* .
   
   # Commit and push
   git add .
   git commit -m "Initial commit: Eko legal website"
   git push origin main
   ```

3. **Enable GitHub Pages:**
   - Go to repository **Settings** → **Pages**
   - Source: `main` branch, `/ (root)` folder
   - Click **Save**

4. **Access your site:**
   - URL: `https://[your-username].github.io/eko-legal/`

### Option 3: Custom Domain (Professional)

If you have a custom domain (e.g., `eko-app.com` or `flickai.net`):

1. **Follow Option 2** above to create a separate repository

2. **Configure custom domain:**
   - In repository **Settings** → **Pages**
   - Under "Custom domain", enter: `eko-app.com` or `legal.flickai.net`
   - Click **Save**

3. **Update DNS settings** at your domain registrar:
   
   For root domain (`eko-app.com`):
   ```
   A     @     185.199.108.153
   A     @     185.199.109.153
   A     @     185.199.110.153
   A     @     185.199.111.153
   ```
   
   For subdomain (`legal.flickai.net`):
   ```
   CNAME legal [your-username].github.io
   ```

4. **Enable HTTPS** in GitHub Pages settings (automatic after DNS propagation)

## 🔗 Update Google Play Console

Once deployed, update your Google Play Console with the URLs:

### Privacy Policy URL:
```
https://[your-username].github.io/Eko-Flutter/privacy-policy.html
```
Or with custom domain:
```
https://eko-app.com/privacy-policy.html
```

### Steps to Update Play Console:
1. Go to [Google Play Console](https://play.google.com/console)
2. Select your Eko app
3. Navigate to **App content** → **Privacy policy**
4. Enter your privacy policy URL
5. Save changes

### Also Update These Sections:
- **Store listing** → Privacy policy link
- **App content** → Data safety → Privacy policy
- **Target audience** → Privacy policy (if requested)

## ✅ Verification Checklist

After deployment, verify these items:

- [ ] All pages load correctly
- [ ] Navigation links work between pages
- [ ] Mobile responsive design works
- [ ] Privacy policy includes all required disclosures
- [ ] Account deletion instructions are clear
- [ ] Contact email (`myh.public@gmail.com`) is correct throughout
- [ ] "Last Updated" dates are current
- [ ] External links (Firebase, Google) work
- [ ] HTTPS is enabled (shows padlock in browser)

## 🔄 Updating Content

To update any page:

1. **Edit the HTML file:**
   ```bash
   cd legal-site
   # Edit the file you want to update
   nano privacy-policy.html  # or use your preferred editor
   ```

2. **Update the "Last Updated" date** in the file

3. **Commit and push:**
   ```bash
   git add privacy-policy.html
   git commit -m "Update privacy policy: [describe changes]"
   git push origin main
   ```

4. **GitHub Pages auto-deploys** (takes 1-2 minutes)

## 📱 Testing on Mobile

Before submitting to Google Play, test on mobile:

1. **Open on phone browser:**
   - Visit your deployed URL
   - Test all pages and navigation
   - Verify readability and layout

2. **Test different screen sizes:**
   - Portrait and landscape modes
   - Different Android devices if possible

3. **Verify load speed:**
   - Should load in under 2 seconds on 3G

## 🛠️ Troubleshooting

### GitHub Pages not working?

1. **Check repository settings:**
   - Ensure repository is public (or has Pages enabled for private repos with Pro)
   - Verify correct branch and folder selected

2. **Check file names:**
   - Must be lowercase
   - No spaces in filenames
   - Use hyphens, not underscores (for URLs)

3. **Wait for build:**
   - Initial deployment can take 5-10 minutes
   - Check **Actions** tab for build status

### 404 Errors?

1. **Verify URL structure:**
   - With subfolder: `https://username.github.io/Eko-Flutter/privacy-policy.html`
   - Without subfolder: `https://username.github.io/eko-legal/privacy-policy.html`

2. **Check file paths:**
   - All files must be in the correct folder
   - Links must use relative paths or full URLs

### Styling not working?

1. **Check CSS link:**
   - Verify `<link rel="stylesheet" href="styles.css">` in each HTML file
   - Ensure `styles.css` is in the same directory

2. **Clear browser cache:**
   - Hard refresh: Ctrl+F5 (Windows) or Cmd+Shift+R (Mac)

## 🔐 Security & Privacy

- ✅ No user data collected by this static site
- ✅ No cookies or tracking
- ✅ HTTPS enabled by default on GitHub Pages
- ✅ No JavaScript (pure HTML/CSS)
- ✅ No external dependencies (except Google Fonts optional)

## 📝 Content Compliance

This legal website includes:

### Privacy Policy ✅
- Firebase services disclosure
- Google Sign-In / Apple Sign-In
- AI-generated content (Gemini)
- Data collection and usage
- User rights (GDPR)
- Children's privacy (COPPA)
- Data retention and deletion
- International data transfers
- Contact information

### Terms of Service ✅
- User eligibility (13+)
- Account requirements
- Acceptable use policy
- AI content disclaimers
- Intellectual property
- Liability limitations
- Termination rights
- Governing law (Romania/EU)

### Account Deletion ✅
- In-app deletion instructions
- Email deletion alternative
- Data deletion scope
- Timeline and consequences
- Cannot be undone warning

### Support Page ✅
- Contact information
- FAQ section
- Troubleshooting guides
- Response time expectations

## 📧 Contact & Maintenance

**Developer:** FlickAI  
**Support Email:** myh.public@gmail.com  
**Repository:** https://github.com/[your-username]/Eko-Flutter

### Maintenance Schedule:
- Review privacy policy: Every 6 months or when features change
- Update terms of service: When app functionality changes
- Check external links: Quarterly
- Update "Last Updated" dates: When content changes

## 📄 License

These legal documents are specific to the Eko application and FlickAI. 

The HTML/CSS code structure can be reused for other projects, but you must:
- Update all company/app-specific information
- Update contact details
- Modify privacy/terms content to match your app
- Consult a lawyer for legal compliance

---

**Last Updated:** November 13, 2024  
**Version:** 1.0.0

For questions or issues with this legal site, contact: myh.public@gmail.com

