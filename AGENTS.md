# Repository instructions

These instructions apply to all work in this repository.

## Project documentation is the source of truth

Before making any significant change, read:

- `PRODUCT.md`
- `ARCHITECTURE.md`
- `DESIGN.md`
- `STATUS.md`
- any specialist documentation relevant to the task

Use `README.md` for repository orientation. If documentation and implementation disagree about current behaviour, verify the code and correct the documentation as part of the same work.

This repository currently owns the VisitMade marketing website, not the external CRM or visitor application. Do not infer platform implementation from marketing copy, illustrative UI or external links.

## Documentation updates are part of the definition of done

After any material piece of work:

- update `STATUS.md` if the current project state, validation, deployment status, known issues, decisions or immediate priorities changed;
- update `PRODUCT.md` if functionality, requirements, audience, scope or approval status changed;
- update `ARCHITECTURE.md` if technical architecture, infrastructure, integrations, security posture or implementation approach changed;
- update `DESIGN.md` if UX, UI, accessibility, content or design-system decisions changed; and
- update relevant specialist documentation where applicable.

Do not update documentation merely to record trivial implementation details. Documentation changes must ship with the material change they describe.

## Scope control

Before implementing functionality that materially expands the product beyond `PRODUCT.md`:

1. identify it as a potential scope expansion;
2. check whether it belongs in the current product or an approved MVP;
3. classify it as current, planned/approved, proposed, or deferred/out of scope; and
4. obtain a product decision when the classification is not supported by repository evidence.

Never turn brainstorming, marketing illustrations or possible integrations into committed scope silently. Implement application functionality in the repository that owns that application unless an explicit architectural decision changes this boundary.

## Status maintenance

`STATUS.md` must remain concise and current. It is a snapshot, not a development diary or changelog.

- Update or remove stale statements in existing sections.
- Record only current risks, decisions, priorities and delivery state.
- Use version control for history.
- Date externally observed deployment or availability checks because they can become stale.

## Accuracy and evidence

- Describe implemented functionality only when it exists in the repository being documented or is backed by a named authoritative source.
- Label planned, proposed, illustrative, external and unverified functionality explicitly.
- Prefer actual code and configuration for current technical behaviour.
- If another repository owns a capability, link to its authoritative documentation rather than duplicating details that can drift.
- Do not claim customer results, live integrations, automated data collection, pricing, security/compliance certification or accessibility conformance without evidence.
- Preserve useful historical context, but do not present it as current state.

## Repository safeguards

- Keep tasks documentation-only when requested; do not change application behaviour, deployment configuration, database behaviour or infrastructure as a side effect.
- Treat `dist/` as generated output; edit source files and rebuild it for validation.
- Run `npm run check` and `npm run build` for changes that could affect the site or its build.
- Validate affected internal links and external URLs when documentation or navigation changes.
- Maintain keyboard support, visible focus, semantic structure and reduced-motion behaviour for UI changes.

## Specialist documentation

Create a specialist document only when it has a clear owner and reduces complexity without duplicating these core files. CRM, visitor-site, multi-tenancy, permissions, data-model and publishing-workflow documentation belongs with the implementation that can substantiate it. If such implementation later moves into this repository, add focused documents under `docs/` and link them from `README.md`, `PRODUCT.md` and `ARCHITECTURE.md` as appropriate.
