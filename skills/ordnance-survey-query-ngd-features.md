---
name: Query OS NGD features with OGC API - Features
description: >-
  Discover an OS National Geographic Database collection, learn its queryable
  attributes, and page through filtered GeoJSON features using the OGC API -
  Features conformant OS NGD API - Features.
api: openapi/ordnance-survey-ngd-features-openapi.json
base_url: https://api.os.uk/features/ngd/ofa/v1
operations:
  - getLandingPageResponse
  - getConformanceResponse
  - getAllCollections
  - getCollectionById
  - getSchema
  - getCollectionQueryables
  - getItems
  - getItemById
licensing: >-
  Metadata operations are anonymous. getItems and getItemById require a key on
  a Premium Plan, Public Sector Plan or PSGA membership.
generated: '2026-07-26'
method: generated
source: openapi/ordnance-survey-ngd-features-openapi.json + https://docs.os.uk/os-apis/accessing-os-apis/os-ngd-api-features
---

# Query OS NGD features

OS NGD API - Features is an OGC API - Features service. Its live `/conformance`
document declares Part 1 Core + OAS3 + GeoJSON, Part 2 CRS, and Part 3
filtering (`simple-cql`, `cql-text`, `arrays`). Everything below follows from
those conformance classes — you can use standard OGC clients against it.

## The discovery path is free

`getLandingPageResponse`, `getConformanceResponse`, `getAllCollections`,
`getCollectionById`, `getSchema` and `getCollectionQueryables` all answer
**anonymously**, with no API key. Only the two data operations —
`getItems` and `getItemById` — are licensed. Do all your exploration before you
need credentials.

## Steps

1. **List collections.** `getAllCollections` → `GET /collections`. Pick a
   `collectionId` (building, land, address, transport themes).
2. **Read the collection.** `getCollectionById` gives `crs`, `storageCrs`,
   `itemType` and the spatial/temporal `extent`. Do not assume EPSG:4326 —
   check `storageCrs`.
3. **Learn what you can filter on.** `getCollectionQueryables` returns the
   `Queryable` vocabulary for that collection: each attribute with `type`,
   `format`, `enum` and a `parent`/`child` hierarchy. **Always call this before
   writing a filter.** Guessing attribute names is the number one source of
   400s here (`"The queryable request is not supported."`).
4. **Read the schema if you need property types.** `getSchema` returns the
   collection's feature property schema.
5. **Query.** `getItems` → `GET /collections/{collectionId}/items` with:
   - `bbox` (+ `bbox-crs`) to bound spatially
   - `datetime` to bound temporally
   - `filter` with `filter-lang` and `filter-crs` for CQL2 text
   - `crs` to choose the output CRS
   - `limit` and `offset` to page
6. **Page with the links, not with arithmetic.** The `FeatureCollectionResponse`
   carries `links[]` with `rel=next`, plus `numberReturned` and `numberMatched`.
   Follow `rel=next` until it is absent.
7. **Fetch one feature.** `getItemById` →
   `GET /collections/{collectionId}/items/{featureId}` when you already hold an
   id (for example a TOID resolved via
   `ordnance-survey-join-property-identifiers.md`).

## Errors specific to this API

- **400** — `"The items request is not supported."` / `"The queryable request
  is not supported."` Your filter or parameter set is not valid for this
  collection; re-read `getCollectionQueryables`.
- **404** — `"Collection '{collectionId}' is not a supported Collection."` Take
  the id from `getAllCollections`.
- **406** — your `Accept` header is not one the operation declares
  (`application/geo+json`, `application/json`).
- **504** — the query timed out. Narrow the `bbox`, tighten the filter, lower
  `limit`. The spec's own 504 description points at
  <https://osdatahub.os.uk/support/status>.

## Tiles

For a rendered rather than a queried view of the same data, OS NGD API - Tiles
serves the same collections as vector tiles with `getCollectionsList`,
`getTileMatrixSetsList` and `getStylesList`.
