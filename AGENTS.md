# AGENTS.md — Pixel Bootstrap UI Kit

## Project type

Static HTML/CSS/JS site. Bootstrap 5 UI Kit customized for 山西宏泽惠科技有限公司. No tests, no linter, no TypeScript.

## Commands

```bash
gulp              # Dev server (BrowserSync on .temp/, watches src/)
gulp build:dev    # Output unminified to html&css/
gulp build:dist   # Output minified to dist/
```

Requires global `gulp-cli`: `npm install gulp-cli -g`

## Template system

HTML uses `gulp-file-include`. Partials live in `src/partials/` and are included with:

```html
@@include('./_head.html', { "path": ".", "title": "Page Title" })
```

- `@@variable` placeholders are replaced from the JSON context passed to `@@include`
- `path` controls relative asset prefix (use `"."` for root, `".."` for pages in `html/pages/`)
- `environment` is set to `"development"` or `"production"` — use it for conditional includes
- Partials prefixed with `_` (e.g. `_head.html`, `_navigation.html`, `_footer.html`, `_scripts.html`)

## Source layout

```
src/
  index.html              # Root page (includes partials with path=".")
  html/pages/             # Subpages (include partials with path="../..")
  partials/               # Shared HTML fragments (_head, _nav, _footer, _scripts, components/)
  scss/pixel.scss         # Main SCSS entry (imports pixel/ and custom/)
  scss/custom/            # Site overrides — edit here, not pixel/
  scss/pixel/             # Upstream Pixel theme styles (prefer not to modify)
  assets/img/             # Images (company/, favicon/, etc.)
  assets/js/              # Vanilla JS
```

## Build artifacts (gitignored)

- `.temp/` — dev server output
- `html&css/` — `build:dev` output (note: directory name contains `&`)
- `dist/` — `build:dist` output
- `vendor/` — copied from `node_modules/` at build time via `gulp-npm-dist`

## Gotchas

- When adding a new page in `src/html/pages/`, set `"path": "../.."` in partial includes so vendor/css/image paths resolve correctly.
- SCSS changes go in `src/scss/custom/`, not `src/scss/pixel/` (upstream theme).
- Vendor JS/CSS is not hand-edited; it is copied from `node_modules/` on every build.
- The `html&css/` directory name contains a literal `&` — quote it in shell commands.
- Content is in Chinese (zh-CN). Keep UI copy consistent with existing tone.
