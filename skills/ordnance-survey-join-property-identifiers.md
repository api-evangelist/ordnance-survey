---
name: Join UPRN, TOID and USRN with OS Linked Identifiers
description: >-
  Resolve the relationships between a property (UPRN), a topographic feature
  (TOID) and a street (USRN) using the Ordnance Survey OS Linked Identifiers
  API - the join key between OS data, HM Land Registry and local authority
  property records.
api: openapi/ordnance-survey-linked-identifiers-openapi.json
base_url: https://api.os.uk/search/links/v1
operations:
  - 'GET /identifiers/{id}'
  - 'GET /identifierTypes/{identifierType}/{id}'
  - 'GET /featureTypes/{featureType}/{id}'
  - 'GET /productVersionInfo/{correlationMethod}'
operation_id_note: >-
  The OpenAPI fragments Ordnance Survey publishes for this API declare no
  operationId, so operations are named here by method and path exactly as they
  appear in the spec. overlays/ordnance-survey-linked-identifiers-overlay.yaml
  proposes operationIds without mutating the original.
licensing: >-
  Backed by OS Open Linked Identifiers, an OS OpenData product; API access
  still requires an OS Data Hub project key.
generated: '2026-07-26'
method: generated
source: openapi/ordnance-survey-linked-identifiers-openapi.json + https://docs.os.uk/os-apis/accessing-os-apis/os-linked-identifiers-api
---

# Join UPRN, TOID and USRN

This is the smallest, most under-used API in the Ordnance Survey estate and the
most important one for anybody doing UK property work. It answers one question:
*given one national identifier, what are the others?*

- **UPRN** — a property / addressable location
- **TOID** — an OS MasterMap topographic feature (the building footprint)
- **USRN** — a street

## Steps

1. **Have an identifier.** Get one from
   `ordnance-survey-resolve-address-to-uprn.md`, from HM Land Registry data, or
   from the free OS Open UPRN / OS Open TOID / OS Open USRN downloads.
2. **Resolve it.** `GET /identifiers/{id}` — pass the UPRN, TOID or USRN
   directly. The response is a `linkedIdentifierSet` of `linkedIdentifier`
   objects, each carrying its `correlations`.
3. **Constrain it when you know the type.** If you already know what kind of
   identifier you hold, use `GET /identifierTypes/{identifierType}/{id}`; if
   you know the feature type you want back, use
   `GET /featureTypes/{featureType}/{id}`. Both are narrower and cheaper than
   the open lookup.
4. **Record provenance.** `GET /productVersionInfo/{correlationMethod}` returns
   `correlationMethodInformation` — the method identifier, product creation
   date, and the two `identifierSource` records that were joined. Store this
   with any derived dataset; correlations change as OS republishes source
   products.
5. **Expect fan-out.** A UPRN can correlate to more than one TOID and vice
   versa. Treat the relationship as `has_many`, never `has_one`. See
   `data-model/ordnance-survey-data-model.yml`.

## Where this fits

Once you have the TOID you can pull the feature geometry from
`ordnance-survey-query-ngd-features.md` (OS NGD API - Features). Once you have
the USRN you can join to street-level data. Once you have the UPRN you can join
to HM Land Registry.

## Errors

This API declares the fullest error set in the estate: 400, 401, 403, 404, 405,
429, 500, 503. A **403** means the API is not on your OS Data Hub plan or not
added to your project — it is a licensing result, not a credential result.
Full catalogue: `errors/ordnance-survey-problem-types.yml`.
