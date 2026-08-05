---
name: Launch a SMART on FHIR app against ModMed
description: Run the SMART App Launch authorization_code + PKCE flow and read a patient's clinical record from the ONC Certified FHIR API.
api: openapi/modernizing-medicine-certified-fhir-api-openapi.json
generated: '2026-08-04'
method: generated
operations:
  - GET /auth/realms/fhir/protocol/openid-connect/auth
  - POST /auth/realms/fhir/protocol/openid-connect/token
  - GET /metadata
  - GET /Patient/{id}
  - GET /Condition
  - GET /Observation
  - GET /MedicationRequest
  - GET /AllergyIntolerance
  - GET /DocumentReference
---

# Launch a SMART on FHIR app against ModMed

FHIR base (`aud`): `https://{firm}.mmi.prod.fhir.ema-api.com/fhir/r4` — the practice's base URL is
published at <https://mm-fhir-endpoint-display.prod.fhir.ema-api.com/>. Production only; there is no
Certified FHIR sandbox.

## Steps

1. **Discover.** `GET /.well-known/smart-configuration` under the FHIR base — it returns the
   `authorization_endpoint`, `token_endpoint`, `scopes_supported`, `capabilities`
   (`launch-ehr`, `launch-standalone`, `permission-patient`, `permission-user`, `sso-openid-connect`,
   `context-ehr-patient`, …) and `code_challenge_methods_supported: [S256]`.
2. **Authorize.** Redirect the browser to
   `GET /auth/realms/fhir/protocol/openid-connect/auth` on `https://sso.ema.md` with
   `response_type=code`, `client_id`, `redirect_uri`, space-separated `scope`, `state`,
   `aud=<FHIR base>`, `code_challenge` and `code_challenge_method=S256`.
   - Patient app: the patient signs in with Patient Portal credentials.
   - Provider app: the provider signs in with their EHR credentials.
   - EHR Launch: include the `launch` scope and pass through the `launch` parameter.
3. **Exchange the code.** `POST /auth/realms/fhir/protocol/openid-connect/token` with
   `grant_type=authorization_code`, `code`, `redirect_uri`, `code_verifier`, `client_id`,
   `client_secret` (`client_secret_post`). You get an `access_token`, an `id_token` when `openid`
   was requested, and a `refresh_token` when `online_access` / `offline_access` was granted.
4. **Read the record.** With `Authorization: Bearer <token>`:
   `GET /Patient/{id}`, `GET /Condition?patient=`, `GET /Observation?patient=`,
   `GET /MedicationRequest?patient=`, `GET /AllergyIntolerance?patient=`,
   `GET /DocumentReference?patient=`. Everything is US Core read/search.

## Scope rules

| App type | Required | Sensible | Wrong |
|---|---|---|---|
| Standalone (patient picker) | `openid`, `launch/patient` | `fhirUser`, `online_access`, `patient/*.rs` | `launch`, `launch/encounter`, `user/*.rs` |
| EHR Launch — Patient | `openid`, `launch`, `launch/patient` | `fhirUser`, `online_access`, `patient/*.rs` | `launch/encounter`, `user/*.rs` |
| EHR Launch — Provider | `openid`, `launch`, `launch/encounter` | `fhirUser`, `online_access`, `user/*.rs` | `launch/patient`, `patient/*.rs` |
| Background / automated | `openid`, `offline_access` | `user/*.rs` | `launch/patient`, `launch/encounter` |

Request only the scopes you need; `patient/…` is bounded to the token's patient, `user/…` to what
the signed-in user can see. Full list in `scopes/modernizing-medicine-scopes.yml`.

## Rules

- Read/search only — no writes on this API.
- After the first Standalone authentication ModMed places a launch link in the patient portal or the
  EHR for repeat use; your app must still provide that first Standalone flow.
- Errors are FHIR `OperationOutcome`.
