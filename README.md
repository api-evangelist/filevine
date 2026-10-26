# Filevine (filevine)

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

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/filevine/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/filevine/refs/heads/main/apis.yml)

## Scope

- **Position:** Provider
- **Access:** 3rd-Party

## Tags

- Legal
- Case Management
- Matters
- Intake
- Documents
- LOIS
- Webhooks
- Legal AI
- Personal Injury
- Mass Torts

## Timestamps

- **Created:** 2026-05-25
- **Modified:** 2026-05-25

## APIs

### Filevine Identity API

Exchange a Filevine Personal Access Token (PAT) for a short-lived bearer access token used to call the Filevine API Gateway. Tokens are issued at https://identity.filevine.io/connect/token with grant_type personal_access_token, the PAT, and a requested scope set. Tokens are typically valid for ~20 minutes.

- **Human URL:** [https://support.filevine.com/hc/en-us/articles/27944810461851-Authenticate-Requests-to-the-API-Gateway](https://support.filevine.com/hc/en-us/articles/27944810461851-Authenticate-Requests-to-the-API-Gateway)

#### Tags

- Legal
- Identity
- Auth
- OAuth

#### Properties

- [Documentation](https://support.filevine.com/hc/en-us/articles/27944810461851-Authenticate-Requests-to-the-API-Gateway)
- [Documentation](https://support.filevine.com/hc/en-us/articles/29937964706203-API-Authentication-Q-A)
- [OpenAPI](openapi/filevine-identity-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/filevine-identity-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/filevine-identity-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Filevine Projects API

List, create, read, and update Filevine projects (matters/cases). Each project belongs to a project type, carries a primary client contact, has a phase, and a customizable set of sections and fields. The Projects API is the spine of Filevine integrations and is the parent surface for documents, notes, deadlines, tasks, and time entries.

- **Human URL:** [https://developer.filevine.io/docs/v2-us/branches/main/31e991e1bfac1-filevine-api-v2](https://developer.filevine.io/docs/v2-us/branches/main/31e991e1bfac1-filevine-api-v2)

#### Tags

- Legal
- Matters
- Case Management
- Projects

#### Properties

- [Documentation](https://developer.filevine.io/docs/v2-us/branches/main/31e991e1bfac1-filevine-api-v2)
- [OpenAPI](openapi/filevine-projects-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/filevine-projects-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/filevine-projects-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/filevine-project-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Structure](json-structure/filevine-project-structure.json)
- [JSON-LD](json-ld/filevine-context.jsonld) — [JSON-LD](https://www.w3.org/TR/json-ld11/)

### Filevine Contacts API

Manage the global Filevine contact list and project-scoped contact attachments. Contacts represent clients, opposing parties, witnesses, experts, and adjusters with structured emails, phones, and organization affiliation.

- **Human URL:** [https://developer.filevine.io/docs/v2-us/branches/main/31e991e1bfac1-filevine-api-v2](https://developer.filevine.io/docs/v2-us/branches/main/31e991e1bfac1-filevine-api-v2)

#### Tags

- Legal
- Contacts

#### Properties

- [Documentation](https://developer.filevine.io/docs/v2-us/branches/main/31e991e1bfac1-filevine-api-v2)
- [OpenAPI](openapi/filevine-contacts-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/filevine-contacts-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/filevine-contacts-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/filevine-contact-schema.json) — [JSON Schema](https://json-schema.org/specification)

### Filevine Documents API

Upload, list, and read documents attached to Filevine projects. Documents support folders, tags, versioning, locking, and optional sharing to the secure client portal.

- **Human URL:** [https://developer.filevine.io/docs/v2-us/branches/main/31e991e1bfac1-filevine-api-v2](https://developer.filevine.io/docs/v2-us/branches/main/31e991e1bfac1-filevine-api-v2)

#### Tags

- Legal
- Documents
- Files

#### Properties

- [Documentation](https://developer.filevine.io/docs/v2-us/branches/main/31e991e1bfac1-filevine-api-v2)
- [OpenAPI](openapi/filevine-documents-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/filevine-documents-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/filevine-documents-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/filevine-document-schema.json) — [JSON Schema](https://json-schema.org/specification)

### Filevine Notes API

Append, edit, and read project notes and activity items. Notes carry a typed kind (note, task, portal message, phone call, text) and support @mentions, pinning, and attached documents.

- **Human URL:** [https://developer.filevine.io/docs/v2-us/da00bc90e087f-create-note](https://developer.filevine.io/docs/v2-us/da00bc90e087f-create-note)

#### Tags

- Legal
- Notes
- Activity

#### Properties

- [Documentation](https://developer.filevine.io/docs/v2-us/da00bc90e087f-create-note)
- [OpenAPI](openapi/filevine-notes-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/filevine-notes-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/filevine-notes-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Filevine Deadlines API

Manage the date-driven legal milestones on a project — statutes of limitations, court dates, response deadlines — with assignees and reminder notifications. Deadlines can chain off a parent deadline.

- **Human URL:** [https://developer.filevine.io/docs/v2-us/branches/main/31e991e1bfac1-filevine-api-v2](https://developer.filevine.io/docs/v2-us/branches/main/31e991e1bfac1-filevine-api-v2)

#### Tags

- Legal
- Deadlines
- Calendaring

#### Properties

- [Documentation](https://developer.filevine.io/docs/v2-us/branches/main/31e991e1bfac1-filevine-api-v2)
- [OpenAPI](openapi/filevine-deadlines-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/filevine-deadlines-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/filevine-deadlines-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Filevine Tasks API

List, create, and update assignable to-do items on a project with status, priority, due dates, and completion tracking. Tasks are produced by workflow automation and by direct user assignment.

- **Human URL:** [https://developer.filevine.io/docs/v2-us/branches/main/31e991e1bfac1-filevine-api-v2](https://developer.filevine.io/docs/v2-us/branches/main/31e991e1bfac1-filevine-api-v2)

#### Tags

- Legal
- Tasks
- Workflow

#### Properties

- [Documentation](https://developer.filevine.io/docs/v2-us/branches/main/31e991e1bfac1-filevine-api-v2)
- [OpenAPI](openapi/filevine-tasks-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/filevine-tasks-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/filevine-tasks-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Filevine Time Entries API

Record billable and non-billable time entries against a project, including timer-driven entries. Time entries feed invoice generation and staff productivity reporting.

- **Human URL:** [https://developer.filevine.io/docs/v2-us/branches/main/31e991e1bfac1-filevine-api-v2](https://developer.filevine.io/docs/v2-us/branches/main/31e991e1bfac1-filevine-api-v2)

#### Tags

- Legal
- Time
- Billing

#### Properties

- [Documentation](https://developer.filevine.io/docs/v2-us/branches/main/31e991e1bfac1-filevine-api-v2)
- [OpenAPI](openapi/filevine-time-entries-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/filevine-time-entries-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/filevine-time-entries-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Filevine Webhooks API

Manage organization webhook subscriptions and receive event callbacks (project.created, project.updated, document.uploaded, note.created, deadline.created, task.completed, payment.created, payment.updated). Each subscription has a unique signing key for delivery verification.

- **Human URL:** [https://support.filevine.com/hc/en-us/articles/13644331859611-Webhooks-Subscriptions](https://support.filevine.com/hc/en-us/articles/13644331859611-Webhooks-Subscriptions)

#### Tags

- Legal
- Webhooks
- Events

#### Properties

- [Documentation](https://support.filevine.com/hc/en-us/articles/13644331859611-Webhooks-Subscriptions)
- [OpenAPI](openapi/filevine-webhooks-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/filevine-webhooks-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/filevine-webhooks-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [AsyncAPI](asyncapi/filevine-events-asyncapi.yml) — [AsyncAPI Specification](https://www.asyncapi.com/docs/reference/specification/latest)

## Common Properties

- [Portal](https://www.filevine.com)
- [Documentation](https://developer.filevine.io/)
- [Documentation](https://developer.filevine.io/docs/v2-us/branches/main/31e991e1bfac1-filevine-api-v2)
- [Documentation](https://developer.filevine.io/docs/v2-ca/branches/main/31e991e1bfac1-filevine-api-v2)
- [Documentation](https://support.filevine.com/hc/en-us/sections/28543097895835-API)
- [Documentation](https://support.filevine.com/hc/en-us/articles/27944810461851-Authenticate-Requests-to-the-API-Gateway)
- [Documentation](https://support.filevine.com/hc/en-us/articles/29259311975707-General-API-Q-A)
- [Documentation](https://support.filevine.com/hc/en-us/articles/29937964706203-API-Authentication-Q-A)
- [Documentation](https://support.filevine.com/hc/en-us/articles/13644331859611-Webhooks-Subscriptions)
- [Documentation](https://support.filevine.com/hc/en-us/articles/18053591346331-Intraday-Data-Feed)
- [Portal](https://www.filevine.com/platform/case-management-software/)
- [Documentation](https://www.filevine.com/platform/case-management-software/client-portal-software/)
- [Documentation](https://www.filevine.com/features/docsplus/)
- [Documentation](https://www.filevine.com/integrations/)
- [Pricing](https://www.filevine.com/pricing/)
- [Documentation](https://www.filevine.com/security/)
- [Trust Center](https://trust.paramify.com/filevine)
- [Blog](https://www.filevine.com/blog/)
- [Case Studies](https://www.filevine.com/customers/)
- [Jobs](https://www.filevine.com/company/jobs/)
- [Support](https://support.filevine.com/)
- [Status Page](https://support.filevine.com/hc/en-us/articles/8671232852507-Status-Page)
- [Terms of Service](https://www.filevine.com/subscription-agreement/)
- [Terms of Service](https://www.filevine.com/terms-of-service/)
- [Privacy Policy](https://www.filevine.com/privacy-policy/)
- [Documentation](https://www.filevine.com/subprocessors/)
- [GitHub Organization](https://github.com/Filevine)
- [Code Examples](https://github.com/Filevine/filevine-api-examples)
- [Tool](https://github.com/Filevine/migration-helpers)
- [Documentation](https://github.com/Filevine/fedramp20x-low-submission)
- [LinkedIn](https://www.linkedin.com/company/filevine)
- [X (Twitter)](https://x.com/filevine)
- [Plans](plans/filevine-plans-pricing.yml)
- [Rate Limits](rate-limits/filevine-rate-limits.yml)
- [Fin Ops](finops/filevine-finops.yml)
- [Vocabulary](vocabulary/filevine-vocabulary.yml)
- [Spectral Rules](rules/filevine-rules.yml)
- [Features](undefined)
- [Integrations](undefined)

## Maintainers

**FN:** Kin Lane
**Email:** info@apievangelist.com
**URL:** https://apievangelist.com
