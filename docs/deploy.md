# Deploy

Gazette builds to a static site in `dist/`. There is no server runtime, no database and no
environment variable you have to set at runtime.

## Before you deploy

Set `site.url` in `src/config.ts` to your production URL. Canonical links, the feed, the sitemap
and `robots.txt` all print absolute URLs from it.

## Requirements

- Node.js 22.12 or newer (`.nvmrc` says `22`).
- pnpm. `package.json` pins the exact version in `packageManager`; pnpm 10+ and Corepack switch to
  it on their own. To install that version yourself:

```sh
npm i -g "$(node -p "require('./package.json').packageManager.split('+')[0]")"
```

## Build

```sh
pnpm install
pnpm build
```

Output goes to `dist/`. `pnpm preview` serves it locally, which is the closest thing to what your
host will serve.

`SITE_URL` overrides `site.url` at build time, which is useful for a staging deploy:
`SITE_URL=https://staging.example.com pnpm build`.

## Your own repository

Hosts build from a Git repository you own. The Pro repository is private and cannot be forked, and
the zip carries no Git history, so push your own copy first.

If you cloned from GitHub, keep the theme repository as `upstream` so you can pull later releases:

```sh
git remote rename origin upstream
git remote add origin https://github.com/<you>/<your-site>.git
git push -u origin main
```

If you started from the zip:

```sh
git init -b main
git add -A
git commit -m "Start from Gazette Pro"
git remote add origin https://github.com/<you>/<your-site>.git
git push -u origin main
```

Then connect that repository to a host. The defaults are right; you only confirm the build
settings.

## Cloudflare Workers / Pages

Build command `pnpm build`, output directory `dist`.

## Vercel

Framework preset Astro, build command `pnpm build`, output directory `dist`.

## Netlify

Build command `pnpm build`, publish directory `dist`.

## GitHub Pages

Works, with one thing to watch: a project site is served from `/<repo>/`, so set `base: '/<repo>/'`
in `astro.config.mjs` as well as `site.url`. A custom domain or a `<user>.github.io` repository
needs neither.

## CI

`.github/workflows/ci.yml` runs on every push to `main` and on every pull request: install,
`pnpm check`, `pnpm lint`, `pnpm check:contrast`, `pnpm build`, a Lighthouse run against the built
site, and an internal link check. The Lighthouse pages and thresholds are in `lighthouserc.json`.

You do not need it to deploy, but it is the list of things worth verifying before you ship, and it
is what the theme itself is held to.
