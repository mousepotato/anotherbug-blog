# anotherbug-blog-hugo

Source repo for `https://anotherbug.com`.

This is a Hugo-based blog. Content lives in this repository, and GitHub Actions builds and publishes the site to GitHub Pages.

## Requirements

- Hugo extended `0.160.1` or compatible
- Git

Local check:

```bash
hugo version
```

## Daily Workflow

Create a new post:

```bash
./new-post "My New Post"
```

Edit the generated file under `content/posts/`.

Preview locally:

```bash
hugo server
```

Deploy:

```bash
./deploy "add new post"
```

`deploy` commits the source repo and pushes to `master`. GitHub Actions then builds and publishes the site.

## Writing Posts

Posts live in `content/posts/`.

This repo uses the filename convention:

```text
YYYY-MM-DD-post-title.md
```

Example:

```text
content/posts/2026-04-08-my-new-post.md
```

The `./new-post` helper:

- prefixes today’s date
- slugifies the title
- runs `hugo new`

Generated front matter follows the archetype in `archetypes/default.md`.

Typical post front matter:

```md
---
title: "My New Post"
date: 2026-04-08T10:00:00-10:00
draft: false
hidedate: true
tags: ["tag1"]
categories: ["Technique"]
featured_image:
description:
---
```

Notes:

- URLs are generated from `[permalinks]` in `config.toml`
- post URLs look like `/YYYY/MM/DD/slug/`
- `date = [":filename", ":default"]` means Hugo can derive the date from the filename
- this repo has `draft: false` by default in the archetype

## Local Development

Run the local server:

```bash
hugo server
```

Useful variants:

```bash
hugo
hugo --gc --minify
```

If Hugo complains about cache permissions in a restricted environment, use:

```bash
hugo --gc --minify --cacheDir /tmp/hugo_cache_anotherbug
```

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

Manual deploy command:

```bash
./deploy "your message"
```

The script currently does:

```bash
git add .
git commit -m "your message"
git push origin master
```

There is no second deploy repo anymore. The old `mousepotato.github.io` repo is no longer part of the publish path.

## Repository Structure

Top-level layout:

```text
.
├── .github/workflows/     # GitHub Actions deploy workflow
├── archetypes/            # Hugo content templates
├── content/               # Site content
├── data/                  # Hugo data files
├── layouts/               # Site-specific layout overrides
├── static/                # Static assets copied as-is
├── themes/mogege-local/   # Active theme, vendored into this repo
├── config.toml            # Hugo site configuration
├── new-post               # Helper script to create a dated post
└── deploy                 # Commit and push helper
```

Content layout:

- `content/posts/`: blog posts
- `content/about.md`: about page
- `content/archives.md`: archives page
- `content/tools.md`: uses/tools page
- `content/thoughts.md`: thoughts page
- `content/main/`: academic/personal site pages and assets

Static assets:

- `static/assets/images/`: images and icons used by the site
- `static/CNAME`: legacy Pages domain file; kept in the repo, but the GitHub Pages custom domain is now configured in GitHub repository settings

Theme:

- active theme is `themes/mogege-local`
- configured in `config.toml` with `theme = "mogege-local"`
- this theme was vendored into the repo so GitHub Actions can build without a submodule dependency

## Configuration

Main config file:

- `config.toml`

Important settings:

- `baseURL = "https://anotherbug.com"`
- `theme = "mogege-local"`
- `languageCode = "zh-cn"`
- `DefaultContentLanguage = "zh-cn"`
- `paginate = 15`
- `enableEmoji = true`
- `enableRobotsTXT = true`

Markup:

- Goldmark raw HTML is enabled
- this preserves older posts that contain inline raw HTML

Permalinks:

```toml
[permalinks]
posts = "/:year/:month/:day/:slug"
```

This means a file like:

```text
content/posts/2026-04-08-my-new-post.md
```

publishes to:

```text
/2026/04/08/my-new-post/
```

Menus:

Configured in `config.toml` under `[menu]`:

- Blog
- Categories
- Tags
- Thoughts
- Uses
- About
- Academics

Comments:

- Gitalk is enabled in `[params.gitalk]`
- comment issues are stored in `mousepotato.github.io`

Analytics:

- Google Analytics is configured in `config.toml`

## Theme and Layout Notes

The repo uses a vendored theme:

- `themes/mogege-local`

That theme contains:

- `layouts/`: templates
- `assets/css/`: SCSS
- `assets/js/`: JavaScript

If you need to change how the site looks, start in:

- `themes/mogege-local/layouts/`
- `themes/mogege-local/assets/css/`
- `themes/mogege-local/assets/js/`

If you need a repo-specific override instead of editing the theme directly, you can add files under the root `layouts/` directory.

## GitHub Pages Configuration

The GitHub repository should be configured as:

- Pages source: `GitHub Actions`
- Custom domain: `anotherbug.com`

Operational note:

- for this custom workflow, the custom domain is managed in GitHub repository settings
- `static/CNAME` is not the source of truth for deployment configuration

## Troubleshooting

### New post command fails

Check that Hugo is installed:

```bash
hugo version
```

### Local build fails

Try:

```bash
hugo --gc --minify --cacheDir /tmp/hugo_cache_anotherbug
```

### Site does not update after push

Check:

1. the push reached `master`
2. the `Deploy Hugo Site` workflow ran
3. the build job succeeded
4. the deploy job succeeded

### Custom domain shows 404

Usually one of:

- GitHub Pages deployment has not completed yet
- the custom domain is attached to the wrong repo
- DNS is not pointed correctly

### Git index lock error

If Git reports a stale `.git/index.lock`, make sure no git command is still running before removing it manually.

## Current Publish Contract

The intended current workflow is:

```bash
./new-post "Post Title"
# edit content/posts/YYYY-MM-DD-post-title.md
hugo server
./deploy "publish post"
```

That is the whole publish path.
