# VisitMade

VisitMade is presented as a connected platform for destination teams: a visitor-facing destination website alongside CRM, membership, content, events, billing and reporting tools. This repository contains the public VisitMade **marketing website**, not the application that implements those operational capabilities.

The site explains the proposition, illustrates the visitor and team experiences, and links to the external Visit Valechester product demo. Its intended audience ranges from small tourism teams to wider destination partnerships.

## What is in this repository

- A single-page, responsive marketing site in `index.html`
- Styling and responsive design in `styles.css`
- Navigation and accessible product-tab behaviour in `script.js`
- Brand and demonstration imagery in `assets/`
- A dependency-free Node build script that copies deployable files into `dist/`
- A GitHub Actions workflow that deploys `main` to GitHub Pages

There is no application backend, database, authentication, multi-tenancy implementation or CRM source code in this repository. Product capabilities described by the marketing site are classified in [PRODUCT.md](PRODUCT.md); do not infer their implementation from the marketing copy alone.

## Technology

- Semantic HTML5
- Plain CSS with responsive breakpoints
- Browser-native JavaScript (ES modules are not required by the page)
- Node.js for the build and JavaScript syntax check; CI uses Node 22
- GitHub Actions and GitHub Pages for deployment
- Google Fonts (`DM Sans` and `Manrope`) loaded by the browser

## Local development

Prerequisite: Node.js 22 is the CI reference version. No package installation is required because the repository has no runtime or development dependencies.

```sh
npm run check
npm run build
cd dist
python3 -m http.server 8000
```

Open <http://localhost:8000>. Edit the source files at the repository root, not generated files in `dist/`; the build removes and recreates `dist/`.

## Testing

```sh
npm run check  # JavaScript syntax only
npm run build  # clean production build
```

There is currently no automated unit, integration, end-to-end, accessibility or visual-regression suite. See [STATUS.md](STATUS.md) for the current validation posture and recommended priorities.

## Deployment

Pushes to `main` run [`.github/workflows/pages.yml`](.github/workflows/pages.yml), build `dist/`, and deploy it to GitHub Pages. The public site is <https://visitmade.github.io/visitmade-site/>. GitHub Pages is the only deployment configured in this repository; any other host would need equivalent `npm run build` and `dist/` settings.

## Project documentation

- [PRODUCT.md](PRODUCT.md) — product vision, scope and evidence-based capability classification
- [ARCHITECTURE.md](ARCHITECTURE.md) — the implementation that actually exists in this repository
- [DESIGN.md](DESIGN.md) — current UX, visual and accessibility conventions
- [STATUS.md](STATUS.md) — concise, current project state and priorities
- [AGENTS.md](AGENTS.md) — permanent working rules for developers and AI agents
