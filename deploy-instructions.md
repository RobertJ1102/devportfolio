# GitHub Pages + Cloudflare Deployment Guide

## 🚀 Quick Deployment Steps

### 1. Push to GitHub
```bash
git add .
git commit -m "Initial portfolio deployment"
git push origin main
```

### 2. Enable GitHub Pages
1. Go to your GitHub repository
2. Settings → Pages
3. Source: "GitHub Actions"
4. The workflow will automatically build and deploy

### 3. Custom Domain Setup
1. Edit the `CNAME` file with your actual domain
2. In GitHub repo Settings → Pages → Custom domain: Enter your domain
3. Enable "Enforce HTTPS"

### 4. Cloudflare Configuration
1. Add your domain to Cloudflare
2. Set up these DNS records:
   ```
   Type: CNAME
   Name: @ (or www)
   Content: yourusername.github.io
   ```
3. Enable SSL/TLS → Full (strict)
4. Enable automatic HTTPS rewrites

### 5. Update Contact Form
- Replace the email in the contact form with your actual email
- Consider using Formspree, Netlify Forms, or EmailJS for form handling

## 🔧 Development Workflow

### Local Development
```bash
npm run watch  # Starts gulp watch mode
```

### Before Pushing
```bash
npx gulp styles  # Compile SCSS
npx gulp scripts # Compile JS
```

### File Structure for Deployment
- ✅ `index.html` - Main page
- ✅ `css/` - Compiled CSS (auto-generated)
- ✅ `js/` - Compiled JS (auto-generated)
- ✅ `images/` - Static assets
- ✅ `libs/` - Third-party libraries
- ❌ `scss/` - Source files (not needed in production)
- ❌ `node_modules/` - Dependencies (not needed in production)

## 📱 Performance Optimizations

Your site automatically includes:
- ✅ Gzipped assets via GitHub Pages
- ✅ CDN delivery via Cloudflare
- ✅ Automatic HTTPS
- ✅ Minified CSS and JS
- ✅ Optimized images (if properly sized)

## 🎯 Next Steps
1. Replace placeholder projects with your real work
2. Add your actual contact information
3. Test on mobile devices
4. Set up analytics (Google Analytics, Cloudflare Analytics)
5. Consider adding a blog section 