# Changelog

## 2026-04-09

### Theme migration

- switched the site to the local `themes/tapa/` theme
- removed old `PaperMod` / `mogege-local` theme wiring from active use
- moved site-specific layout behavior into the local theme instead of repo-level overrides

### Home and navigation

- changed `/` to show only the home intro block
- added `/posts/` as the main archive-style entry point for articles
- reordered the main nav so `Posts` appears before `Tags`
- hid `/main/` from navigation while keeping the page itself available

### Posts page

- rebuilt `/posts/` as a compact paginated list
- grouped post listings by year
- showed full `yyyy-mm-dd` dates beside titles
- removed the large `Posts` page heading and breadcrumb
- simplified pagination labels and layout
- stabilized pagination positioning across pages with different heights

### Thoughts page

- rebuilt `/thoughts/` to follow the `hutusi.com/flows` editorial layout more closely
- added timeline-style thought entries with date anchors
- parsed inline thought tags and generated a sidebar tag section
- added a calendar-based sidebar and month-based browse list with counts
- widened and rebalanced the thoughts layout multiple times for readability
- removed extra thoughts-page header clutter
- aligned tag styling with the `/tags/` page style

### Post detail pages

- reduced single post title size aggressively
- removed single-post breadcrumbs
- toned down post meta so it does not dominate reading
- simplified previous/next post navigation
- improved long-form reading typography by reducing body heading scale
- hid leading horizontal rules at the top of article content
- added clearer accent separation on post detail pages:
  purple for headings, teal for links/code, warm orange for quotes and footer navigation

### Content cleanup

- added and tagged thoughts entries in `content/thoughts.md`
- changed the `Source code is a liability, not an asset!` thought tag from `Tech` to `Programming`
- removed duplicated first-body title headings from `章鱼花园 Vol` posts
- reduced `章鱼花园 Vol` subscription sections to Substack only

### Typography and color

- switched Chinese text rendering to local `LXGW WenKai`
- kept code and Latin-heavy UI on a Monaco-centered monospace stack
- introduced separated purple / teal / warm orange accents by component instead of blended gradients
- changed selection highlight from purple to warm orange

### Footer

- changed footer copy from `Powered by Hugo & Tapa` to `Powered by Hugo & Tapa (in development)`

### Local build notes

- main preview command:

```bash
HUGO_CACHEDIR=$(pwd)/.hugo_cache hugo server --bind 127.0.0.1 --port 1315 --disableFastRender
```

- one-off build check:

```bash
hugo --destination /tmp/anotherbug-check
```
