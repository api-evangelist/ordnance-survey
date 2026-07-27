---
name: Download OS OpenData with no API key
description: >-
  Automate bulk retrieval of the 26 free OS OpenData products - OS Open UPRN,
  OS Open TOID, OS Open USRN, Code-Point Open, OS Open Names, Boundary-Line and
  the rest - through the OS Downloads API, entirely anonymously.
api: openapi/ordnance-survey-downloads-openapi.yaml
base_url: https://api.os.uk/downloads/v1
operations:
  - 'GET /products'
  - 'GET /products/{productId}'
  - 'GET /products/{productId}/downloads'
  - 'GET /products/{productId}/images/{index}'
  - 'GET /dataPackages'
  - 'GET /dataPackages/{dataPackageId}/versions'
  - 'GET /dataPackages/{dataPackageId}/versions/{versionId}'
  - 'GET /dataPackages/{dataPackageId}/versions/{versionId}/downloads'
operation_id_note: >-
  The published OS Downloads OpenAPI declares no operationId values, so
  operations are named here by method and path exactly as they appear in the
  spec.
licensing: >-
  The /products half is OS OpenData and needs NO key. The /dataPackages half is
  premium and requires a key or OAuth 2 token.
generated: '2026-07-26'
method: generated
source: openapi/ordnance-survey-downloads-openapi.yaml + https://docs.os.uk/os-apis/accessing-os-apis/os-downloads-api
---

# Download OS OpenData with no API key

This is the only place in the Ordnance Survey estate where you get real
national data with **no account and no credentials**. Verified anonymously on
2026-07-26: `GET https://api.os.uk/downloads/v1/products` returns 26 products.

## The open half

1. **List products.** `GET /products` → 26 OS OpenData products. The ids you
   most likely want: `OpenUPRN`, `OpenTOID`, `OpenUSRN`, `CodePointOpen`,
   `OpenNames`, `BoundaryLine`, `OpenRoads`, `OpenRivers`, `OpenZoomstack`,
   `Terrain50`, `OpenMapLocal`, `VectorMapDistrict`, `BuiltUpAreas`,
   `OpenGreenspace`, `LIDS` (OS Open Linked Identifiers), `MiniScale`.
2. **Inspect one.** `GET /products/{productId}` returns a `Product` with
   `version`, `formats`, `areas`, `dataStructures`, `category` and
   `downloadsUrl`. **Check `version` on every run** — that is how you detect a
   new release; there is no webhook and no event feed anywhere in this estate.
3. **List the files.** `GET /products/{productId}/downloads` returns
   `Download` objects with `url`, `fileName`, `size` and **`md5`**. Filter with
   `format`, `subformat` and `area`.
4. **Fetch.** Either follow the `url`, or add `?redirect` to have the API issue
   a **307** straight to the file.
5. **Verify.** Compare the downloaded file against the published `md5` before
   you ingest it. This is the only integrity signal OS gives you.

## The premium half

`GET /dataPackages` and below require authentication (`key` query parameter,
`key` header, or an OAuth 2 Bearer token) and a plan that includes the product.

1. `GET /dataPackages` — the packages available to your account.
2. `GET /dataPackages/{dataPackageId}/versions` — every version, with
   `createdOn`, `reason`, `supplyType` and `productVersion`.
3. `GET /dataPackages/{dataPackageId}/versions/{versionId}` — the file list.
4. `GET /dataPackages/{dataPackageId}/versions/{versionId}/downloads` —
   **307** redirect to the file.

Poll `/versions` on a schedule and act on a new `id`; that is the supported
change-detection pattern.

## Practical notes

- No paging: these endpoints return complete collections.
- **401** on the `/dataPackages` branch means no or bad credentials; **403**
  elsewhere means the product is not on your plan.
- Rate limits still apply (600/min live, 50/min development). Bulk files are
  large — download files serially, not the whole catalogue in parallel.
- Attribution is a licence condition: *Contains OS data © Crown copyright and
  database rights YYYY*.
