# anotherbug-blog

Source repo for `https://anotherbug.com`.

This is a Hugo-based blog. Content lives in this repository, and GitHub Actions builds and publishes the site to GitHub Pages.

The site now uses a single local theme:

- `tapa` in `themes/tapa/`

## Requirements

- Hugo extended `0.160.1` or compatible
- Git

Check local Hugo:

```bash
hugo version
```

## Daily Workflow

Create a new post:

```bash
./new-post "My New Post"
```

Preview locally:

```bash
HUGO_CACHEDIR=$(pwd)/.hugo_cache hugo server --bind 127.0.0.1 --port 1315 --disableFastRender
```

Build once:

```bash
hugo
```

Deploy:

```bash
./deploy "your message"
```

## Content

Posts live in `content/posts/`.

Filename convention:

```text
YYYY-MM-DD-post-title.md
```

Post URLs are generated from:

```toml
[permalinks]
posts = "/:year/:month/:day/:slug"
```

## Theme

The active theme is:

- `themes/tapa/`

`tapa` is derived from PaperMod and already includes the site-specific behavior that used to live in repo-level overrides.

Current site-level customizations inside `themes/tapa/` include:

- homepage intro-only front page
- compact `/posts/` archive with pagination
- `flows`-style `/thoughts/` page
- single-post typography and navigation adjustments
- local font loading for `LXGW WenKai`
- site accent palette and component-level color mapping

If you want to evolve the look and behavior of the site, start in:

- `themes/tapa/layouts/`
- `themes/tapa/assets/`
- `themes/tapa/theme.toml`

Typical theme work areas:

- page templates: `themes/tapa/layouts/`
- partials and shared page fragments: `themes/tapa/layouts/partials/`
- CSS and visual system: `themes/tapa/assets/css/`
- local fonts and static assets: `static/assets/`

## Change Log

See [CHANGELOG.md](./CHANGELOG.md) for the recent migration and UI changes.

## Deployment

Deployment is GitHub Pages via GitHub Actions.

Workflow file:

- `.github/workflows/hugo.yml`

Current deployment flow:

1. Push to `master`
2. GitHub Actions checks out the repo
3. GitHub Actions installs Hugo extended
4. GitHub Actions runs `hugo --gc --minify`
5. The generated `public/` directory is uploaded as the Pages artifact
6. GitHub Pages deploys the site

## Repository Structure

```text
.
├── .github/workflows/
├── archetypes/
├── content/
├── static/
├── themes/tapa/
├── config.toml
├── new-post
└── deploy
```
