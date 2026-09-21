# Changelog

All notable changes to this project are documented here. Format: [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).

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
