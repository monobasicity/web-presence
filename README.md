# My Journey Blog

A beautiful, minimal Jekyll blog for documenting your journey through tech, health, philosophy, gaming, anime, and life.

## Features

- Clean, dark-themed design
- Responsive layout for all devices
- Category pages for each topic
- Tag system for cross-topic organization
- Reading time estimates
- Previous/next post navigation
- RSS feed support
- SEO optimized

## Quick Start

### Local Development

1. Install Ruby (version 2.7 or higher)
2. Install Bundler: `gem install bundler`
3. Install dependencies: `bundle install`
4. Start the server: `bundle exec jekyll serve`
5. Visit `http://localhost:4000`

### GitHub Pages Deployment

1. Push this repository to GitHub
2. Go to repository Settings > Pages
3. Select "Deploy from a branch"
4. Choose `main` branch and `/ (root)` folder
5. Your site will be live at `https://yourusername.github.io/repo-name`

## Adding Posts

Create new posts by adding Markdown files to the `_posts` directory.

### File Naming

Posts must be named with the format: `YYYY-MM-DD-title.md`

Example: `2026-01-22-my-first-post.md`

### Front Matter Template

```yaml
---
title: "Your Post Title"
description: "A brief description of your post."
date: 2026-01-22
categories: [tech]  # Options: tech, health, philosophy, gaming, anime, life
tags: [tag1, tag2, tag3]
---

Your content goes here...
```

### Available Categories

- `tech` - Software, tools, and digital workflows
- `health` - Physical and mental wellness
- `philosophy` - Deep thoughts and reflections
- `gaming` - Video game reviews and discussions
- `anime` - Series reviews and analyses
- `life` - Personal stories and lessons

## Customization

### Site Configuration

Edit `_config.yml` to update:

- Site title and description
- Author information
- Social media links
- Permalink structure

### Styling

Main styles are in `assets/css/main.css`. CSS variables at the top make it easy to customize colors and fonts.

### Adding New Categories

1. Create a new file in `/categories/` (copy an existing one)
2. Add the category color to `_config.yml`
3. Add the category color to `assets/css/main.css`
4. Add the category icon to the layouts

## Project Structure

```
├── _config.yml          # Site configuration
├── _layouts/            # Page templates
│   ├── default.html
│   ├── home.html
│   ├── post.html
│   ├── page.html
│   ├── category.html
│   └── tag.html
├── _includes/           # Reusable components
│   ├── header.html
│   ├── footer.html
│   └── post-card.html
├── _posts/              # Your blog posts (add .md files here!)
├── assets/
│   ├── css/main.css     # Styles
│   └── js/main.js       # JavaScript
├── categories/          # Category pages
├── index.html           # Home page
├── about.md             # About page
├── posts.html           # All posts page
├── tags.html            # Tags page
└── 404.html             # 404 error page
```

## License

MIT License - Feel free to use this template for your own blog!
