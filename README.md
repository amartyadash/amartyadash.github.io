## What this repo is

This is a Jekyll site repository, built as a GitHub Pages-style site.

Key pieces:

- _config.yml — site-wide settings
- Gemfile / Gemfile.lock — Ruby/Jekyll versions and plugins
- index.md, about.md, projects.md, etc. — content pages
- _layouts — page templates
- _includes — reusable HTML snippets like header/footer
- _posts — blog posts
- style.scss — custom styles
- images — site images

Because the repo is named `amartyadash.github.io`, GitHub can publish it as your user site at `https://amartyadash.github.io`.

---

## How it is configured

### _config.yml
This is the main configuration file.

It defines:
- `title`, `author`, `description`
- `url` and `baseurl`
- theme: `minima`
- plugins: `jekyll-feed`, `jekyll-seo-tag`
- `header_pages` — pages shown in the header navigation
- `minima.social_links` and `minima.skin`

So this file controls global settings, navigation, theme options, and site metadata.

### Gemfile
This tells Bundler which gems to install:
- `jekyll ~> 4.2.2`
- `minima ~> 2.5`
- `jekyll-feed`
- `jekyll-remote-theme`
- `jekyll-seo-tag`
- `webrick`

If you change the Gemfile, run:
```sh
bundle install
```

### Gemfile.lock
This locks exact gem versions so the site builds consistently.

---

## Where content lives

### Home page
- index.md
- Uses `layout: home`
- Contains your home page Markdown content and the list of posts section

### Other pages
- about.md
- education.md
- experience.md
- projects.md

These are simple Markdown files. They are included in the site header because _config.yml lists them in `header_pages`.

### Blog posts
- _posts
- Files here are blog posts with Jekyll front matter and filenames like `YYYY-MM-DD-title.markdown`

---

## Templates and layout

### home.html
Controls how the homepage is rendered:
- inserts page content
- loops through `site.posts`
- shows post titles, dates, excerpts

### default.html
The base HTML wrapper used by every page.

### page.html
Used for normal content pages (`about`, `projects`, etc.)

### post.html
Used for blog posts.

---

## Reusable page pieces

### _includes
- `header.html`
- `footer.html`
- `head.html`
- `google-analytics.html`
- `custom-head.html`
- `social.html`
- `disqus_comments.html`

These are partial templates included by layouts. If you want to change the header or footer, edit the files here.

---

## How to modify the site

### Change text/content
Edit Markdown files:
- index.md
- about.md
- education.md
- experience.md
- projects.md
- any `_posts/*.markdown`

### Change site settings
Edit _config.yml:
- change `title`
- change `description`
- add or remove `header_pages`
- update social links
- adjust theme options

### Change layout/HTML structure
Edit `_layouts/*.html`:
- modify how page content is wrapped
- change homepage post listing in home.html
- change site shell in `default.html`

### Change header/footer or reusable blocks
Edit `_includes/*.html`.

### Change styling
Edit style.scss or the minima files if you want custom CSS.

### Add a new page
Create a new Markdown file:
```md
---
layout: page
title: New Page
---
Your content here.
```
Then add it to _config.yml under `header_pages` if you want it in the top navigation.

### Add a blog post
Create a file in _posts:
```md
---
title: My New Post
date: 2026-06-23
---
Post content here.
```

---

## How to preview locally

After installing your Ruby/Jekyll environment and gems:
```sh
bundle exec jekyll serve
```

Then open:
```sh
http://127.0.0.1:4000
```

---

## Important note

This repo is currently using `jekyll` directly instead of the GitHub Pages gem. That’s fine for local build and deployment, but if you want exact GitHub Pages compatibility later, you may want to switch to the `github-pages` gem or use supported plugin versions.

If you want, I can also show you:
1. exactly where the page nav is built,
2. how to add a new menu link,
3. how to change the homepage content safely.