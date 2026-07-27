---
name: Resolve a UK address to a UPRN with OS Places
description: >-
  Turn a free-text address, a postcode or a coordinate into an authoritative
  Unique Property Reference Number using the Ordnance Survey OS Places API, and
  read the result correctly across the DPA and LPI views.
api: openapi/ordnance-survey-places-openapi.json
base_url: https://api.os.uk/search/places/v1
operations:
  - getFind
  - getPostcode
  - getUPRN
  - getNearest
  - getBbox
  - getRadius
  - postPolygon
licensing: Premium Plan, Public Sector Plan or PSGA membership required
generated: '2026-07-26'
method: generated
source: openapi/ordnance-survey-places-openapi.json + https://docs.os.uk/os-apis/accessing-os-apis/os-places-api
---

# Resolve a UK address to a UPRN

The UPRN is the UK's national property identifier. It is the join key between
Ordnance Survey data, HM Land Registry records and local-authority property
data, so almost every UK property workflow starts by resolving whatever the
user typed into a UPRN.

## Before you start

- OS Places is **licensed**: it needs a Premium Plan, Public Sector Plan or
  PSGA membership. A valid key on a plan that does not include OS Places
  returns **403**, not 401.
- Authenticate with the `key` query parameter, the `key` request header, or an
  OAuth 2 Bearer token (see `ordnance-survey-authenticate.md`).
- Rate limit: 600 transactions/minute per API per live-mode project, 50 in
  development mode. Handle **429** by backing off — OS publishes no
  `Retry-After` header.

## Choose the right operation

| You have | Call | Operation |
|---|---|---|
| A messy address string | `GET /find?query=...` | `getFind` |
| A postcode | `GET /postcode?postcode=...` | `getPostcode` |
| A UPRN already | `GET /uprn?uprn=...` | `getUPRN` |
| A coordinate | `GET /nearest?point=x,y` | `getNearest` |
| A bounding box | `GET /bbox?bbox=...` | `getBbox` |
| A centre + distance | `GET /radius?point=x,y&radius=...` | `getRadius` |
| A GeoJSON polygon | `POST /polygon` | `postPolygon` |

`postPolygon` is the only non-GET operation in the entire Ordnance Survey
estate, and it is a query-by-body, not a write. Nothing in OS is mutable, so
there is no idempotency key to send.

## Steps

1. **Search.** Call `getFind` with `query` set to the raw address text. Set
   `maxresults` deliberately (default paging is `offset` + `maxresults`) and
   read `header.totalresults` to know whether you have everything.
2. **Pick the dataset view.** Use `dataset=DPA` for the Royal Mail postal view
   (formatted `ADDRESS`, `POSTCODE`, `UDPRN`) or `dataset=LPI` for the local
   authority view (`USRN`, `LPI_KEY`, SAO/PAO components). Both carry `UPRN`.
   Request both when you need the street join — `USRN` only exists on LPI.
3. **Judge the match.** Every result carries `MATCH` and `MATCH_DESCRIPTION`.
   Set `minmatch` and `matchprecision` rather than blindly taking result zero.
   For an ambiguous string, hand the top candidates back to the user instead of
   guessing.
4. **Pin the UPRN.** Once resolved, store the UPRN and re-query with `getUPRN`
   on subsequent runs — it is stable, unlike an address string.
5. **Get coordinates right.** DPA records carry both British National Grid
   (`X_COORDINATE` / `Y_COORDINATE`, EPSG:27700) and `LNG` / `LAT`
   (EPSG:4326). Use `output_srs` / `srs` explicitly rather than assuming.

## Then what

- To reach the topographic feature or the street behind that property, follow
  `ordnance-survey-join-property-identifiers.md` — UPRN → TOID → USRN.
- The free tier of this workflow is the **OS Open UPRN** download product,
  which needs no key at all: `GET https://api.os.uk/downloads/v1/products/OpenUPRN/downloads`.

## Errors

| Code | Meaning here |
|---|---|
| 400 | Missing or malformed query parameter. |
| 401 | No key / bad key. |
| 403 | Authenticated but OS Places is not on your plan or not in your project. |
| 429 | Rate limit exceeded; back off. |
| 504 | Query too broad — narrow the bbox/radius. |

Full catalogue: `errors/ordnance-survey-problem-types.yml`.
