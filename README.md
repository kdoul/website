# kdoul.me

Personal website + blog. Built with [Hugo](https://gohugo.io) and the
[terminal theme](https://github.com/panr/hugo-theme-terminal), deployed
to GitHub Pages via GitHub Actions on every push to `main`.

## Daily use

```bash
# new post
hugo new content posts/my-post.md

# local preview at http://localhost:1313
hugo server -D

# publish
git add . && git commit -m "post: my post" && git push
```

## Structure

- `hugo.toml` — site config (menu, subtitle, social links)
- `content/posts/` — blog posts (Markdown)
- `content/{about,projects,contact}/index.md` — static pages
- `static/style.css` — custom palette + terminal-window chrome (overrides theme CSS)
- `static/favicon.svg`, `favicon.png`, `apple-touch-icon.png`, `og-image.png` — site icons and link-preview image
- `static/CNAME` — custom domain for GitHub Pages
- `layouts/` — site-level overrides: terminal title bar/nav (`partials/header.html`), homepage (`index.html`), SEO tags (`partials/extended_head.html`), `robots.txt`
- `.github/workflows/deploy.yml` — CI/CD
