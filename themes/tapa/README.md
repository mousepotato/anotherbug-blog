# Tapa

`Tapa` is a PaperMod-derived local theme for `anotherbug-blog`.

It starts from the current `themes/PaperMod` codebase, then folds in the site-specific overrides that are currently implemented at the repo level.

Current baked-in defaults in `Tapa`:

- home page uses the home-info header plus archive-style yearly listing
- home-info title is hidden when empty
- terms page capitalizes displayed taxonomy labels

Preview it without changing the active site theme:

```bash
HUGO_CACHEDIR=$(pwd)/.hugo_cache hugo --theme tapa
HUGO_CACHEDIR=$(pwd)/.hugo_cache hugo server --theme tapa
```

Recommended workflow:

1. Keep PaperMod as the active fallback
2. Evolve `themes/tapa/`
3. Switch the site only when `Tapa` is ready
4. Extract `themes/tapa/` into its own repo later if desired
