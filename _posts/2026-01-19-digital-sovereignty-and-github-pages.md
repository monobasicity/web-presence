---
layout: default
title: "Digital Sovereignty and the Modern Web Stack: Building on GitHub Pages"
---

In an era defined by algorithmic feeds and ephemeral content, the act of establishing a personal website has evolved from a hobbyist pursuit into a strategic necessity. This post explores the rationale for maintaining a personal web presence in 2026 and details the technical architecture of the platform you are currently reading, built on GitHub Pages.

## The Imperative of Digital Sovereignty

The primary argument for owning a website is the concept of **digital sovereignty**. While social media platforms offer immense reach, they operate on a model of "rented land." Your content, audience connection, and visibility are subject to their terms of service, algorithmic shifts, and corporate stability.

A personal website is the only platform where you possess complete control over your data, branding, and user experience. It serves as a permanent digital home—a canonical source of truth for your portfolio, thoughts, and professional identity.

The image below illustrates this fundamental difference.

![Digital Sovereignty vs. Rented Land]({{ /assets/images/2026-01-19-digital-sovereignty-and-github-pages/2026-01-19-digital-sovereignty-and-github-pages01.png | relative_url }})
*Figure 1: A conceptual model of owning your platform versus relying on third-party services.*

## The Technical Architecture: GitHub Pages and Jekyll

For developers and technical professionals, the most robust and efficient way to build a personal site is through a static site generator (SSG) hosted on a Git-based workflow. This site is hosted on **GitHub Pages**, a service that builds and serves static websites directly from a GitHub repository.

The core engine powering this process is **Jekyll**, a Ruby-based SSG that is tightly integrated with GitHub Pages. The workflow is elegant in its simplicity: you write content in Markdown, push it to your repository, and GitHub automatically compiles it into a complete website.

This "docs-as-code" approach offers several advantages:

1.  **Version Control:** Every change is tracked via Git, allowing for easy rollbacks and collaborative workflows.
2.  **Security & Performance:** Since the output is purely static HTML, CSS, and JavaScript, there is no database to hack and no server-side processing to slow down page loads.
3.  **Zero Maintenance:** There are no servers to manage, no software to patch, and no scaling issues to worry about.

The following flowchart demonstrates the deployment pipeline from your local machine to the live web.

![GitHub Pages Deployment Workflow]({{ /assets/images/2026-01-19-digital-sovereignty-and-github-pages/2026-01-19-digital-sovereignty-and-github-pages02.png | relative_url }})
*Figure 2: The git-based deployment workflow from local development to a live GitHub Pages site.*

## Implementation Guide: The Minimalist Blog Kit

This website was constructed using a minimalist Jekyll template designed for ease of use. The philosophy is to provide a clean, readable foundation that allows you to focus on content.

The structure of the project is intentionally flat and simple. The image below shows the complete file organization.

![Jekyll Project Directory Structure]({{ /assets/images/2026-01-19-digital-sovereignty-and-github-pages/2026-01-19-digital-sovereignty-and-github-pages03.png | relative_url }})
*Figure 3: The directory structure of a minimalist Jekyll blog.*

Here is a breakdown of the essential components I used:

### 1. `_config.yml`
This YAML file is the global configuration for the site. It defines site-wide variables like the title, description, and URL.
```yaml
title: "My Digital Garden"
description: "A collection of thoughts and notes."
baseurl: ""
url: ""
theme: null
```

### 2. `_layouts/default.html`
This HTML template serves as the "wrapper" for every page on the site. It contains the standard `<html>`, `<head>`, and `<body>` tags, including the header and footer. The `{{ content }}` Liquid tag is where the body of your Markdown post is injected.
```html
<!DOCTYPE html>
<html>
<head>
    <title>{{ page.title }}</title>
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <link rel="stylesheet" href="/assets/css/style.css">
</head>
<body>
    <header>
        <h1><a href="/" style="color: inherit;">{{ site.title }}</a></h1>
        <p>{{ site.description }}</p>
    </header>

    <main>
        {{ content }}
    </main>

    <footer>
        <small>&copy; {{ site.time | date: "%Y" }}</small>
    </footer>
</body>
</html>
```

### 3. `assets/css/style.css`
The stylesheet defines the visual aesthetic. This implementation uses modern CSS features like custom properties (variables) for easy theming and includes support for dark mode via the `prefers-color-scheme` media query.
```css
:root {
  --bg: #fffff8;
  --text: #222;
  --accent: #0066cc;
  --font-body: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
}

@media (prefers-color-scheme: dark) {
  :root { --bg: #1a1a1a; --text: #eee; --accent: #66b3ff; }
}

body {
  background: var(--bg);
  color: var(--text);
  font-family: var(--font-body);
  line-height: 1.6;
  max-width: 700px;
  margin: 0 auto;
  padding: 2rem 1rem;
}

header, footer { margin-bottom: 3rem; border-bottom: 2px solid #eee; padding-bottom: 1rem; }
a { color: var(--accent); text-decoration: none; }
a:hover { text-decoration: underline; }
h1, h2, h3 { line-height: 1.2; margin-top: 2rem; }
.post-meta { font-size: 0.9rem; color: #888; }
```

### 4. `index.html`
The homepage uses a simple Liquid loop to iterate through all the posts in the `site.posts` collection, displaying the date and title for each one.
```html
---
layout: default
title: Home
---

<h2>Latest Posts</h2>
<ul>
  {% for post in site.posts %}
    <li>
      <span class="post-meta">{{ post.date | date: "%b %d, %Y" }}</span>
      &mdash; 
      <a href="{{ post.url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>
```

### 5. `_posts/`
This directory contains your content. Each post is a Markdown file with a specific filename format: `YYYY-MM-DD-title.md`. Each file begins with a YAML front-matter block that defines metadata like the post's title and layout.

By adhering to this structure, you have a powerful, scalable, and maintainable blogging platform that lives entirely within your Git repository.