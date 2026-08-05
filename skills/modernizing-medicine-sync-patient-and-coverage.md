---
name: Sync a ModMed patient and their insurance coverage
description: Create or update a patient in EMA and keep their Coverage and InsurancePlan records in sync.
api: openapi/modernizing-medicine-ema-proprietary-api-openapi.json
generated: '2026-08-04'
method: generated
operations:
  - GET /fhir/v2/Patient
  - POST /fhir/v2/Patient
  - PUT /fhir/v2/Patient/{id}
  - GET /fhir/v2/Coverage
  - POST /fhir/v2/Coverage
  - PUT /fhir/v2/Coverage/{id}
  - GET /fhir/v2/InsurancePlan
  - GET /fhir/v2/Account
---

# Sync a ModMed patient and their insurance coverage

Base URL `{base_url}/{firm_url_prefix}/ema`. Auth: OAuth2 `client_credentials` bearer token **plus**
the `x-api-key` header on every call (see `authentication/modernizing-medicine-authentication.yml`).

## Steps

1. **Match before you create.** `GET /fhir/v2/Patient` with `identifier` (your system's MRN if it is
   registered), else `family` + `given` + `birthdate`. Only create when the search returns no match —
   there is no idempotency key to protect you from a duplicate.
2. **Create** — `POST /fhir/v2/Patient` (`201 Created`), or **update** —
   `PUT /fhir/v2/Patient/{id}`.
3. **Read the practice's plans.** `GET /fhir/v2/InsurancePlan` (filter by `owned-by`, `status`) and
   `GET /fhir/v2/InsurancePlan/{id}` for detail. Plans are firm-specific.
4. **List existing coverage.** `GET /fhir/v2/Coverage?patient={patientId}`. Note the coverage `order`
   — it is how ModMed ranks primary/secondary. To read one coverage you need the **Coverage id**, not
   the patient id: `GET /fhir/v2/Coverage/{id}`.
5. **Write coverage.** `POST /fhir/v2/Coverage` for a new policy, `PUT /fhir/v2/Coverage/{id}` to
   correct one. Keep `order` consistent so the practice's primary payer stays primary.
6. **Check the financial picture** — `GET /fhir/v2/Account?patient={patientId}`.

## Rules

- **Pagination**: `_count` (Patient max 50) + `page`; `Bundle.total` is per-page by default.
  Send `Content-flag: Pagination_optimization_disabled` when you need a true total.
- **PHI**: every one of these payloads is protected health information. Log identifiers, never
  payload bodies.
- **403** means your vendor application lacks the ACL for Patient or Coverage — not that the record
  is missing.
- Rate limit 1,250/minute per API key; back off on `429`.
