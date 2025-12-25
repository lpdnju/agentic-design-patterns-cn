# Website Deployment Guide | 网站部署指南

This document explains how to deploy the book website using GitHub Pages.

## 🚀 Quick Deploy (GitHub Pages)

### Step 1: Push changes to GitHub

```bash
git add .
git commit -m "Add: GitHub Pages deployment configuration"
git push origin main
```

### Step 2: Enable GitHub Pages

1. Go to your repository on GitHub: https://github.com/ginobefun/agentic-design-patterns-cn
2. Navigate to **Settings** → **Pages**
3. Under "Build and deployment":
   - **Source**: Select "GitHub Actions"
4. The workflow will automatically build and deploy your site

### Step 3: Access your website

After the first successful deployment (usually 2-3 minutes), your site will be available at:

**https://ginobefun.github.io/agentic-design-patterns-cn/**

---

## 🔧 Local Development

### Prerequisites

- Ruby 3.0+ installed
- Bundler gem installed (`gem install bundler`)

### Setup

```bash
# Install dependencies
bundle install

# Serve locally with live reload
bundle exec jekyll serve --livereload

# Open in browser
# http://localhost:4000/agentic-design-patterns-cn/
```

### Build for production

```bash
bundle exec jekyll build
# Output will be in _site/ directory
```

---

## 📁 Project Structure

```
├── _config.yml              # Jekyll configuration
├── _sass/custom/            # Custom SCSS styles
├── .github/workflows/       # GitHub Actions workflow
├── assets/css/              # Compiled CSS
├── index.md                 # Homepage
├── Gemfile                  # Ruby dependencies
├── 00-Table-of-Contents.md  # Table of contents
├── 01-Dedication.md         # Dedication chapter
├── ...                      # Other chapters
└── codes/                   # Code examples (excluded from build)
```

---

## 🎨 Customization

### Theme

The site uses [Just the Docs](https://just-the-docs.github.io/just-the-docs/) theme, which provides:
- Full-text search
- Dark mode support
- Mobile-responsive design
- Easy navigation

### Styling

Custom styles are in `_sass/custom/custom.scss`. Key customizations:
- Yellow highlighting for Chinese text (`<mark>` tags)
- Bilingual-friendly typography
- Enhanced table styling

### Configuration

Edit `_config.yml` to customize:
- Site title and description
- Navigation links
- Search settings
- Footer content

---

## 🔄 Updating Content

1. Edit any `.md` file in the repository
2. Commit and push to `main` branch
3. GitHub Actions will automatically rebuild and deploy

---

## 🐛 Troubleshooting

### Build fails

Check the Actions tab on GitHub for error logs. Common issues:
- Invalid YAML in `_config.yml`
- Broken Markdown syntax
- Missing files referenced in content

### Site not updating

- Clear browser cache
- Wait a few minutes for CDN propagation
- Check if the workflow completed successfully

### Local serve issues

```bash
# Try cleaning and rebuilding
bundle exec jekyll clean
bundle exec jekyll serve
```

---

## 📚 Resources

- [Just the Docs Documentation](https://just-the-docs.github.io/just-the-docs/)
- [Jekyll Documentation](https://jekyllrb.com/docs/)
- [GitHub Pages Documentation](https://docs.github.com/en/pages)
