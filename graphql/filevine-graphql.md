# Filevine GraphQL Schema

## Overview

This conceptual GraphQL schema maps the Filevine REST API v2 surface onto a unified GraphQL type system. Filevine is a legal case management platform serving plaintiff law firms in personal injury, mass torts, family law, immigration, criminal defense, and government legal teams. The schema covers the full platform: projects (matters/cases), contacts, parties, documents, sections, custom fields, tasks, deadlines, notes, time entries, billing, invoices, pipelines, forms, questionnaires, webhooks, and org/user management.

The schema is derived from the publicly documented Filevine API v2 endpoints at `https://developer.filevine.io/docs/v2-us/branches/main/31e991e1bfac1-filevine-api-v2` and the Filevine developer and support portal.

---

## Schema File

`filevine-schema.graphql`

---

## Authentication

Filevine uses a PAT-based OAuth 2.0 bearer token flow. A Personal Access Token (PAT) is exchanged at `https://identity.filevine.io/connect/token` for a short-lived bearer access token (typically ~20 minutes). All GraphQL requests would carry this bearer token in the `Authorization` header.

The `Token` type in the schema models the issued access token. The `APIKey` type models the underlying PAT credentials.

---

## Type Summary

### Project Domain (10 types)

| Type | Description |
|---|---|
| `Project` | Core matter/case entity; the spine of all Filevine integrations |
| `ProjectDetails` | Extended project metadata — case number, incident date, statute of limitations, referral source |
| `ProjectStatus` | Enum: ACTIVE, ARCHIVED, CLOSED, PENDING, INTAKE |
| `ProjectType` | Practice-area template defining phases, sections, and default assignments |
| `ProjectPhase` | Enum: INTAKE, INVESTIGATION, DEMAND, LITIGATION, SETTLEMENT, CLOSED |
| `CaseDetails` | Court, judge, jurisdiction, injury type, and liability/damages notes |
| `Pipeline` | Named workflow pipeline associated with a project type |
| `PipelineStage` | Ordered stage within a pipeline with optional automation triggers |
| `ProjectConnection` | Paginated project list (cursor-based) |
| `ProjectEdge` | Single edge in a project connection |

### Party and Contact Domain (8 types)

| Type | Description |
|---|---|
| `Parties` | Project-scoped collection of party relationships |
| `Party` | A contact attached to a project in a specific role |
| `PartyDetails` | Insurance policy, claim number, policy limits, and retention for a party |
| `PartyType` | Enum: INDIVIDUAL, ORGANIZATION, GOVERNMENT, UNKNOWN |
| `PartyRole` | Enum: CLIENT, OPPOSING_PARTY, WITNESS, EXPERT, ADJUSTER, COUNSEL, INSURER, OTHER |
| `Contact` | Global Filevine contact — person or organization |
| `ContactDetails` | DOB, gender, SSN, driver's license, preferred language/contact method |
| `ContactAddress` | Structured postal address with type and primary flag |
| `ContactPhone` | Phone number with type, extension, and SMS capability |

### Document Domain (4 types)

| Type | Description |
|---|---|
| `Document` | File attached to a project — pleadings, medical records, contracts, evidence |
| `DocumentDetails` | MIME type, file size, page count, OCR status, eSignature status |
| `DocumentVersion` | Immutable version of a document with upload metadata |
| `DocumentType` | Enum: PLEADING, MEDICAL_RECORD, CORRESPONDENCE, CONTRACT, EVIDENCE, FORM, REPORT, OTHER |

### Section and Field Domain (4 types)

| Type | Description |
|---|---|
| `Section` | Named grouping of custom fields within a project or project type |
| `SectionDetails` | Help text, required flag, and display conditions for a section |
| `Field` | A single custom field definition within a section |
| `FieldType` | Enum: TEXT, NUMBER, DATE, BOOLEAN, SELECT, MULTI_SELECT, CONTACT, CURRENCY, PERCENTAGE, LINK |
| `FieldValue` | The resolved value of a field on a specific project |

### Task Domain (3 types)

| Type | Description |
|---|---|
| `Task` | Assignable to-do item on a project with status, priority, and due date |
| `TaskDetails` | Reminder, auto-assignment source, related deadline, and attached documents |
| `TaskStatus` | Enum: OPEN, IN_PROGRESS, COMPLETED, CANCELLED, DEFERRED |

### Deadline Domain (1 type)

| Type | Description |
|---|---|
| `Deadline` | Date-driven legal milestone with chained child deadlines and reminders |

### Note and Activity Domain (6 types)

| Type | Description |
|---|---|
| `Note` | Project note with typed kind, body, mentions, and optional document attachments |
| `NoteDetails` | Phone number, email metadata, direction, duration, and portal visibility |
| `NoteType` | Enum: NOTE, TASK, PHONE_CALL, TEXT_MESSAGE, EMAIL, PORTAL_MESSAGE, ACTIVITY |
| `Activity` | Immutable audit event on a project |
| `ActivityType` | Enum of 14 platform event types (project/document/note/deadline/task/payment) |
| `Email` | Captured two-way email message linked to a project |
| `EmailDetails` | From/to/cc/bcc addresses, message ID, thread ID, outbound flag |

### Staff and User Domain (6 types)

| Type | Description |
|---|---|
| `Staff` | An attorney, paralegal, or staff member with billing rate and assignments |
| `StaffDetails` | Bar number, bar state, specializations, hourly rate, annual target |
| `User` | Authenticated Filevine user with role and permissions |
| `UserDetails` | Phone, time zone, locale, avatar, 2FA status |
| `UserRole` | Named role with associated permissions |
| `Permission` | Granular resource/action permission entry |

### Assignment Domain (2 types)

| Type | Description |
|---|---|
| `Assignment` | Maps a user to a project in a typed role (primary, secondary, reviewer, observer) |
| `AssignmentType` | Enum: PRIMARY, SECONDARY, REVIEWER, OBSERVER |

### Form and Questionnaire Domain (4 types)

| Type | Description |
|---|---|
| `Form` | Configurable intake or data-collection form linked to a project type |
| `FormField` | A single question/input field within a form |
| `FormDetails` | Submission count, expiry, redirect URL, and confirmation message |
| `Questionnaire` | A form instance sent to a contact/client with response tracking |
| `QuestionnaireDetails` | Delivery channel, response data, and signature requirement |

### Time and Billing Domain (5 types)

| Type | Description |
|---|---|
| `TimeEntry` | Billable or non-billable time record against a project |
| `BillingDetails` | Billed/adjusted amounts, tax, billing code, and invoice linkage |
| `BillingRate` | Rate schedule by staff, project type, or default |
| `BillingRateType` | Enum: HOURLY, FLAT_FEE, CONTINGENCY, BLENDED |
| `Invoice` | Generated invoice with line items, status, and payment tracking |
| `InvoiceDetails` | Payment terms, method, Stripe transaction ID, sent metadata |
| `InvoiceStatus` | Enum: DRAFT, SENT, PAID, OVERDUE, VOID |

### Report Domain (2 types)

| Type | Description |
|---|---|
| `Report` | Saved Filevine Periscope report definition |
| `ReportDetails` | Report type, filters, columns, sort, schedule, and last-run metadata |

### Organization and Team Domain (2 types)

| Type | Description |
|---|---|
| `Organization` | Law firm, insurance company, or other institutional contact |
| `TeamDetails` | Named staff team within an organization with practice-area alignment |

### API Auth Domain (2 types)

| Type | Description |
|---|---|
| `APIKey` | Personal Access Token (PAT) credential record |
| `Token` | Short-lived OAuth bearer access token issued from the PAT |

### Webhook Domain (2 types)

| Type | Description |
|---|---|
| `Webhook` | Registered event subscription endpoint with signing key |
| `WebhookEvent` | Enum of 8 subscribable platform events |
| `WebhookEventPayload` | Delivery record for a webhook event including response status and retry count |

---

## Queries

The `Query` root exposes:

- Single-resource lookups by ID for all major types
- Filtered list queries for projects, contacts, time entries, and documents (cursor-paginated)
- Organization and team lookups
- Full staff/user roster
- Billing rate and invoice listing
- Pipeline and form discovery
- Webhook and API key management
- `currentUser` for token introspection

## Mutations

The `Mutation` root supports:

- Full CRUD for projects, contacts, tasks, deadlines, and notes
- Document upload and versioning with portal sharing controls
- Task assignment and completion
- Time entry creation and deletion
- Invoice generation, delivery, payment recording, and voiding
- Project/user assignment management
- Webhook lifecycle (create, update, toggle, delete)
- API key creation and revocation
- Questionnaire dispatch to contacts

## Subscriptions

Real-time subscriptions are modeled for:

- Project updates
- Task completions
- Note creation
- Document uploads
- Deadline creation
- Payment events
- Webhook delivery confirmations
- Activity feed (org-wide or project-scoped)

---

## Key Design Notes

1. **Dual-region deployment.** Filevine operates separate US (`api.filevine.io`) and Canada (`api.filevineapp.ca`) gateways. A production GraphQL layer would accept a region parameter or use region-specific endpoints.

2. **Rate limits.** The REST API enforces 320 req/min per endpoint (250 for billing, 5 for reports). A GraphQL implementation would need query cost analysis and per-field rate shaping to stay within these limits.

3. **Custom fields.** Filevine's section/field model is highly dynamic. The `FieldValue.value` scalar is typed as `JSON` to accommodate the full range of field types without a separate union per type.

4. **PAT scopes.** The `APIKey.scopes` field and `Token.scopes` field reflect the scope-based access control used by the Filevine identity service.

5. **Webhook signing.** Each `Webhook` carries a `signingKey` used to verify HMAC delivery signatures on inbound events.

---

## Related Resources

- Developer Portal: https://developer.filevine.io/
- API v2 Reference (US): https://developer.filevine.io/docs/v2-us/branches/main/31e991e1bfac1-filevine-api-v2
- API v2 Reference (Canada): https://developer.filevine.io/docs/v2-ca/branches/main/31e991e1bfac1-filevine-api-v2
- Authentication: https://support.filevine.com/hc/en-us/articles/27944810461851-Authenticate-Requests-to-the-API-Gateway
- Webhooks: https://support.filevine.com/hc/en-us/articles/13644331859611-Webhooks-Subscriptions
- API Help Center: https://support.filevine.com/hc/en-us/sections/28543097895835-API
