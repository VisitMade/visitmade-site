# VisitMade product

This document is the product source of truth for this repository. It separates verified repository behaviour from product messaging and unapproved possibilities so that marketing copy does not silently become committed scope.

## Evidence and scope boundary

The repository contains only the VisitMade marketing website. It does not contain the linked visitor site or CRM application. Consequently:

- **Implemented here** means observable in this repository's marketing site.
- **Published product proposition** means a capability is stated in the live marketing copy, but its implementation is outside this repository and is not verified here.
- **Planned/approved** requires roadmap, specification or implementation evidence. None is currently stored here.
- **Proposed** means the repository mentions a possibility without enough evidence that it is approved.

The previous README said its copy was based on the separate `DTosh44/visit-crm` README and features inspected on 22 September 2026. That is useful provenance, not continuing proof of implementation. Before changing capability status, check the owning application repository and record the evidence here.

## Vision

Give destination teams one connected way to present their place to visitors and manage the relationships, membership, content and information behind that visitor experience.

## Problem

The proposition addresses two related problems:

1. Visitors need a useful, inspiring way to discover a destination's places, events and trip ideas.
2. Destination teams otherwise manage businesses, contacts, memberships, content, billing and reporting across disconnected systems and repeated data entry.

The intended differentiator is the relationship between the public visitor experience and the operational workspace: one business record can support relationship management, membership administration and a published visitor listing.

## Target customers and users

### Customers

- Destination-management and destination-marketing organisations
- Small local tourism teams
- Wider destination partnerships
- Destinations operating in the UK or internationally, including the US

No narrower segment, buyer persona, pricing model or procurement model is evidenced in this repository. Those require product decisions.

### User types

| User | Need described by current copy | Evidence status |
| --- | --- | --- |
| Visitor | Discover places, stays, food, events and trip ideas | Published proposition; external implementation not verified here |
| Destination team member | Manage organisations, contacts, tasks, content and reporting | Published proposition; external implementation not verified here |
| Membership or relationship manager | Manage pipeline, membership, benefits, renewals, invoices and agreements | Published proposition; external implementation not verified here |
| Content editor | Edit listings and curated content; review submitted events | Published proposition; external implementation not verified here |
| Event organiser | Submit an event for review | Mentioned in copy; workflow and permissions require verification |
| Administrator | Configure brand, membership structure, team access and modules | Mentioned in copy; exact role and controls require verification |

## Core product proposition

“One connected platform” combining a destination-branded visitor website with a team workspace for CRM, membership, publishing and reporting. External services and destination-specific setup are configured separately.

## A. Core/current scope

### Verified in this repository

The current deliverable is a public, single-page VisitMade marketing site. It:

- explains the connected-platform proposition;
- presents sections for destination websites, CRM/membership and reporting/insights;
- illustrates a fictional Visit Valechester website and workspace with clearly labelled demonstration data;
- links to an external visitor demo and CRM demo;
- answers high-level product questions;
- supports responsive navigation, keyboard-operated product tabs and FAQ disclosures; and
- is built and deployed as a static site.

The marketing site has no lead form, analytics, pricing, testimonials, customer results or compliance certification.

### Published product areas, not verified in this repository

These are current public claims and therefore approved **messaging**, but this repository cannot establish their delivery state:

1. **Destination website** — branded sites, searchable listings, maps, filters, saved places, guides, itineraries, trails, booking links, offers and enquiries.
2. **CRM and membership** — organisations, multiple contacts, sales pipeline, follow-ups, shared tasks, membership levels, benefits and benefit usage.
3. **Content and events** — listings and curated content, plus event submission, review and publication.
4. **Billing and agreements** — invoices, payment status, renewals and agreement progress.
5. **Reporting and insights** — configurable dashboard widgets; membership, pipeline and billing summaries; supplied visitor-economy and social figures; themes recorded against listings.
6. **Team workspace** — shared tasks, website enquiries, user roles and configurable modules.
7. **Connected records** — movement from a business relationship and membership record to a visitor listing without re-entering the same context.

Before treating any item above as implemented product scope, verify it in the application repository and identify limitations, roles and tenancy behaviour.

## Important journeys

### Implemented marketing journey

1. A prospective customer lands on the VisitMade site.
2. They learn the proposition and switch among website, CRM and reporting explanations.
3. They review the connected-record story, package overview and FAQ.
4. They open the external Visit Valechester visitor or CRM demo.

The journey currently stops at exploration. There is no contact, booking, signup or purchase conversion in this repository.

### Product journeys described by the proposition

These journeys are directionally described, but their implementation details are unverified here:

- A visitor discovers and filters listings, saves places and uses curated trip content.
- An organiser submits an event; a team member reviews and publishes it.
- A team member develops an organisation from prospect through membership and follow-up.
- A team member maintains a member's benefits, renewal, invoice, payment and agreement status.
- A content editor uses business context to publish a visitor-facing listing.
- A team member arranges dashboard widgets and reviews operational and supplied external figures.

## B. Planned/approved functionality

No roadmap, backlog, product specification or approval record exists in this repository. Do not place an item in this section solely because it appears in marketing copy or an illustrative mock-up.

The next product-documentation action is to reconcile the published claims above against the application repository and an authorised roadmap. Record only confirmed gaps as planned work.

## C. Ideas/proposals requiring a product decision

The site says that accounting, banking, email and AI services may be configured separately. It does not identify providers, use cases, integration depth, delivery state or approval. Each is therefore a proposal requiring a product decision, not committed scope.

The following also require explicit decisions because the repository provides no authoritative answer:

- sales/contact or demo-booking conversion;
- pricing and packaging;
- analytics and consent management;
- exact customer onboarding and destination provisioning;
- supported languages, currencies, locales and regions;
- third-party booking, mapping, social, accounting, banking and email providers;
- native mobile applications;
- self-service visitor or member accounts;
- data import/export and migration commitments; and
- service levels, support model and compliance claims.

## D. Deferred or out of scope

No core-platform functionality is explicitly recorded as deferred or out of scope. That absence is itself a scope-control risk and requires a product decision.

For this **marketing-site repository**, the following are outside the current implementation unless separately approved:

- implementing the CRM, visitor application, APIs, database, authentication or integrations here;
- presenting illustrative figures as customer results;
- claiming live integrations, automated data collection, pricing or compliance certification without evidence; and
- inventing a sales destination or collecting enquiries before an approved contact route and data-handling approach exist.

## MVP and scope-control boundary

The repository does not define a platform MVP. Until one is approved, the safest boundary is:

- preserve the connected visitor-site + operational-workspace proposition;
- treat public capability copy as claims that need evidence, not as a backlog;
- require an owner and acceptance criteria before promoting a proposal to planned scope; and
- keep destination-specific customisation distinct from generally supported platform functionality.

Any material expansion beyond this document must first be identified as a potential scope change and classified as current, approved/planned, proposed or deferred/out of scope.
