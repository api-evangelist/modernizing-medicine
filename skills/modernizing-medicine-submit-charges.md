---
name: Submit charges into ModMed Practice Management
description: Post ChargeItem transactions from an external billing system into ModMed PM and reconcile inbound charges.
api: openapi/modernizing-medicine-ema-proprietary-api-openapi.json
generated: '2026-08-04'
method: generated
operations:
  - POST /fhir/v2/ChargeItem
  - GET /fhir/v2/ChargeItem
  - GET /fhir/v2/ChargeItem/CHG|{id}
  - GET /fhir/v2/ChargeItem/INBOUND
  - GET /fhir/v2/ChargeItem/INBOUND|{id}
  - GET /fhir/v2/Encounter
  - GET /fhir/v2/Practitioner
---

# Submit charges into ModMed Practice Management

Base URL `{base_url}/{firm_url_prefix}/ema`. Bearer token + `x-api-key` on every call.

## Steps

1. **Resolve the encounter and providers.** `GET /fhir/v2/Encounter` (by `patient`, `date`,
   `status`) and `GET /fhir/v2/Practitioner` for the attending, performing and ordering provider ids.
2. **Post the charge.** `POST /fhir/v2/ChargeItem`. One ChargeItem is one transaction and may carry
   several `financialTransactionDetail` lines — one per CPT/HCPCS code. Required identification
   fields per the docs: `sendingFacility` / `receivingFacility` (the target firm prefix),
   `transactionId`, `attendingProviderId`, plus `performingProviderId` per line and optionally
   `orderingProviderId`.
3. **Decide the pricing mode.** Omit `totalCost` and `unitCost` and ModMed PM applies the practice's
   fee schedule automatically. Send `totalCost` at transaction level and `unitCost` per line **only**
   when your system must override the fee schedule with explicit amounts (pathology, DME).
4. **Verify.** `GET /fhir/v2/ChargeItem` for the practice, `GET /fhir/v2/ChargeItem/CHG|{id}` for one
   charge, and `GET /fhir/v2/ChargeItem/INBOUND` / `GET /fhir/v2/ChargeItem/INBOUND|{id}` to
   reconcile inbound charges.

## Rules

- **`transactionId` is the only duplicate guard on this API.** It must be unique per submission from
  your system — ModMed uses it to detect duplicate submissions. There is no `Idempotency-Key`
  header; if you reuse a transactionId ModMed treats the post as a duplicate, and if you change it on
  a retry you will double-bill. Persist it before you send.
- A `201 Created` is the only confirmation a charge landed. On a timeout, re-query
  `GET /fhir/v2/ChargeItem` by patient/context before resending.
- `422` here almost always means a coding/validation problem in a `financialTransactionDetail` line.
- Rate limit 1,250/minute per API key.
