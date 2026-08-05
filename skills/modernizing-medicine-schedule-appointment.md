---
name: Schedule a ModMed appointment
description: Find a patient, locate an open slot, book an appointment and update it on the EMA Proprietary API.
api: openapi/modernizing-medicine-ema-proprietary-api-openapi.json
generated: '2026-08-04'
method: generated
operations:
  - GET /fhir/v2/Patient
  - GET /fhir/v2/Location
  - GET /fhir/v2/Slot
  - POST /fhir/v2/Appointment
  - GET /fhir/v2/Appointment/{id}
  - PUT /fhir/v2/Appointment/{id}
  - GET /fhir/v2/ValueSet
---

# Schedule a ModMed appointment

The EMA Proprietary API has no `operationId` on any published operation, so every step below is
addressed by **method + path** against the base URL
`{base_url}/{firm_url_prefix}/ema` (sandbox base: `https://stage.ema-api.com/ema-dev/firm/apiportal/ema`).

## Before you start

1. Get a token — `POST /auth/realms/ema-fhir/protocol/openid-connect/token` with
   `grant_type=client_credentials`, `client_id`, `client_secret`
   (`https://sso.ema.md` in production, `https://ssoqa01-lb-01.m2qa.com` in the sandbox).
   The token is an RS256 JWT valid for **900 seconds** and there is **no refresh token** — request a
   new one when it expires.
2. Send **both** headers on every call: `Authorization: Bearer <token>` and `x-api-key: <key>`.
3. Your token's `scope` claim is a space-separated list of ModMed ACLs. If a call returns **403**,
   your vendor application has not been granted the ACL for that resource — ask the synapSYS team.

## Steps

1. **Resolve the practice's appointment types.** `GET /fhir/v2/ValueSet` — appointment types are
   firm-specific, so never hard-code them.
2. **Find the patient.** `GET /fhir/v2/Patient` with `family`, `given`, `birthdate`, `identifier`,
   `email` or `phone`. Page with `_count` (max 50 for Patient) and `page`; follow
   `Bundle.link[relation=next]` until `total` is 0. `Bundle.total` is the count **on this page**,
   not the grand total, unless you send `Content-flag: Pagination_optimization_disabled`.
3. **Pick the location** — `GET /fhir/v2/Location` (filter by `name`, `address-city`,
   `address-state`, `status`).
4. **Find an open slot.** `GET /fhir/v2/Slot` with `date` and `appointment-type`.
   **Slot is not paginated** — do not send `page`.
5. **Book it.** `POST /fhir/v2/Appointment` with the patient, practitioner, location and slot
   references. A `201 Created` means the appointment exists.
6. **Confirm / adjust.** `GET /fhir/v2/Appointment/{id}` to read it back;
   `PUT /fhir/v2/Appointment/{id}` to reschedule or change status.
7. Need referral context on the payload? Send `Content-flag: Referral` to add Referral Contact and
   Referral Source to Patient and Appointment responses.

## Rules

- **No idempotency key exists on this API.** A retried `POST /fhir/v2/Appointment` can create a
  second appointment. Read back with `GET /fhir/v2/Appointment` before retrying a write whose
  response you did not receive.
- **Rate limit:** 1,250 calls/minute per API key (~20/second). Stagger calls; `429` is the only
  signal — there are no `X-RateLimit-*` headers.
- Error handling: `400` bad request, `401` bad/expired token, `403` missing ACL, `404` unknown id
  or firm prefix, `422` validation error, `429` throttled, `500` server error. See
  `errors/modernizing-medicine-problem-types.yml`.
