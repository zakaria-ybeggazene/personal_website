# personal_website

Personal website of Zakaria Ybeggazene — built with [Hugo](https://gohugo.io) and
the [PaperMod](https://github.com/adityatelange/hugo-PaperMod) theme, deployed on
**Cloudflare Pages**. Live at <https://zakaria.ybeggazene.com>.

Languages: English (default), French (`/fr/`), Arabic (`/ar/`, RTL).

## Local development

The theme is a git submodule, so clone with submodules:

```bash
git clone --recurse-submodules <repo-url>
# or, in an existing clone:
git submodule update --init --recursive

hugo server -D     # http://localhost:1313
```

## Adding a blog post

```bash
hugo new blog/my-post/index.md
```

Write Markdown, put images in the same folder, set `draft: false`, then
`git push`. Cloudflare Pages rebuilds and deploys automatically (~1 min).

### Translations & the English fallback

Posts are leaf bundles (`blog/my-post/index.md`). To translate one, add
`index.fr.md` / `index.ar.md` in the same folder.

Every post should appear in **all** languages. For a language you haven't
translated yet, add a stub `index.<lang>.md` containing only front matter plus
`translated: false`:

```yaml
---
title: "Translated title (shown in the list & tab)"
date: 2026-06-17
draft: false
translated: false
summary: "Translated summary."
ShowToc: true
---
```

The site then:

- shows the post in that language's blog list with an **EN** badge, and
- renders the **English content** on the post page under a localized
  "not translated yet" notice (reading time, TOC and images all come from the
  English version).

When you write a real translation, fill in the body and either set
`translated: true` or remove the key — the badge and notice disappear
automatically.

## Analytics

Both options are **opt-in** via site params in `config/_default/hugo.yaml`
(nothing is tracked until you set them), wired in
`layouts/_partials/extend_head.html`.

**Cloudflare Web Analytics** (visitor + per-page counts, private dashboard, no
cookies). Simplest path: in the Cloudflare dashboard → your Pages project →
*Web Analytics*, enable it — Cloudflare auto-injects the beacon, no code needed.
Or inject it yourself:

```yaml
params:
  cloudflareAnalyticsToken: "your-beacon-token"
```

**GoatCounter** (upgrade path for a *public* view-count badge on each post).
Create a free site at goatcounter.com, then:

```yaml
params:
  goatcounterCode: "your-site-code"   # e.g. "zakaria" for zakaria.goatcounter.com
```

This loads the counter script and renders a `👁 <count>` badge under each post
(see `layouts/_partials/extend_post_content.html`).

## Cloudflare Pages build settings

| Setting | Value |
|---|---|
| Build command | `hugo --gc --minify` |
| Build output directory | `public` |
| Environment variable | `HUGO_VERSION` = a recent extended version (e.g. `0.163.1`) |

Submodules are cloned automatically by Cloudflare Pages. No Go toolchain is
required (the theme is vendored as a submodule, not a Hugo Module).

## Structure

```
config/_default/hugo.yaml   # site config + the three languages
content/                    # _index, resume, certifications, contact, search, blog/
assets/css/extended/        # custom CSS layered on PaperMod
static/                     # images, icon, résumé/CV PDFs
themes/PaperMod/            # theme (git submodule)
```
