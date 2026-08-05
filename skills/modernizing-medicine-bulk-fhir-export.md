---
name: Run a ModMed Bulk FHIR export
description: Authenticate a background app with client_credentials and export a practice population as NDJSON from the ONC Certified FHIR API.
api: openapi/modernizing-medicine-certified-fhir-api-openapi.json
generated: '2026-08-04'
method: generated
operations:
  - POST /auth/realms/fhir/protocol/openid-connect/token
  - GET /metadata
  - GET /Group/{id}
  - GET /Group/{id}/$export
  - GET /Group/$export
  - GET /Patient/$export
  - GET /Patient/{id}/$export
---

# Run a ModMed Bulk FHIR export

The ONC Certified FHIR API has **no sandbox** — this runs against production. The FHIR base is
`https://{firm}.mmi.prod.fhir.ema-api.com/fhir/r4`; find the practice's base URL in the public
directory at <https://mm-fhir-endpoint-display.prod.fhir.ema-api.com/>.

## Before you start

1. Register a **Bulk FHIR (system/background)** app at
   <https://portal.api.modmed.com/docs/register-to-become-a-modmed-certified-fhir-api-vendor>.
   A practice Admin adds your `ClientId` to their practice once.
2. Request `openid`, `offline_access` and the `system/<Resource>.rs` scopes you need — see
   `scopes/modernizing-medicine-scopes.yml`.

## Steps

1. **Get a token.** `POST /auth/realms/fhir/protocol/openid-connect/token` at `https://sso.ema.md`
   with `grant_type=client_credentials`, `client_id`, `client_secret`
   (auth method `client_secret_post` — credentials go in the body).
2. **Confirm capabilities.** `GET /metadata` returns the CapabilityStatement (FHIR 4.0.1, US Core
   server, bulk-data, `$export` declared). `GET /.well-known/smart-configuration` gives the
   authorization endpoints and the full `scopes_supported` list.
3. **Kick off the export.** `GET /Group/{id}/$export` for a cohort, `GET /Group/$export` at type
   level, or `GET /Patient/$export` / `GET /Patient/{id}/$export`. Send
   `Accept: application/fhir+json` and `Prefer: respond-async` per the HL7 Bulk Data spec; the
   response is a `Content-Location` to poll.
4. **Poll** the status URL until it completes, then download each NDJSON file it lists.
5. Resolve `Group` membership first with `GET /Group/{id}` if you need to know what the cohort is.

## Rules

- Read/search only. The Certified FHIR API supports **no writes** — use the EMA Proprietary API for
  create/update flows.
- Every export is PHI at population scale. Handle the NDJSON output under the practice's BAA.
- Errors come back as FHIR `OperationOutcome`, not RFC 9457 problem+json.
