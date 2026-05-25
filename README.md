# Filevine (filevine)

Filevine is the leading legal case management and operating intelligence platform for plaintiff, personal-injury, mass-tort, family, immigration, criminal-defense, estate-planning, and government legal teams. The platform combines a customizable matter / project system with intake (Lead Docket), documents (Docs+), eSignature (Vinesign), contract management (Outlaw), deadline calendaring, time and billing, a secure client portal, and the LOIS Legal Operating Intelligence System for AI-assisted drafting, deposition prep, and case analysis. Filevine exposes a public REST API v2 with US and Canada gateways, PAT-based OAuth bearer authentication, and webhook subscriptions for event-driven integrations.

**URL:** [Visit APIs.json](https://raw.githubusercontent.com/api-evangelist/filevine/refs/heads/main/apis.yml)

**Run:** [Capabilities Using Naftiko](https://github.com/naftiko/fleet?utm_source=api-evangelist&utm_medium=readme&utm_campaign=company-api-evangelist&utm_content=repo)

## Tags

 - Legal, Case Management, Matters, Intake, Documents, LOIS, Webhooks, Legal AI, Personal Injury, Mass Torts

## Timestamps

- **Created:** 2026-05-25
- **Modified:** 2026-05-25

## APIs

### Filevine Identity API
Exchange a Personal Access Token (PAT) for a short-lived bearer access token used by the Filevine API Gateway. Token endpoint: `POST https://identity.filevine.io/connect/token` with `grant_type=personal_access_token`.

- [Documentation](https://support.filevine.com/hc/en-us/articles/27944810461851-Authenticate-Requests-to-the-API-Gateway)
- [OpenAPI](openapi/filevine-identity-api-openapi.yml)
- [Naftiko Capability — Tokens](capabilities/identity-tokens.yaml)

### Filevine Projects API
List, create, read, and update projects (matters / cases). Each project belongs to a project type, carries a primary client contact, has a phase, and a customizable set of sections and fields.

- [Documentation](https://developer.filevine.io/docs/v2-us/branches/main/31e991e1bfac1-filevine-api-v2)
- [OpenAPI](openapi/filevine-projects-api-openapi.yml)
- [JSON Schema — Project](json-schema/filevine-project-schema.json)
- [JSON Structure — Project](json-structure/filevine-project-structure.json)
- [JSON-LD](json-ld/filevine-context.jsonld)
- [Naftiko Capability — Projects](capabilities/projects-projects.yaml)

### Filevine Contacts API
Manage the global contact list and project-scoped contact attachments. Contacts represent clients, opposing parties, witnesses, experts, and adjusters.

- [Documentation](https://developer.filevine.io/docs/v2-us/branches/main/31e991e1bfac1-filevine-api-v2)
- [OpenAPI](openapi/filevine-contacts-api-openapi.yml)
- [JSON Schema — Contact](json-schema/filevine-contact-schema.json)
- [Naftiko Capability — Contacts](capabilities/contacts-contacts.yaml)

### Filevine Documents API
Upload, list, and read documents attached to projects. Supports folders, tags, versioning, locking, and optional client-portal sharing.

- [Documentation](https://developer.filevine.io/docs/v2-us/branches/main/31e991e1bfac1-filevine-api-v2)
- [OpenAPI](openapi/filevine-documents-api-openapi.yml)
- [JSON Schema — Document](json-schema/filevine-document-schema.json)
- [Naftiko Capability — Documents](capabilities/documents-documents.yaml)

### Filevine Notes API
Append, edit, and read project notes / activity items. Notes carry a typed kind (note, task, portal message, phone call, text) and support @mentions, pinning, and attached documents.

- [Documentation](https://developer.filevine.io/docs/v2-us/da00bc90e087f-create-note)
- [OpenAPI](openapi/filevine-notes-api-openapi.yml)
- [Naftiko Capability — Notes](capabilities/notes-notes.yaml)

### Filevine Deadlines API
Manage statutes of limitations, court dates, response deadlines, and reminder notifications. Deadlines can chain.

- [Documentation](https://developer.filevine.io/docs/v2-us/branches/main/31e991e1bfac1-filevine-api-v2)
- [OpenAPI](openapi/filevine-deadlines-api-openapi.yml)
- [Naftiko Capability — Deadlines](capabilities/deadlines-deadlines.yaml)

### Filevine Tasks API
List, create, and update assignable to-do items with status, priority, and due dates.

- [Documentation](https://developer.filevine.io/docs/v2-us/branches/main/31e991e1bfac1-filevine-api-v2)
- [OpenAPI](openapi/filevine-tasks-api-openapi.yml)
- [Naftiko Capability — Tasks](capabilities/tasks-tasks.yaml)

### Filevine Time Entries API
Record billable and non-billable time entries against projects. Feeds invoice generation and productivity reporting.

- [Documentation](https://developer.filevine.io/docs/v2-us/branches/main/31e991e1bfac1-filevine-api-v2)
- [OpenAPI](openapi/filevine-time-entries-api-openapi.yml)
- [Naftiko Capability — Time Entries](capabilities/time-entries-time-entries.yaml)

### Filevine Webhooks API
Manage organization webhook subscriptions and receive event callbacks (project.created, project.updated, document.uploaded, note.created, deadline.created, task.completed, payment.created, payment.updated).

- [Documentation](https://support.filevine.com/hc/en-us/articles/13644331859611-Webhooks-Subscriptions)
- [OpenAPI](openapi/filevine-webhooks-api-openapi.yml)
- [AsyncAPI](asyncapi/filevine-events-asyncapi.yml)
- [Naftiko Capability — Subscriptions](capabilities/webhooks-subscriptions.yaml)

## Authentication

Filevine API v2 uses a Personal Access Token (PAT) → bearer token exchange. POST a form body to `https://identity.filevine.io/connect/token` (or `https://identity.filevineapp.ca/connect/token` for Canada) with `grant_type=personal_access_token`, your PAT in the `token` field, and the desired space-separated `scope`. The response includes an `access_token` valid for ~20 minutes. Pass the token as `Authorization: Bearer ...` on calls to `https://api.filevine.io` (US) or `https://api.filevineapp.ca` (Canada).

## Rate Limits

- Default: 320 requests per endpoint per minute per organization
- Billing endpoints: 250 requests per minute
- Report endpoints: 5 requests per minute

See [rate-limits/filevine-rate-limits.yml](rate-limits/filevine-rate-limits.yml).

## Plans / Pricing

Filevine does not publish list pricing. Packages are quoted by Sales based on selected modules (Matters, Intake, LOIS, Depositions, Signatures, Periscope, Timely, Client Portal, DataBridge) and seat count. A free trial is available. See [plans/filevine-plans-pricing.yml](plans/filevine-plans-pricing.yml).

## FinOps

Subscription, per-seat, per-module SaaS billed monthly in USD. FOCUS-aligned definition in [finops/filevine-finops.yml](finops/filevine-finops.yml).

## Webhook Events

Filevine fires event callbacks for project create/update, document upload, note create, deadline create, task completion, and payment create/update. Each subscription has a unique signing key. See [asyncapi/filevine-events-asyncapi.yml](asyncapi/filevine-events-asyncapi.yml).

## Examples

- [Create Project](examples/filevine-create-project-example.json)
- [Create Note](examples/filevine-create-note-example.json)
- [Create Deadline](examples/filevine-create-deadline-example.json)

## Sample Code on GitHub

- [Filevine/filevine-api-examples](https://github.com/Filevine/filevine-api-examples) — C#, JavaScript, and Python authentication and partner-app samples
- [Filevine/migration-helpers](https://github.com/Filevine/migration-helpers)
- [Filevine/fedramp20x-low-submission](https://github.com/Filevine/fedramp20x-low-submission)

## Security & Compliance

SOC 2 Type II (with HIPAA), CJIS 5.9.3/5.9.4, ISO 27001, HIPAA, GDPR, CCPA/CPRA, PCI DSS (via Stripe). FedRAMP Moderate authorization, FIPS 140-3, and ISO 27701/27017/27018 in progress. AES-256 at rest, TLS 1.2/1.3 in transit, 2FA, RBAC, WAF, DDoS protection, annual pentests, public bug bounty. [Trust Center](https://trust.paramify.com/filevine).
