# kdoul.me

Personal website + blog. Built with [Hugo](https://gohugo.io) and the
[terminal theme](https://github.com/panr/hugo-theme-terminal), deployed
to GitHub Pages via GitHub Actions.

## One-time setup

1. Create a GitHub repo (e.g. `kdoul.me`) and push this directory:

   ```bash
   git init
   git submodule add https://github.com/panr/hugo-theme-terminal.git themes/terminal
   git add .
   git commit -m "initial site"
   git branch -M main
   git remote add origin git@github.com:YOURUSERNAME/kdoul.me.git
   git push -u origin main
   ```

2. In the repo: **Settings → Pages → Build and deployment → Source: GitHub Actions**.
   The included workflow (`.github/workflows/deploy.yml`) builds and deploys on every push to `main`.

3. **Settings → Pages → Custom domain**: enter `kdoul.me`, wait for the
   certificate, then enable *Enforce HTTPS*. `www.kdoul.me` will redirect
   to the apex automatically.

4. In Cloudflare DNS:
   - `kdoul.me`  → CNAME → `YOURUSERNAME.github.io` (DNS only until the cert is issued)
   - `www`       → CNAME → `YOURUSERNAME.github.io` (DNS only)

   `*.home.kdoul.me` records are unaffected.

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

- `hugo.toml` — site config (theme color, menu, subtitle)
- `content/posts/` — blog posts (Markdown)
- `content/{about,projects,contact}/index.md` — static pages
- `static/CNAME` — custom domain for GitHub Pages
- `.github/workflows/deploy.yml` — CI/CD
- `static/style.css` — custom palette + terminal-window chrome (overrides theme CSS)
- `layouts/` — site-level overrides: terminal title bar/nav (`partials/header.html`) and homepage (`index.html`)
