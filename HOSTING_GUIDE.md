# Hosting Guide for nan.ai

## Option 1: Netlify (Recommended - Easiest)

### Steps:
1. **Create a Netlify account** at https://www.netlify.com
2. **Install Netlify CLI** (optional, for command line):
   ```bash
   npm install -g netlify-cli
   ```

3. **Deploy via Netlify Dashboard**:
   - Go to https://app.netlify.com
   - Click "Add new site" → "Deploy manually"
   - Drag and drop your project folder, OR
   - Connect to GitHub/GitLab/Bitbucket for automatic deployments

4. **Configure Custom Domain**:
   - In your site settings, go to "Domain settings"
   - Click "Add custom domain"
   - Enter `nan.ai`
   - Follow the DNS configuration instructions:
     - Add a CNAME record: `www` → `your-site-name.netlify.app`
     - Add an A record: `@` → Netlify's IP (they'll provide it)
     - Or use Netlify DNS (recommended)

5. **SSL Certificate**: Netlify automatically provides free SSL via Let's Encrypt

---

## Option 2: Vercel (Also Very Easy)

### Steps:
1. **Create a Vercel account** at https://vercel.com
2. **Install Vercel CLI**:
   ```bash
   npm install -g vercel
   ```

3. **Deploy**:
   ```bash
   cd /Users/nan/claudeCode
   vercel
   ```
   Or use the Vercel dashboard to drag and drop your folder

4. **Configure Custom Domain**:
   - Go to your project settings → Domains
   - Add `nan.ai` and `www.nan.ai`
   - Update your DNS records as instructed:
     - A record: `@` → Vercel's IP
     - CNAME: `www` → `cname.vercel-dns.com`

5. **SSL**: Automatically handled by Vercel

---

## Option 3: GitHub Pages (Free, but requires GitHub)

### Steps:
1. **Create a GitHub repository**:
   ```bash
   cd /Users/nan/claudeCode
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/yourusername/nan-ai.git
   git push -u origin main
   ```

2. **Enable GitHub Pages**:
   - Go to repository Settings → Pages
   - Source: Deploy from a branch
   - Branch: `main` / `root`
   - Save

3. **Configure Custom Domain**:
   - In Pages settings, add `nan.ai` to Custom domain
   - Create a file named `CNAME` in your repo root with content: `nan.ai`
   - Update DNS:
     - A records: Add GitHub Pages IPs (185.199.108.153, 185.199.109.153, 185.199.110.153, 185.199.111.153)
     - CNAME: `www` → `yourusername.github.io`

---

## Option 4: Cloudflare Pages (Fast & Free)

### Steps:
1. **Create Cloudflare account** at https://dash.cloudflare.com
2. **Add your site**:
   - Go to Pages → Create a project
   - Connect to Git or upload files directly
3. **Configure Domain**:
   - In Pages settings, add custom domain `nan.ai`
   - Cloudflare will handle DNS automatically if you use their nameservers

---

## DNS Configuration for nan.ai

Regardless of which hosting service you choose, you'll need to configure DNS with your domain registrar:

### If using Netlify:
- **A Record**: `@` → `75.2.60.5`
- **CNAME**: `www` → `your-site.netlify.app`

### If using Vercel:
- **A Record**: `@` → `76.76.21.21`
- **CNAME**: `www` → `cname.vercel-dns.com`

### If using GitHub Pages:
- **A Records** (add all 4):
  - `@` → `185.199.108.153`
  - `@` → `185.199.109.153`
  - `@` → `185.199.110.153`
  - `@` → `185.199.111.153`
- **CNAME**: `www` → `yourusername.github.io`

### If using Cloudflare Pages:
- Use Cloudflare's nameservers (they'll provide them)
- DNS is managed automatically

---

## Quick Start (Recommended: Netlify)

1. Go to https://app.netlify.com/drop
2. Drag your `/Users/nan/claudeCode` folder
3. Your site will be live in seconds!
4. Then add custom domain in settings

---

## Notes:
- DNS changes can take 24-48 hours to propagate (usually much faster)
- Make sure you own the domain `nan.ai` and have access to its DNS settings
- All these services offer free SSL certificates automatically
- Netlify and Vercel are the easiest for quick deployment
