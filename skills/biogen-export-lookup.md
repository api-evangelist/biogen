---
name: biogen-export-lookup
description: >-
  Look up a Biogen API service or package export record on the Biogen non-production gateway
  (dev1.api.biogen.com) using a portal-issued API key. Use when an agent needs to confirm which
  Biogen APIs or packages exist in the non-production estate before attempting an integration.
api: biogen:biogen-cdp-export-api
operations:
  - getServiceExportNonProd
  - getPackageExportNonProd
generated: '2026-09-04'
method: generated
source: >-
  openapi/biogen-cdp-export-api-openapi.yml, derived from the provider-published definition at
  https://developer1.biogen.com/swagger/export/23683.
---

# Biogen export lookup

Two read operations on Biogen's **non-production** API gateway return the export record for a named
API service or a named API package. This is the only Biogen API contract that is readable without a
developer-portal account.

## Before you start

- **Environment.** These operations exist on `https://dev1.api.biogen.com` — Biogen's
  **non-production** gateway. Production is `https://api.biogen.com` and its contract is not
  published anonymously. Never assume a non-production result reflects production.
- **Credential.** You need an API key issued through the Biogen developer portal. Send it in the
  `x-api-key` request header. There is no self-service registration: the portal's Register control is
  disabled and sign-in is external SSO, so a human with a Biogen portal account has to obtain the key
  first. An anonymous call returns HTTP 403.

## Step 1 — look up a service

Call `getServiceExportNonProd`:

```
GET https://dev1.api.biogen.com/serviceexp/np?Api_Name=<name>
x-api-key: <portal key>
```

`Api_Name` is optional in the provider's definition. Omit it to request the unfiltered export.

## Step 2 — look up a package

Call `getPackageExportNonProd`:

```
GET https://dev1.api.biogen.com/packageexp/np?Package_Name=<name>
x-api-key: <portal key>
```

`Package_Name` is optional in the same way.

## Handling responses

- **200** — the export record. Biogen declares **no response schema**, so do not assume a shape;
  read the body defensively and do not hard-code field paths you have not seen in a live response.
- **403** — no valid key, or the key is not authorized for this package. Get a portal key rather than
  retrying.

## Conventions that apply

- Both operations are **GET** and read-only. There is nothing to reverse and nothing to replay-protect
  (`conventions/biogen-conventions.yml`: `idempotency.coverage: none`, `reversibility.grade: na`).
- Biogen publishes **no rate-limit headers and no documented limits** — do not rely on
  `X-RateLimit-*` or `Retry-After` being present. Back off conservatively on any non-200.
- The error envelope is proprietary (`{error, code}`), not RFC 9457 problem+json
  (`errors/biogen-problem-types.yml`).
- No pagination contract is published; do not construct page parameters.
