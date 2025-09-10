# Shiv's Blog – Hugo + PaperMod

A fast, minimal blog powered by Hugo and the PaperMod theme. This README covers local setup, content authoring, customization, and deployment to GitHub Pages.

## Prerequisites
- Hugo (extended) v0.148.0 or newer
  - macOS (Homebrew):
    ```bash
    brew install hugo
    ```
  - Verify you have the extended build:
    ```bash
    hugo version
    # look for "+extended" in the output
    ```
- Git and GitHub account (for deployment)

## Quick Start
```bash
# Clone
git clone https://github.com/davshiv20/davshiv20github.io.git
cd davshiv20github.io

# Run local server
hugo server -D
# Visit http://localhost:1313
```

## Project Structure
- `hugo.toml` – Site config (title, theme, params, baseURL, pagination, markup)
- `content/` – Markdown content
  - `content/_index.md` – Home page content
  - `content/posts/` – Blog posts
- `archetypes/` – Default front matter for new content
- `themes/PaperMod/` – Theme (checked into repo; no submodule required)
- `layouts/` – Local overrides/partials (takes precedence over theme)
- `public/` – Generated site output (built by Hugo)
- `.github/workflows/deploy.yaml` – GitHub Actions workflow for Pages

## Local Development
- Start dev server with drafts and live reload:
  ```bash
  hugo server -D
  ```
- Build production site to `public/`:
  ```bash
  hugo --gc --minify
  ```
- Match CI version locally (recommended):
  ```bash
  # CI uses 0.148.0; ensure you have a compatible version
  hugo version
  ```

## Creating Content
- New post (draft by default from `archetypes/default.md`):
  ```bash
  hugo new posts/my-new-post.md
  ```
- Edit the new file under `content/posts/` and set `draft = false` to publish.
- Front matter defaults:
  - `title` – inferred from filename
  - `date` – created date
  - `draft` – starts as `true`

## Configuration
Key settings in `hugo.toml`:
- `baseURL = "https://davshiv20.github.io/"` – Must match your GitHub Pages URL
- `theme = 'PaperMod'`
- `enableRobotsTXT = true`
- `pagination.pagerSize = 5`
- `params.env = "production"`
- `params.googleAnalytics = ""` – Set to your GA measurement ID if using GA
- Goldmark unsafe HTML is enabled to allow raw HTML in Markdown

After changing `baseURL`, rebuild and redeploy to reflect canonical URLs.

## Customization
- PaperMod is vendored under `themes/PaperMod/`.
- To override theme templates/partials, add files under `layouts/` mirroring the theme paths. Hugo will prefer your local `layouts/` over the theme.
- Custom partials:
  - `layouts/partials/google_analytics.html` – Optional custom GA injection. If using PaperMod built-in GA via `params.googleAnalytics`, you may not need this.
- Styling:
  - For light overrides, add assets under `assets/` or `static/` and reference them in a custom head partial (e.g., `layouts/partials/extend_head.html`).

## Deployment (GitHub Pages)
This repo is configured to deploy with GitHub Actions to GitHub Pages:
- Workflow: `.github/workflows/deploy.yaml`
  - Triggers on pushes to `master`
  - Uses Hugo extended v0.148.0
  - Builds the site and publishes the `public/` artifact to GitHub Pages

One-time GitHub setup:
1. In GitHub repo settings, enable Pages:
   - Settings → Pages → Build and deployment → Source: "GitHub Actions"
2. Ensure default branch is `master` (or update the workflow trigger if you change it).

Deploying changes:
```bash
git add -A
git commit -m "Update content"
git push origin master
# GitHub Actions will build and deploy automatically
```

Notes:
- You do not need to commit `public/` when using the Actions workflow; CI builds it. If `public/` is currently tracked, you can keep it, but it’s optional for Pages via Actions.
- If you change the site URL or repository name, update `baseURL` in `hugo.toml`.

## Troubleshooting
- Missing styles or 404s locally:
  - Run with `hugo server -D` (it handles baseURL differences).
- GA not recording:
  - Set `params.googleAnalytics` in `hugo.toml` or ensure your custom GA partial is included.
- Version mismatch errors in CI:
  - Update your local Hugo to match CI (0.148.0) or adjust the workflow `HUGO_VERSION`.
- Theme not applied:
  - Confirm `theme = 'PaperMod'` in `hugo.toml` and that the theme directory exists.

## License
Content is yours. PaperMod theme is licensed per `themes/PaperMod/LICENSE`.
