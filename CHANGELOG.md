# Changelog

All notable changes to this project are documented here. Format: [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).

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
