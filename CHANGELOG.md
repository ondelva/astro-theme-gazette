# Changelog

All notable changes to this project are documented here. Format: [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).

## [1.1.0] - 2026-09-21

### Added

- Umami as an analytics provider, next to Plausible and GA4. `analytics.host` points a self-hosted
  Plausible or Umami at your own origin; leave it empty for the hosted service. The default is
  still `provider: null`, and a build with nothing set loads no third-party script.
- One-click deploy buttons for Cloudflare, Netlify and Vercel in the README and in
  `docs/deploy.md`, with the `SITE_URL` step that follows them.

### Fixed

- The screenshots in `docs/screenshots/` were taken before the webfonts loaded, so they showed
  the system fallbacks rather than the faces the theme ships. All of them are new.
- The webfonts were never loaded. `astro.config.mjs` extracted the woff2 files but no `<Font>` put
  them in the `<head>`, and `tokens.css` redeclared the three font variables as system stacks on
  top of what the font component sets. Both are fixed, and Archivo 400/500 are preloaded so the
  swap no longer shifts the page. Until now the cover fell back to Didot on macOS and Georgia
  elsewhere.
- `docs/deploy.md` described the Pro edition: a private repository that cannot be forked, and a zip
  with no Git history. This edition is public, so the section now covers the three routes that
  apply to it. The `pro-only` marker on `Analytics.astro` is gone as well.

## [1.0.1] - 2026-09-21

### Added

- A purchase link for Gazette Pro in the README, next to the demos and in the Free vs Pro section.

## [1.0.0] - 2026-09-21

First public release. The demo is live and the screenshots are in `docs/screenshots/`.

### Added

- A live demo at https://gazette-free.ondelva.com, and the Pro demo at https://gazette.ondelva.com.
- Screenshots of the cover, an issue and a piece, light and dark, desktop and mobile.

### Fixed

- The header stacked a single control on a ragged line of its own below 640px. The links and the
  controls now wrap as one group, flush left under the nameplate.
- Issue rows put the piece count and the date at the right edge of a narrow screen. They now sit
  flush left under the cover line.
- On the masthead, a contributor's piece count stopped short of the rule it sits on.

## [0.9.1] - 2026-09-21

### Fixed

- CI could not start: `actions/setup-node@v5` looks for pnpm before the step that installs it.
  The workflow now uses `actions/checkout@v7`, `actions/setup-node@v7` and
  `actions/upload-artifact@v7`.

## [0.9.0] - 2026-09-21

First snapshot. The theme is complete; the live demo and the screenshots follow in 1.0.0.

### Added

- The cover home page, the issue page, the piece, the archive, the masthead, 404.
- Leader contents rows: the hanging number, the dotted leader, the byline.
- Dark mode, the drop cap, the pull-quote epigraph, the folio.
- The feed, the sitemap, `robots.txt`, and an analytics slot (Plausible, GA4).
- `docs/customization.md`, `docs/content.md`, `docs/deploy.md`, and `AGENTS.md`.
