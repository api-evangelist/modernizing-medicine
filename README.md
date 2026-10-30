# ModMed

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

ModMed (Modernizing Medicine, Inc., Boca Raton FL) builds specialty-specific cloud healthcare software — the EMA electronic health record, ModMed Practice Management, gGastro for gastroenterology, analytics, revenue cycle management and telehealth — for allergy, dermatology, ENT, gastroenterology, OBGYN, ophthalmology, orthopedics, pain management, plastic surgery, podiatry and urology practices. It publishes two public APIs from one developer portal at portal.api.modmed.com: the EMA Proprietary API, a FHIR R4-style read/write interface under /fhir/v2 covering patients, appointments, slots, coverage, charges, documents and clinical data for synapSYS Marketplace vendors; and the ModMed Certified FHIR API, an ONC-certified HL7 FHIR R4 / US Core read-and-search interface with SMART on FHIR app launch and Bulk FHIR NDJSON export across EMA, ModMed PM, ModMed GI and gGastro. Customer FHIR service base URLs are published publicly as required by the 21st Century Cures Act.

**Areas:** Company · Healthcare · Electronic Health Records · Practice Management · FHIR · Health IT · Interoperability · Medical Billing · SMART on FHIR · Telehealth

## ModMed on APIs.io

Everything profiled for ModMed is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/modernizing-medicine/](https://apis.io/providers/modernizing-medicine/)** — or go straight to one of the APIs or properties below.

### APIs (43)

- [ModMed Appointments and Slots API](https://apis.io/apis/modernizing-medicine/modernizing-medicine-appointments-and-slots-api/) — Appoitments and Slots Details
- [ModMed Authentication API](https://apis.io/apis/modernizing-medicine/modernizing-medicine-authentication-api/) — SMART-on-FHIR OAuth 2.0 endpoints.
- [ModMed Capability Statement API](https://apis.io/apis/modernizing-medicine/modernizing-medicine-capability-statement-api/) — Capability Statement
- [ModMed Care Team API](https://apis.io/apis/modernizing-medicine/modernizing-medicine-careteam-api/) — The CareTeam FHIR resource type<br/>Base profile: http://hl7.org/fhir/us/core/StructureDefinition/us-core-careteam
- [ModMed Charges/Financial API](https://apis.io/apis/modernizing-medicine/modernizing-medicine-charges-financial-api/) — Charges/Financial details
- [ModMed Clinical Data/Clipboard API](https://apis.io/apis/modernizing-medicine/modernizing-medicine-clinical-data-clipboard-api/) — Clinical Data/Clipboard details
- [ModMed Condition API](https://apis.io/apis/modernizing-medicine/modernizing-medicine-condition-api/) — The Condition FHIR resource type<br/>Base profile: http://hl7.org/fhir/us/core/StructureDefinition/us-core-condition
- [ModMed Coverage API](https://apis.io/apis/modernizing-medicine/modernizing-medicine-coverage-api/) — The Coverage FHIR resource type<br/>Base profile: http://hl7.org/fhir/us/core/StructureDefinition/us-core-coverage
- [ModMed Device API](https://apis.io/apis/modernizing-medicine/modernizing-medicine-device-api/) — The Device FHIR resource type<br/>Base profile: http://hl7.org/fhir/us/core/StructureDefinition/us-core-implantable-device
- [ModMed Diagnostic Report API](https://apis.io/apis/modernizing-medicine/modernizing-medicine-diagnosticreport-api/) — The DiagnosticReport FHIR resource type
- [ModMed Documents API](https://apis.io/apis/modernizing-medicine/modernizing-medicine-documents-api/) — Documents details
- [ModMed Encounter API](https://apis.io/apis/modernizing-medicine/modernizing-medicine-encounter-api/) — The Encounter FHIR resource type<br/>Base profile: http://hl7.org/fhir/us/core/StructureDefinition/us-core-encounter
- [ModMed Encounters/Visits API](https://apis.io/apis/modernizing-medicine/modernizing-medicine-encounters-visits-api/) — Encounters/Visits details
- [ModMed Endpoint API](https://apis.io/apis/modernizing-medicine/modernizing-medicine-endpoint-api/) — The Endpoint FHIR resource type
- [ModMed Goal API](https://apis.io/apis/modernizing-medicine/modernizing-medicine-goal-api/) — The Goal FHIR resource type<br/>Base profile: http://hl7.org/fhir/us/core/StructureDefinition/us-core-goal
- [ModMed Group API](https://apis.io/apis/modernizing-medicine/modernizing-medicine-group-api/) — The Group FHIR resource type
- [ModMed Immunization API](https://apis.io/apis/modernizing-medicine/modernizing-medicine-immunization-api/) — The Immunization FHIR resource type<br/>Base profile: http://hl7.org/fhir/us/core/StructureDefinition/us-core-immunization
- [ModMed Insurance API](https://apis.io/apis/modernizing-medicine/modernizing-medicine-insurance-api/) — Insurance Details
- [ModMed Location API](https://apis.io/apis/modernizing-medicine/modernizing-medicine-location-api/) — The Location FHIR resource type<br/>Base profile: http://hl7.org/fhir/us/core/StructureDefinition/us-core-location
- [ModMed Locations/Facilities API](https://apis.io/apis/modernizing-medicine/modernizing-medicine-locations-facilities-api/) — Locations/Facilities details
- [ModMed Medication API](https://apis.io/apis/modernizing-medicine/modernizing-medicine-medication-api/) — The Medication FHIR resource type<br/>Base profile: http://hl7.org/fhir/StructureDefinition/Medication
- [ModMed Medication Dispense API](https://apis.io/apis/modernizing-medicine/modernizing-medicine-medicationdispense-api/) — The MedicationDispense API from ModMed — 2 operation(s) for medicationdispense.
- [ModMed Observation API](https://apis.io/apis/modernizing-medicine/modernizing-medicine-observation-api/) — The Observation FHIR resource type
- [ModMed Operation Definition API](https://apis.io/apis/modernizing-medicine/modernizing-medicine-operationdefinition-api/) — The OperationDefinition FHIR resource type<br/>Base profile: http://hl7.org/fhir/StructureDefinition/OperationDefinition
- [ModMed Organization API](https://apis.io/apis/modernizing-medicine/modernizing-medicine-organization-api/) — The Organization FHIR resource type<br/>Base profile: http://hl7.org/fhir/us/core/StructureDefinition/us-core-organization
- [ModMed Patient API](https://apis.io/apis/modernizing-medicine/modernizing-medicine-patient-api/) — The Patient FHIR resource type<br/>Base profile: http://hl7.org/fhir/us/core/StructureDefinition/us-core-patient
- [ModMed Practitioner API](https://apis.io/apis/modernizing-medicine/modernizing-medicine-practitioner-api/) — The Practitioner FHIR resource type<br/>Base profile: http://hl7.org/fhir/us/core/StructureDefinition/us-core-practitioner
- [ModMed Procedure API](https://apis.io/apis/modernizing-medicine/modernizing-medicine-procedure-api/) — The Procedure FHIR resource type<br/>Base profile: http://hl7.org/fhir/us/core/StructureDefinition/us-core-procedure
- [ModMed Provenance API](https://apis.io/apis/modernizing-medicine/modernizing-medicine-provenance-api/) — The Provenance FHIR resource type<br/>Base profile: http://hl7.org/fhir/us/core/StructureDefinition/us-core-provenance
- [ModMed Providers and Referring Providers API](https://apis.io/apis/modernizing-medicine/modernizing-medicine-providers-and-referring-providers-api/) — Providers details
- [ModMed Questionnaire API](https://apis.io/apis/modernizing-medicine/modernizing-medicine-questionnaire-api/) — The Questionnaire API from ModMed — 2 operation(s) for questionnaire.
- [ModMed Questionnaire Response API](https://apis.io/apis/modernizing-medicine/modernizing-medicine-questionnaireresponse-api/) — The QuestionnaireResponse API from ModMed — 2 operation(s) for questionnaireresponse.
- [ModMed Related Person API](https://apis.io/apis/modernizing-medicine/modernizing-medicine-relatedperson-api/) — The RelatedPerson API from ModMed — 2 operation(s) for relatedperson.
- [ModMed Service Request API](https://apis.io/apis/modernizing-medicine/modernizing-medicine-servicerequest-api/) — The ServiceRequest FHIR resource type<br/>Base profile: http://hl7.org/fhir/us/core/StructureDefinition/us-core-servicerequest
- [ModMed Specimen API](https://apis.io/apis/modernizing-medicine/modernizing-medicine-specimen-api/) — The Specimen API from ModMed — 2 operation(s) for specimen.
- [ModMed Tasks/Recalls API](https://apis.io/apis/modernizing-medicine/modernizing-medicine-tasks-recalls-api/) — Tasks/Recalls Details
- [ModMed Transcription API](https://apis.io/apis/modernizing-medicine/modernizing-medicine-transcription-api/) — Transcription details
- [ModMed Value Set API](https://apis.io/apis/modernizing-medicine/modernizing-medicine-valueset-api/) — The ValueSet FHIR resource type
- [ModMed Allergy Intolerance API](https://apis.io/apis/modernizing-medicine/modernizing-medicine-allergy-intolerance-api/) — The AllergyIntolerance FHIR resource type Base profile: http://hl7.org/fhir/us/core/StructureDefinition/us-core-allergyintolerance
- [ModMed Care plan API](https://apis.io/apis/modernizing-medicine/modernizing-medicine-care-plan-api/) — The CarePlan FHIR resource type Base profile: http://hl7.org/fhir/us/core/StructureDefinition/us-core-careplan
- [ModMed Document Reference API](https://apis.io/apis/modernizing-medicine/modernizing-medicine-document-reference-api/) — The DocumentReference FHIR resource type Base profile: http://hl7.org/fhir/us/core/StructureDefinition/us-core-documentreference
- [ModMed Medication Request API](https://apis.io/apis/modernizing-medicine/modernizing-medicine-medication-request-api/) — The MedicationRequest FHIR resource type Base profile: http://hl7.org/fhir/us/core/StructureDefinition/us-core-medicationrequest
- [ModMed Practitioner Role API](https://apis.io/apis/modernizing-medicine/modernizing-medicine-practitioner-role-api/) — The PractitionerRole FHIR resource type Base profile: http://hl7.org/fhir/us/core/StructureDefinition/us-core-practitionerrole

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [modmed-api-portal-docs](https://apis.io/servers/modernizing-medicine/modmed-api-portal-docs/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Modernizing Medicine Agentic Access](https://apis.io/agentic-access/modernizing-medicine/modernizing-medicine-agentic-access/)

#### Collections (43)

Postman and Open Collection request collections.

- [ModMed Certified Allergy Intolerance API](https://apis.io/collections/modernizing-medicine/open-modernizing-medicine-allergyintolerance-api/)
- [EMA Proprietary Appointments and Slots API](https://apis.io/collections/modernizing-medicine/open-modernizing-medicine-appointments-and-slots-api/)
- [Modernizing Medicine Authentication API](https://apis.io/collections/modernizing-medicine/open-modernizing-medicine-authentication-api/)
- [Modernizing Medicine Capability Statement API](https://apis.io/collections/modernizing-medicine/open-modernizing-medicine-capability-statement-api/)
- [ModMed Certified Care Plan API](https://apis.io/collections/modernizing-medicine/open-modernizing-medicine-careplan-api/)
- [ModMed Certified Care Team API](https://apis.io/collections/modernizing-medicine/open-modernizing-medicine-careteam-api/)
- [EMA Proprietary Charges/Financial API](https://apis.io/collections/modernizing-medicine/open-modernizing-medicine-charges-financial-api/)
- [EMA Proprietary Clinical Data/Clipboard API](https://apis.io/collections/modernizing-medicine/open-modernizing-medicine-clinical-data-clipboard-api/)
- [ModMed Certified Condition API](https://apis.io/collections/modernizing-medicine/open-modernizing-medicine-condition-api/)
- [ModMed Certified Coverage API](https://apis.io/collections/modernizing-medicine/open-modernizing-medicine-coverage-api/)
- [ModMed Certified Device API](https://apis.io/collections/modernizing-medicine/open-modernizing-medicine-device-api/)
- [ModMed Certified Diagnostic Report API](https://apis.io/collections/modernizing-medicine/open-modernizing-medicine-diagnosticreport-api/)
- [ModMed Certified Document Reference API](https://apis.io/collections/modernizing-medicine/open-modernizing-medicine-documentreference-api/)
- [EMA Proprietary Documents API](https://apis.io/collections/modernizing-medicine/open-modernizing-medicine-documents-api/)
- [ModMed Certified Encounter API](https://apis.io/collections/modernizing-medicine/open-modernizing-medicine-encounter-api/)
- [EMA Proprietary Encounters/Visits API](https://apis.io/collections/modernizing-medicine/open-modernizing-medicine-encounters-visits-api/)
- [ModMed Certified Endpoint API](https://apis.io/collections/modernizing-medicine/open-modernizing-medicine-endpoint-api/)
- [ModMed Certified Goal API](https://apis.io/collections/modernizing-medicine/open-modernizing-medicine-goal-api/)
- [ModMed Certified Group API](https://apis.io/collections/modernizing-medicine/open-modernizing-medicine-group-api/)
- [ModMed Certified Immunization API](https://apis.io/collections/modernizing-medicine/open-modernizing-medicine-immunization-api/)
- [EMA Proprietary Insurance API](https://apis.io/collections/modernizing-medicine/open-modernizing-medicine-insurance-api/)
- [ModMed Certified Location API](https://apis.io/collections/modernizing-medicine/open-modernizing-medicine-location-api/)
- [EMA Proprietary Locations/Facilities API](https://apis.io/collections/modernizing-medicine/open-modernizing-medicine-locations-facilities-api/)
- [ModMed Certified Medication API](https://apis.io/collections/modernizing-medicine/open-modernizing-medicine-medication-api/)
- [ModMed Certified Medication Dispense API](https://apis.io/collections/modernizing-medicine/open-modernizing-medicine-medicationdispense-api/)
- …and 18 more published on APIs.io

#### Overlays (4)

OpenAPI overlays, including conversational phrasing for each operation.

- [Modernizing Medicine Certified Fhir Api Overlay](https://apis.io/overlays/modernizing-medicine/modernizing-medicine-certified-fhir-api-overlay/)
- [Modernizing Medicine Certified Fhir Auth Overlay](https://apis.io/overlays/modernizing-medicine/modernizing-medicine-certified-fhir-auth-overlay/)
- [Modernizing Medicine Ema Proprietary Api Overlay](https://apis.io/overlays/modernizing-medicine/modernizing-medicine-ema-proprietary-api-overlay/)
- [Modernizing Medicine Ema Proprietary Auth Overlay](https://apis.io/overlays/modernizing-medicine/modernizing-medicine-ema-proprietary-auth-overlay/)

#### Security (3)

Authentication, trust centre, and vulnerability disclosure.

- [Modernizing Medicine Authentication](https://apis.io/security/modernizing-medicine/modernizing-medicine-authentication/)
- [Modernizing Medicine Domain Security](https://apis.io/security/modernizing-medicine/modernizing-medicine-domain-security/)
- [Modernizing Medicine Vulnerability Disclosure](https://apis.io/security/modernizing-medicine/modernizing-medicine-vulnerability-disclosure/)

#### OAuth scopes (1)

The permissions the API asks for.

- [Modernizing Medicine Scopes](https://apis.io/scopes/modernizing-medicine/modernizing-medicine-scopes/)

#### Rate limits (1)

Published request limits.

- [Modernizing Medicine Rate Limits](https://apis.io/rate-limits/modernizing-medicine/modernizing-medicine-rate-limits/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.modmed.com/)
- [Documentation](https://portal.api.modmed.com/docs)
- [Getting started](https://portal.api.modmed.com/docs/getting-started)
- [API reference](https://portal.api.modmed.com/reference/getting-started-2)
- [Sign up](https://www.modmed.com/synapsys/developers/)
- [Support](https://www.modmed.com/support/)
- [Blog](https://www.modmed.com/resources/blog/)
- [Security](https://www.modmed.com/security/)
- [Compliance](https://www.modmed.com/onc-certification/)
- [Terms of service](https://www.modmed.com/terms-of-use/)
- [Privacy policy](https://www.modmed.com/privacy-policy/)

## API Evangelist rating

**Kin Score 52.0** — developing · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 90.0 |
| Contract quality | 50.8 |
| Contract governance | 18.2 |
| Operational transparency | 35.5 |
| Developer ergonomics | 41.1 |
| Access clarity | 42.1 |

**Agent readiness 49.8** — agent-ready (gated down from agent-native)

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | — |
| MCP Server | verified |
| Auth Clarity | served (partial credit) |
| Idempotency | — |
| Error Semantics | documented (partial credit) |
| OpenAPI Examples | verified |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | — |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | served (partial credit) |
| Protected Resource Metadata | — |
| Dynamic Client Registration | yes |
| Agentic Commerce | — |
| Pagination Ratio | na |
| Operation Distinctiveness | mostly |

**Regulatory alignment 62.5** — Health

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/modernizing-medicine/](https://apis.io/providers/modernizing-medicine/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for ModMed: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/modernizing-medicine/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
