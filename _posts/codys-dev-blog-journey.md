---
layout: post
title: "Building Cody's Dev Blog: A Journey from Design to Deployment"
date: 2025-06-17 16:19:00 -0700
categories: [jekyll, web-dev, github-pages]
excerpt_separator: <!--more-->
---

What started as a simple idea — “I want a clean blog to post my dev writeups” — turned into a detailed walkthrough of static site building, templating, versioning, and deployment. This post outlines the entire process I went through to build **Cody's Dev Blog**, from the first layout concept to pushing a polished site to GitHub Pages.

<!--more-->

## 🖼️ Designing the Blog Layout

The journey kicked off with a visual mockup. I uploaded a JPEG of the desired layout, and from that came a Tailwind-based dark mode blog layout, built with responsiveness and simplicity in mind. Key elements included:

- Hero header with the blog title
- Two-column layout with a sidebar
- Modern card design for posts
- A comment form built right into the homepage

## 🛠 Integrating Markdown Support

Next, I needed to feed Markdown posts into this layout. That’s where Jekyll came in.

I learned that:

- Jekyll supports Markdown out of the box
- Posts must go in a `_posts/` directory and follow the `YYYY-MM-DD-title.md` format
- Front matter is crucial for titles, categories, and excerpt handling

Using `excerpt_separator: <!--more-->` let me control where the preview stopped.

## 💡 Handling Missing Pieces

While the UI came together nicely, a few hiccups happened:

- The comment button was initially the same color as the background — easily fixed by improving contrast and padding.
- The post list wasn’t fully clickable — resolved by wrapping links properly.
- The homepage had leftover artifacts from the `minima` Jekyll theme — removed by stripping the `theme:` config and adding a custom `default.html`.

## 🧱 Structuring the Repo

To get things organized and GitHub-ready:

- I created the necessary folders (`_posts`, `_layouts`, `_includes`, `assets/images`)
- Used Tailwind via CDN for quick deployment
- Made `_config.yml` clean, adding `baseurl` and removing unnecessary themes

I learned that GitHub Pages supports Jekyll out of the box, but I had to be careful about base URLs (`/codys-dev-blog` vs `/`).

## 🗺️ SEO and Metadata

To make things searchable and shareable:

- I added Open Graph metadata and Twitter cards
- Enabled the `jekyll-sitemap` plugin to generate a working `sitemap.xml`
- Considered adding a `robots.txt` file (which is next up)

## 💬 Comments? Giscus vs Staticman

I explored two options:

- **Giscus** — GitHub Discussions powered comment system (easy setup, zero backend)
- **Staticman** — static-site compatible backend with GitHub PR-based comment submissions (but requires Netlify or your own webhook)

Ultimately, I’m leaning toward Giscus because of its simplicity.

## 🏷 Tags and Filtering

I added `tags:` to post front matter, built a `tag.html` layout, and created per-tag Markdown files. This allows for simple URL-based filtering without JavaScript.

A future enhancement would be a plugin or script to auto-generate tag index pages.

## 🚀 Polishing the Blog

Final cleanup included:

- A professional `README.md` with usage, screenshot, and instructions
- Cleaned up `default.html` (no theme artifacts)
- Added a navbar and footer with GitHub links
- Fixed spacing between comment sections and footer
- Packaged everything into a downloadable ZIP for version control

## ✅ Final Thoughts

If you're building a personal blog:

- Don’t default to a heavy theme — custom layouts are more flexible
- Use Tailwind for quick design wins (especially via CDN)
- Jekyll is super GitHub-friendly, but mind your folder structure
- SEO and clean metadata go a long way

This project was more than just “set up a blog.” It was a deep dive into clean static site architecture and modern UI decisions — and I’m glad I went through it.

You can check out the blog here: [https://codyliska.github.io/codys-dev-blog](https://codyliska.github.io/codys-dev-blog)
