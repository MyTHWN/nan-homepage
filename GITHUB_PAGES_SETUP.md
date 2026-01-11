# GitHub Pages Setup for nan.ai

## ✅ Already Done:
- ✅ Git repository initialized
- ✅ All files committed
- ✅ CNAME file created with `nan.ai`
- ✅ Branch set to `main`

## Next Steps:

### 1. Create a GitHub Repository

1. Go to https://github.com/new
2. Repository name: `nan-ai` (or any name you prefer)
3. Description: "Personal website for nan.ai"
4. **Make it Public** (required for free GitHub Pages)
5. **DO NOT** initialize with README, .gitignore, or license (we already have these)
6. Click "Create repository"

### 2. Connect and Push Your Code

After creating the repository, GitHub will show you commands. Use these:

```bash
cd /Users/nan/claudeCode
git remote add origin https://github.com/YOUR_USERNAME/nan-ai.git
git push -u origin main
```

**Replace `YOUR_USERNAME` with your actual GitHub username.**

### 3. Enable GitHub Pages

1. Go to your repository on GitHub
2. Click **Settings** (top right of the repo)
3. Scroll down to **Pages** in the left sidebar
4. Under **Source**, select:
   - Branch: `main`
   - Folder: `/ (root)`
5. Click **Save**

### 4. Configure Custom Domain

1. Still in **Settings → Pages**
2. Under **Custom domain**, enter: `nan.ai`
3. Check **Enforce HTTPS** (recommended)
4. GitHub will verify the domain (this may take a few minutes)

### 5. Configure DNS Records

Go to your domain registrar (where you bought nan.ai) and add these DNS records:

#### A Records (add all 4):
- **Type**: A
- **Name**: `@` (or leave blank, depending on your registrar)
- **Value**: `185.199.108.153`
- **TTL**: 3600 (or default)

- **Type**: A  
- **Name**: `@`
- **Value**: `185.199.109.153`
- **TTL**: 3600

- **Type**: A
- **Name**: `@`
- **Value**: `185.199.110.153`
- **TTL**: 3600

- **Type**: A
- **Name**: `@`
- **Value**: `185.199.111.153`
- **TTL**: 3600

#### CNAME Record (for www subdomain):
- **Type**: CNAME
- **Name**: `www`
- **Value**: `YOUR_USERNAME.github.io` (replace with your GitHub username)
- **TTL**: 3600

### 6. Wait for DNS Propagation

- DNS changes can take 24-48 hours, but usually work within 1-2 hours
- You can check DNS propagation at: https://www.whatsmydns.net/#A/nan.ai
- Once DNS propagates, GitHub will automatically provision an SSL certificate

### 7. Verify It's Working

- Your site should be live at: `https://nan.ai`
- The `CNAME` file in your repo tells GitHub to use your custom domain
- GitHub will automatically renew your SSL certificate

## Troubleshooting

### If the site doesn't load:
1. Check DNS propagation: https://www.whatsmydns.net/#A/nan.ai
2. Verify the CNAME file exists in your repo root
3. Check GitHub Pages settings show the custom domain
4. Wait a bit longer - DNS can be slow

### If you need to update your site:
```bash
cd /Users/nan/claudeCode
# Make your changes
git add .
git commit -m "Update website"
git push
```
Changes will be live in 1-2 minutes!

## Quick Reference Commands

```bash
# Navigate to project
cd /Users/nan/claudeCode

# Check status
git status

# Add changes
git add .

# Commit
git commit -m "Your commit message"

# Push to GitHub
git push
```
