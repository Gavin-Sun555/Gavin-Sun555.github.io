# Yan's Personal Website

A personal blog and portfolio website built with [Hugo](https://gohugo.io/) using the [CleanWhite](https://github.com/zhaohuabing/hugo-theme-cleanwhite) theme.

🌐 **Live site**: [gavin-sun555.github.io](https://gavin-sun555.github.io/)

## Prerequisites

- [Hugo Extended](https://gohugo.io/installation/) (v0.147+)
- [Git](https://git-scm.com/)
- [Node.js](https://nodejs.org/) (only if using Algolia search indexing)

## Getting Started

```bash
# Clone with submodules (for the theme)
git clone --recurse-submodules <your-repo-url>
cd personal-web-original

# Run the development server
hugo server -D
```

The site will be available at `http://localhost:1313/`.

## Project Structure

```
.
├── .github/workflows/    # GitHub Actions CI/CD
├── content/
│   ├── about/            # About page
│   ├── archive/          # Archive page
│   ├── portfolio/        # Portfolio page
│   ├── post/             # Blog posts
│   └── search/           # Search page
├── static/
│   └── img/              # Static images
├── themes/
│   └── hugo-theme-cleanwhite/  # Theme (git submodule)
├── hugo.toml             # Hugo configuration
└── package.json          # Node.js dependencies (Algolia)
```

## Writing Content

### New blog post

```bash
hugo new post/YYYY-MM-DD-your-post-title.md
```

Then edit the generated file in `content/post/`.

### Front matter template

```yaml
---
layout: post
title: "Your Post Title"
subtitle: "Optional subtitle"
date: YYYY-MM-DD
author: "YAN"
URL: "/YYYY/MM/DD/your-post-slug/"
image: "img/your-header-image.jpg"
tags:
  - tag1
  - tag2
---
```

## Deployment

This site deploys automatically via **GitHub Actions** on every push to `main`/`master`. The workflow:

1. Installs Hugo
2. Builds the site with `hugo --gc --minify`
3. Deploys to GitHub Pages

No manual steps required.

## Algolia Search

To update the search index:

1. Copy `.env.example` to `.env` and fill in your Algolia credentials
2. Run `hugo` to generate the `algolia.json` index
3. Run `npm run algolia` to push the index

## License

Content © Yan Sun. Theme licensed under [Apache 2.0](https://github.com/zhaohuabing/hugo-theme-cleanwhite/blob/master/LICENSE).
