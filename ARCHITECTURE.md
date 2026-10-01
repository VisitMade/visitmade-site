# VisitMade architecture

This document describes the implementation in this repository at commit `0989dab` (the `main` baseline reviewed on 1 October 2026). It does not describe the architecture of the external VisitMade CRM or visitor demo.

## System boundary

This repository is a static marketing website. The browser downloads HTML, CSS, JavaScript, fonts and images. There is no server-side application, API, database or application persistence.

```text
Git push to main
  -> GitHub Actions (Node 22)
  -> node build.mjs
  -> dist/ static artifact
  -> GitHub Pages
  -> visitor browser
       -> Google Fonts
       -> optional links to external VisitMade demo
```

## Implemented architecture

### Front end

- `index.html` contains the entire page structure, product copy, illustrative UI and external demo links.
- `styles.css` defines the design tokens, component styles and responsive breakpoints.
- `script.js` implements the mobile menu, product tabs, hash synchronisation, Escape handling and current footer year.
- The site uses browser-native APIs and has no JavaScript framework, bundler or runtime dependency.
- `favicon.svg` and files in `assets/` are served unchanged.

### Build

`build.mjs` deletes `dist/`, recreates it, copies the four root web assets, and recursively copies `assets/`. The build performs no compilation, minification, hashing or content validation.

`package.json` exposes:

- `npm run check` — `node --check script.js` syntax validation only;
- `npm run build` — static file copy into `dist/`.

There is no lockfile because no packages are declared.

### Deployment and hosting

`.github/workflows/pages.yml` runs on pushes to `main` and manual dispatch. It:

1. checks out the repository;
2. installs Node 22;
3. runs the build;
4. configures GitHub Pages;
5. uploads `dist/`; and
6. deploys with GitHub's official Pages action.

The workflow has read-only repository contents access plus `pages: write` and `id-token: write`. The `pages` concurrency group cancels an older in-progress deployment when a newer one starts.

### External dependencies and integrations

- CSS imports `DM Sans` and `Manrope` from Google Fonts at page-render time.
- Links send users to `https://visit-crm.vercel.app/` and `/crm`; there is no API or data integration with that application.
- The source contains no analytics, enquiry form, cookie tooling or other third-party scripts.

### Configuration

There are no environment variables or runtime configuration files. Public URLs, copy, colour values and asset paths are hard-coded in source files.

### Storage and data model

There is no application storage or data model. Example organisations, membership totals and other figures are hard-coded illustrative content. `localStorage`, cookies and IndexedDB are not used.

### Authentication, authorisation and multi-tenancy

None is implemented. The marketing site is public and stateless. The copy refers to team access, roles, destination configuration and a demo sign-in, but those belong to the external application and must be documented in its owning repository.

### APIs and backend

None is implemented. GitHub Pages serves static files only.

### Security

The small static surface avoids application credentials and server-side data handling. External links that open a new tab use `rel="noopener"`. Deployment uses GitHub's OIDC token for Pages.

Current limitations include no repository-defined Content Security Policy or other HTTP security headers, a remote font dependency, and no automated dependency/security scan (there are no package dependencies). Any analytics or form addition would introduce privacy, consent, spam and data-handling requirements.

### Testing architecture

There is no test framework. Current automated validation is limited to JavaScript syntax and a successful static build. There are no HTML/CSS validators, broken-link checks, accessibility scans, browser tests, visual regression tests or deployment smoke tests.

## Planned architecture

No technical roadmap is committed in this repository. Product copy refers to a CRM, destination websites, memberships, permissions, external providers and connected data, but this repository contains no architectural evidence for them. Do not infer a database, framework, cloud platform, tenancy model or integration design.

If architecture documentation for the product platform is needed, create or update it in the repository that owns that implementation, then link to it here. Avoid duplicating details that will drift.

## Important decisions embodied by the code

- **Static delivery:** suitable for a content-led marketing site with minimal operational complexity.
- **No dependency installation:** keeps local and CI builds small and reproducible from the tracked sources and Node runtime.
- **Progressive native controls:** buttons, links and `<details>` provide the interaction foundation; JavaScript adds tab and menu behaviour.
- **Generated output excluded:** `dist/` is ignored and rebuilt rather than committed.
- **Illustrative product UI:** mock CRM/reporting data is HTML and CSS, not a connection to production or demo data.

## Known constraints and technical debt

- `index.html` and `styles.css` are large, compressed source files, which makes review and content maintenance harder.
- Product content and component markup are coupled in one HTML file.
- Hard-coded external URLs have no automated availability or correctness check.
- Runtime font loading depends on Google Fonts and network availability.
- The JavaScript assumes all expected DOM nodes exist; there is no defensive initialisation or test coverage.
- The build does not fail on broken internal links, missing assets or invalid HTML/CSS.
- The repository cannot substantiate the architecture or delivery status of the product it markets.
