# VisitMade status

- **Snapshot:** 1 October 2026
- **Repository:** `VisitMade/visitmade-site` (the requested `DTosh44/visitmade` URL redirects here)
- **Reviewed baseline:** `main` at `0989dab`

## Overall state

The repository is a small, deployable static marketing-site prototype for VisitMade. It presents a coherent connected-platform proposition and links to a separate live demo, but it is not the VisitMade application codebase. Platform delivery status, data architecture and operational readiness cannot be determined from this repository.

## Working and completed

- Responsive single-page marketing site with hero, product areas, connected workflow, package overview, demos and FAQ.
- Mobile menu, keyboard-operable product tabs, hash deep links and dynamic footer year.
- Approved brand artwork and two illustrative destination images.
- Basic accessibility provisions: semantic structure, skip link, visible focus, reduced motion, keyboard controls and descriptive labels.
- Dependency-free Node build that produces `dist/`.
- GitHub Pages workflow on `main`; the latest recorded run succeeded and the public site returned HTTP 200 during this review.
- External visitor and CRM demo URLs both returned HTTP 200 during this review.

## Partial or unverified

- Product capability claims are public and detailed, but their implementation is outside this repository and has not been reconciled here against the owning application code.
- Accessibility has implementation support but no recorded audit, automated scan or screen-reader test.
- Responsive design is encoded for four viewport ranges but has no visual-regression coverage.
- Deployment is automated, but there is no post-deployment smoke test or custom-domain configuration in this repository.

## Outstanding

- Reconcile every published capability in `PRODUCT.md` with the application repository and an approved roadmap.
- Decide the desired conversion path: the current site offers demo exploration but no contact, booking or signup route.
- Add proportionate HTML/link/accessibility/browser validation.
- Decide whether Google-hosted fonts meet privacy, performance and resilience requirements.
- Establish owners for product copy, product scope and release/deployment verification.

## Known issues and technical debt

- The repository name and owner differ from the originally supplied GitHub path because that path redirects; references should use the canonical repository where practical.
- The previous README described Vercel deployment, while the implemented deployment is GitHub Pages. The documentation now follows the workflow.
- Large compressed HTML and CSS files are harder to review and maintain.
- No automated test suite exists; `npm run check` validates JavaScript syntax only.
- Hard-coded external links and assets are not checked by CI.
- No security headers or Content Security Policy are defined by this repository.
- The site cannot itself substantiate claims about CRM, permissions, multi-tenancy, billing, integrations or reporting data.

No reproducible functional bug was found in the repository during this documentation review.

## Deployment status

- **Configured host:** GitHub Pages
- **Trigger:** push to `main` or manual workflow dispatch
- **Build output:** `dist/`
- **Public URL:** <https://visitmade.github.io/visitmade-site/>
- **Last observed state:** successful workflow and HTTP 200 on 1 October 2026

This is an observed snapshot, not continuous monitoring.

## Testing status

- JavaScript syntax check: available
- Clean production build: available
- Unit/integration/end-to-end tests: absent
- HTML/CSS validation: absent
- Automated link checks: absent
- Automated accessibility checks: absent
- Visual regression/browser matrix: absent

## Unresolved decisions

1. Which repository and owner are authoritative for the actual platform's product and architecture status?
2. Which marketing claims are implemented now, approved next, merely proposed or intentionally deferred?
3. What is the platform MVP, and what is explicitly outside it?
4. Which sales/contact conversion should the marketing site support?
5. Which third-party integrations and geographic/localisation commitments are approved?
6. What evidence and review are required before a capability is described publicly?

## Immediate priorities

1. Reconcile `PRODUCT.md` against the application codebase and authorised product decisions; remove or qualify unsupported public claims.
2. Define the MVP and explicit non-goals to control scope.
3. Add a lightweight CI quality gate for build, internal links, HTML and accessibility.
4. Choose and implement an approved prospect conversion route if the site is intended to generate enquiries.
5. Improve source formatting only as a separate, behaviour-preserving maintenance task.

## Logical next development steps

After the product reconciliation, address only approved gaps. Keep application work in the repository that owns the application; keep this repository focused on the marketing site. Update this file in place whenever the current state materially changes rather than appending a diary.
