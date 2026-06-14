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
