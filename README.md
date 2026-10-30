# Filevine

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Filevine is the leading legal case management and operating intelligence platform for plaintiff, personal-injury, mass-tort, family, immigration, criminal-defense, estate-planning, and government legal teams. The platform combines a customizable matter / project system with intake (Lead Docket), documents (Docs+), eSignature (Vinesign), contract management (Outlaw), deadline calendaring, time and billing, a secure client portal, and the LOIS Legal Operating Intelligence System for AI-assisted drafting, deposition prep, and case analysis. Filevine exposes a public REST API v2 with US and Canada gateways, PAT-based OAuth bearer authentication, and webhook subscriptions for event-driven integrations.

**Areas:** Legal · Case Management · Matter · Intake · Documents · LOIS · Webhook · Legal AI · Personal Injury · Mass Torts

## Filevine on APIs.io

Everything profiled for Filevine is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/filevine/](https://apis.io/providers/filevine/)** — or go straight to one of the APIs or properties below.

### APIs (9)

- [Filevine Identity API](https://apis.io/apis/filevine/filevine-identity-api/) — Exchange a Filevine Personal Access Token (PAT) for a short-lived bearer access token used to call the Filevine API Gateway. Tokens are issued at…
- [Filevine Projects API](https://apis.io/apis/filevine/filevine-projects-api/) — List, create, read, and update Filevine projects (matters/cases). Each project belongs to a project type, carries a primary client contact, has a phase, and…
- [Filevine Contacts API](https://apis.io/apis/filevine/filevine-contacts-api/) — Manage the global Filevine contact list and project-scoped contact attachments. Contacts represent clients, opposing parties, witnesses, experts, and…
- [Filevine Documents API](https://apis.io/apis/filevine/filevine-documents-api/) — Upload, list, and read documents attached to Filevine projects. Documents support folders, tags, versioning, locking, and optional sharing to the secure…
- [Filevine Notes API](https://apis.io/apis/filevine/filevine-notes-api/) — Append, edit, and read project notes and activity items. Notes carry a typed kind (note, task, portal message, phone call, text) and support @mentions,…
- [Filevine Deadlines API](https://apis.io/apis/filevine/filevine-deadlines-api/) — Manage the date-driven legal milestones on a project — statutes of limitations, court dates, response deadlines — with assignees and reminder notifications.…
- [Filevine Tasks API](https://apis.io/apis/filevine/filevine-tasks-api/) — List, create, and update assignable to-do items on a project with status, priority, due dates, and completion tracking. Tasks are produced by workflow…
- [Filevine Webhooks API](https://apis.io/apis/filevine/filevine-webhooks-api/) — Manage organization webhook subscriptions and receive event callbacks (project.created, project.updated, document.uploaded, note.created, deadline.created,…
- [Filevine Time Entries API](https://apis.io/apis/filevine/filevine-time-entries-api/) — Billable time tracking.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### AsyncAPI (1)

Event-driven and webhook contracts.

- [Filevine Webhook Events](https://apis.io/asyncapis/filevine/filevine-events-asyncapi/)

#### Event channels (8)

Individual events and webhooks the provider emits.

- [deadline.created](https://apis.io/channels/filevine/deadline-created/)
- [document.uploaded](https://apis.io/channels/filevine/document-uploaded/)
- [note.created](https://apis.io/channels/filevine/note-created/)
- [payment.created](https://apis.io/channels/filevine/payment-created/)
- [payment.updated](https://apis.io/channels/filevine/payment-updated/)
- [project.created](https://apis.io/channels/filevine/project-created/)
- [project.updated](https://apis.io/channels/filevine/project-updated/)
- [task.completed](https://apis.io/channels/filevine/task-completed/)

#### GraphQL (1)

GraphQL schemas.

- [Moved to /providers/filevine/](https://apis.io/graphqls/filevine/filevine-graphql/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Filevine Agentic Access](https://apis.io/agentic-access/filevine/filevine-agentic-access/)

#### JSON Schema (3)

The data models the API reads and writes.

- [Filevine Contact](https://apis.io/schemas/filevine/filevine-contact/)
- [Filevine Document](https://apis.io/schemas/filevine/filevine-document/)
- [Filevine Project](https://apis.io/schemas/filevine/filevine-project/)

#### JSON Structure (1)

Data models expressed in JSON Structure.

- [Filevine Project Structure](https://apis.io/json-structure/filevine/filevine-project-structure/)

#### JSON-LD (1)

Linked-data contexts for the provider's vocabulary.

- [Filevine Context](https://apis.io/jsonld/filevine/filevine-context/)

#### Vocabulary (1)

The provider's domain terms, defined.

- [Filevine Vocabulary](https://apis.io/vocabularies/filevine/filevine-vocabulary/)

#### Examples (3)

Example requests and responses.

- [Filevine Create Deadline Example](https://apis.io/examples/filevine/filevine-create-deadline-example/)
- [Filevine Create Note Example](https://apis.io/examples/filevine/filevine-create-note-example/)
- [Filevine Create Project Example](https://apis.io/examples/filevine/filevine-create-project-example/)

#### Collections (19)

Postman and Open Collection request collections.

- [Filevine Contacts API](https://apis.io/collections/filevine/open-filevine-contacts-api/)
- [Filevine Contacts Deadlines API](https://apis.io/collections/filevine/open-filevine-deadlines-api/)
- [Filevine Contacts Documents API](https://apis.io/collections/filevine/open-filevine-documents-api/)
- [Filevine Contacts Identity API](https://apis.io/collections/filevine/open-filevine-identity-api/)
- [Filevine Contacts Notes API](https://apis.io/collections/filevine/open-filevine-notes-api/)
- [Filevine Contacts Projects API](https://apis.io/collections/filevine/open-filevine-projects-api/)
- [Filevine Contacts Tasks API](https://apis.io/collections/filevine/open-filevine-tasks-api/)
- [Filevine Time Entries API](https://apis.io/collections/filevine/open-filevine-time-entries-api/)
- [Filevine Contacts TimeEntries API](https://apis.io/collections/filevine/open-filevine-timeentries-api/)
- [Filevine Contacts Webhooks API](https://apis.io/collections/filevine/open-filevine-webhooks-api/)
- [Filevine Contacts API](https://apis.io/collections/filevine/postman-filevine-contacts-api/)
- [Filevine Contacts Deadlines API](https://apis.io/collections/filevine/postman-filevine-deadlines-api/)
- [Filevine Contacts Documents API](https://apis.io/collections/filevine/postman-filevine-documents-api/)
- [Filevine Contacts Identity API](https://apis.io/collections/filevine/postman-filevine-identity-api/)
- [Filevine Contacts Notes API](https://apis.io/collections/filevine/postman-filevine-notes-api/)
- [Filevine Contacts Projects API](https://apis.io/collections/filevine/postman-filevine-projects-api/)
- [Filevine Contacts Tasks API](https://apis.io/collections/filevine/postman-filevine-tasks-api/)
- [Filevine Contacts TimeEntries API](https://apis.io/collections/filevine/postman-filevine-timeentries-api/)
- [Filevine Contacts Webhooks API](https://apis.io/collections/filevine/postman-filevine-webhooks-api/)

#### Governance rules (3)

Spectral rulesets for the provider's contracts.

- [Filevine — asyncapi rules](https://apis.io/rules/filevine/filevine-asyncapi-spectral-rules/)
- [Filevine — jsonschema rules](https://apis.io/rules/filevine/filevine-jsonschema-spectral-rules/)
- [Filevine API Rules](https://apis.io/rules/filevine/filevine-rules/)

#### Security (4)

Authentication, trust centre, and vulnerability disclosure.

- [Filevine Authentication](https://apis.io/security/filevine/filevine-authentication/)
- [Filevine Domain Security](https://apis.io/security/filevine/filevine-domain-security/)
- [Filevine Trust Center](https://apis.io/security/filevine/filevine-trust-center/)
- [Filevine Vulnerability Disclosure](https://apis.io/security/filevine/filevine-vulnerability-disclosure/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Filevine Plans Pricing](https://apis.io/plans/filevine/filevine-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Filevine Rate Limits](https://apis.io/rate-limits/filevine/filevine-rate-limits/)

#### FinOps (1)

What the API costs to run, by operation.

- [Filevine Finops](https://apis.io/finops/filevine/filevine-finops/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.filevine.com/)
- [Documentation](https://developer.filevine.io/)
- [Pricing](https://www.filevine.com/pricing/)
- [Support](https://support.filevine.com/)
- [Blog](https://www.filevine.com/blog/)
- [Trust centre](https://trust.paramify.com/filevine)
- [Terms of service](https://www.filevine.com/subscription-agreement/)
- [Privacy policy](https://www.filevine.com/privacy-policy/)
- [GitHub](https://github.com/Filevine)
- [Status](https://support.filevine.com/hc/en-us/articles/8671232852507-Status-Page)

## API Evangelist rating

**Kin Score 52.1** — developing · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 57.1 |
| Contract quality | 66.9 |
| Contract governance | 27.3 |
| Operational transparency | 39.5 |
| Developer ergonomics | 39.3 |
| Access clarity | 55.3 |

**Agent readiness 22.9** — agent-aware

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | — |
| MCP Server | — |
| Auth Clarity | bearer (partial credit) |
| Idempotency | — |
| Error Semantics | — |
| OpenAPI Examples | documented (partial credit) |
| Rate Limit Signal | derived (partial credit) |
| Event Surface Described | derived (partial credit) |
| Agent Skills | — |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | partial |
| Operation Distinctiveness | distinct |

**Regulatory alignment 35.3** — Horizontal (data, software, accessibility, platform)

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/filevine/](https://apis.io/providers/filevine/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Filevine: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/filevine/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
