# Deployment Instructions for Your Academic Website

## Overview
Your personal academic website is now ready to deploy! This guide will walk you through deploying it to GitHub Pages (free hosting).

## Prerequisites
- A GitHub account (https://github.com)
- Git installed on your computer

## Method 1: Deploy to GitHub Pages (Recommended)

### Step 1: Create GitHub Repository
1. Go to GitHub.com and log in
2. Click the "+" icon in the top right and select "New repository"
3. Name your repository: `Chenguang-Zhao.github.io` (exactly as shown)
4. Make the repository **Public**
5. Do NOT initialize with README, .gitignore, or license
6. Click "Create repository"

### Step 2: Push Your Website to GitHub
Open Terminal in your website directory and run:

```bash
# Initialize git repository
git init

# Add all files
git add .

# Create first commit
git commit -m "Initial commit: Personal academic website"

# Add your GitHub repository as remote
git remote add origin https://github.com/Chenguang-Zhao/Chenguang-Zhao.github.io.git

# Push to GitHub
git branch -M main
git push -u origin main
```

### Step 3: Enable GitHub Pages
1. Go to your repository on GitHub
2. Click "Settings" tab
3. In the left sidebar, click "Pages"
4. Under "Source", select "Deploy from a branch"
5. Under "Branch", select "main" and "/ (root)"
6. Click "Save"

### Step 4: Wait for Deployment
- GitHub will automatically build and deploy your site
- This takes 2-5 minutes for the first deployment
- Once complete, your site will be live at: **https://chenguang-zhao.github.io**

## Method 2: Test Locally with Docker (Optional)

If you want to test the site locally before deploying:

```bash
# Build and run with Docker
docker-compose up

# Your site will be available at http://localhost:4000
```

## What's Been Set Up

### ✅ Pages Created
- **Home** (_pages/about.md) - Your bio and introduction
- **Research** (_pages/research.md) - Research interests and opportunities for students
- **Publications** (_pages/publications.html) - Publications list (ready for you to add)
- **Teaching** (_pages/teaching.md) - Teaching information
- **CV** (_pages/cv.md) - CV page with PDF download link

### ✅ Configuration
- Site title: Chenguang Zhao
- Email: ZhaoChenguang@sau.edu
- GitHub: Chenguang-Zhao
- Location: Davenport, Iowa
- Employer: St. Ambrose University

### ✅ Files Integrated
- CV PDF uploaded to `/files/cv.pdf`
- Download button on CV page

### ✅ Analytics Ready
- Visit counter setup ready (see instructions below)
- Google Analytics ready to configure

## Post-Deployment Tasks

### 1. Add Profile Picture
1. Replace `images/profile.png` with your professional photo
2. Recommended size: 500x500 pixels
3. Keep the filename as `profile.png` or update `_config.yml` line 26

### 2. Enable Visit Counter (Choose One Option)

#### Option A: ClustrMaps (Shows geographic map)
1. Go to https://clustrmaps.com/
2. Sign up for free account
3. Add your website URL: https://chenguang-zhao.github.io
4. Copy the widget code they provide
5. Paste it in `_includes/analytics-providers/custom.html` (replace the example)

#### Option B: Counter.dev (Simple counter)
1. Uncomment line 17 in `_includes/analytics-providers/custom.html`
2. The counter will work immediately (no signup needed)

### 3. Add Google Analytics (Optional)
1. Go to https://analytics.google.com
2. Create a new property for your website
3. Get your tracking ID (format: G-XXXXXXXXXX)
4. Edit `_config.yml` line 154: change provider to "google-analytics-4"
5. Edit `_config.yml` line 157: add your tracking ID

### 4. Add Google Scholar & ORCID Links
Edit `_config.yml` lines 37-40:
```yaml
googlescholar    : "https://scholar.google.com/citations?user=YOUR_ID"
orcid            : "https://orcid.org/YOUR-ORCID-ID"
```

### 5. Add Publications
- Add publication markdown files to `_publications/` directory
- Follow the format of existing sample publications
- Or use the CSV to markdown converter in `markdown_generator/`

### 6. Update Teaching Information
- Edit `_pages/teaching.md` with your actual courses
- Add office hours and location

## Making Updates

After your site is deployed, to make updates:

```bash
# Make your changes to files
# Then commit and push:

git add .
git commit -m "Description of changes"
git push
```

GitHub Pages will automatically rebuild your site (takes 2-5 minutes).

## Troubleshooting

### Site not showing up?
- Check GitHub Pages settings (Settings → Pages)
- Make sure repository name is exactly: `Chenguang-Zhao.github.io`
- Wait 5 minutes after first push

### Changes not appearing?
- Changes take 2-5 minutes to deploy
- Clear your browser cache (Cmd+Shift+R on Mac, Ctrl+Shift+R on Windows)

### Need to test locally?
- Use Docker method: `docker-compose up`
- Or use GitHub Actions preview branches

## Local Development Note

**Important**: Local Jekyll development has Ruby dependency issues on macOS with system Ruby 2.6.

**Solutions:**
1. **Use Docker** (recommended): `docker-compose up`
2. **Deploy to GitHub Pages** and test there (changes appear in 2-5 minutes)
3. **Install rbenv** to manage Ruby versions:
   ```bash
   brew install rbenv
   rbenv install 3.1.0
   rbenv local 3.1.0
   bundle install
   bundle exec jekyll serve
   ```

## Support & Documentation
- AcademicPages Documentation: https://github.com/academicpages/academicpages.github.io
- Jekyll Documentation: https://jekyllrb.com/docs/
- GitHub Pages Documentation: https://docs.github.com/en/pages

## Need Help?
- Check the README.md in the repository
- Review the AcademicPages wiki
- GitHub Issues: https://github.com/academicpages/academicpages.github.io/issues

---

**Your website is ready to go live! Follow the deployment steps above to publish it.**
