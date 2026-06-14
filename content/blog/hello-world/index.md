---
title: "Hello, world — the new site is live"
date: 2026-06-14
draft: false
tags: ["meta", "hugo"]
summary: "Why I rebuilt my personal website on Hugo + Cloudflare Pages, and how I'll post from now on."
cover:
  image: ""        # optional: drop an image in this folder and set its filename here
  alt: ""
  caption: ""
---

Welcome to the rebuilt site. It now runs on [Hugo](https://gohugo.io) with the
[PaperMod](https://github.com/adityatelange/hugo-PaperMod) theme and deploys
automatically to Cloudflare Pages on every `git push`.

## How I post now

Each post is a folder under `content/blog/`. To add one:

```bash
hugo new blog/my-post/index.md
```

Then write Markdown, drop any images **into the same folder**, and reference them
relatively:

```markdown
![A descriptive caption](my-image.png)
```

Set `draft: false`, commit, and push — the post is live in about a minute.

## What's here

- A built-in [résumé](/resume/) (also downloadable as PDF).
- A list of [certifications & achievements](/certifications/).
- A way to [get in touch or book a call](/contact/).

More soon.
