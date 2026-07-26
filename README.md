# Ordnance Survey (ordnance-survey)

Ordnance Survey is Great Britain's national mapping agency, a government-owned company that maintains the addressing and mapping layer the UK property market runs on — the Unique Property Reference Number (UPRN), the TOID, AddressBase, and the OS National Geographic Database. The UK has no MLS; residential listings sit behind the Rightmove/Zoopla duopoly and agency CRM software, so the open layer in this market is public-sector rather than private, and OS is one half of it alongside HM Land Registry. Its API posture is unusually honest for this sector: the OS Data Hub is a self-serve developer portal with real machine-readable contracts — OGC-conformant OpenAPI 3.0 documents served live and anonymously at api.os.uk for OS NGD API - Features and Tiles, plus published OpenAPI for the OS Downloads and OS Net APIs. The split that matters is licensing, not reachability: OS OpenData products are free and downloadable with no API key at all through the OS Downloads API, while the premium addressing and mapping products require a paid Premium plan or Public Sector Geospatial Agreement (PSGA) membership. RESO plays no part here — the Real Estate Standards Organization standards are a US MLS construct and appear nowhere in the OS estate. Home market is the United Kingdom.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/ordnance-survey/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/ordnance-survey/refs/heads/main/apis.yml)

## Tags

- Real Estate
- United Kingdom
- Land Registry
- Geospatial
- Addressing
- Open Data
- Property Data
- PropTech
- Government
- Mapping

## Timestamps

- **Created:** 2026-07-26
- **Modified:** 2026-07-26

## APIs

### OS NGD API - Features

OGC API – Features conformant access to the OS National Geographic Database, serving building, land, address, and transport feature collections as GeoJSON. The OpenAPI 3.0.1 description is served live and anonymously at /api.

- **Human URL:** [https://docs.os.uk/os-apis/accessing-os-apis/os-ngd-api-features](https://docs.os.uk/os-apis/accessing-os-apis/os-ngd-api-features)
- **Base URL:** `https://api.os.uk/features/ngd/ofa/v1`

#### Tags

- Features
- OGC API
- Geospatial
- Property Data

#### Properties

- [OpenAPI](openapi/ordnance-survey-ngd-features-openapi.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://docs.os.uk/os-apis/accessing-os-apis/os-ngd-api-features)
- [API Reference](https://api.os.uk/features/ngd/ofa/v1/api)

### OS NGD API - Tiles

OGC API – Tiles conformant vector tile service over the OS National Geographic Database, including tile matrix sets and styles. The OpenAPI 3.0.1 description is served live and anonymously at /api.

- **Human URL:** [https://docs.os.uk/os-apis/accessing-os-apis/os-ngd-api-tiles](https://docs.os.uk/os-apis/accessing-os-apis/os-ngd-api-tiles)
- **Base URL:** `https://api.os.uk/maps/vector/ngd/ota/v1`

#### Tags

- Tiles
- OGC API
- Vector Tiles
- Mapping

#### Properties

- [OpenAPI](openapi/ordnance-survey-ngd-tiles-openapi.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://docs.os.uk/os-apis/accessing-os-apis/os-ngd-api-tiles)
- [API Reference](https://api.os.uk/maps/vector/ngd/ota/v1/api)

### OS Downloads API

Automated bulk download of OS OpenData and OS Premium datasets. The OpenData half of this API answers anonymously with no key — 26 open products including OS Open UPRN, OS Open TOID, Code-Point Open, OS Open Names, and Boundary-Line, each with direct zip download URLs.

- **Human URL:** [https://docs.os.uk/os-apis/accessing-os-apis/os-downloads-api](https://docs.os.uk/os-apis/accessing-os-apis/os-downloads-api)
- **Base URL:** `https://api.os.uk/downloads/v1`

#### Tags

- Downloads
- Open Data
- Bulk Data
- Addressing

#### Properties

- [OpenAPI](openapi/ordnance-survey-downloads-openapi.yaml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://docs.os.uk/os-apis/accessing-os-apis/os-downloads-api)
- [API Reference](https://api.os.uk/downloads/v1/openapi.yaml)

### OS Net API

High-precision GNSS data from the OS Net network of continuously operating reference stations across Great Britain, including station metadata, health, and RINEX observation files.

- **Human URL:** [https://docs.os.uk/os-apis/accessing-os-apis/os-net-api](https://docs.os.uk/os-apis/accessing-os-apis/os-net-api)
- **Base URL:** `https://api.os.uk/positioning/osnet/v1`

#### Tags

- Positioning
- GNSS
- Surveying

#### Properties

- [OpenAPI](openapi/ordnance-survey-osnet-openapi.yaml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://docs.os.uk/os-apis/accessing-os-apis/os-net-api)
- [API Reference](https://api.os.uk/positioning/osnet/v1/openapi.yaml)

### OS Places API

Address search and geocoding over AddressBase Premium — every UPRN in the United Kingdom, Jersey, Guernsey, and the Isle of Man, with current, provisional, and historic address records and TOID cross-references. Premium or PSGA licensed; no OpenAPI is published.

- **Human URL:** [https://docs.os.uk/os-apis/accessing-os-apis/os-places-api](https://docs.os.uk/os-apis/accessing-os-apis/os-places-api)
- **Base URL:** `https://api.os.uk/search/places/v1`

#### Tags

- Addressing
- Geocoding
- UPRN
- Property Data

#### Properties

- [Documentation](https://docs.os.uk/os-apis/accessing-os-apis/os-places-api)

### OS Names API

A geographic directory of identifiable places, roads, and settlements in Great Britain, with find and nearest operations.

- **Human URL:** [https://docs.os.uk/os-apis/accessing-os-apis/os-names-api](https://docs.os.uk/os-apis/accessing-os-apis/os-names-api)
- **Base URL:** `https://api.os.uk/search/names/v1`

#### Tags

- Search
- Gazetteer
- Geospatial

#### Properties

- [Documentation](https://docs.os.uk/os-apis/accessing-os-apis/os-names-api)

### OS Linked Identifiers API

Resolves the relationships between properties, streets, and OS MasterMap identifiers — UPRN to TOID to USRN — which is the join key between OS data, HM Land Registry records, and local authority property data.

- **Human URL:** [https://docs.os.uk/os-apis/accessing-os-apis/os-linked-identifiers-api](https://docs.os.uk/os-apis/accessing-os-apis/os-linked-identifiers-api)
- **Base URL:** `https://api.os.uk/search/links/v1`

#### Tags

- Identifiers
- UPRN
- TOID
- Property Data

#### Properties

- [Documentation](https://docs.os.uk/os-apis/accessing-os-apis/os-linked-identifiers-api)

### OS Match & Cleanse API

Matches and cleanses supplied address strings against OS authoritative addressing data, returning a matched AddressBase record and confidence score.

- **Human URL:** [https://docs.os.uk/os-apis/accessing-os-apis/os-match-and-cleanse-api](https://docs.os.uk/os-apis/accessing-os-apis/os-match-and-cleanse-api)
- **Base URL:** `https://api.os.uk/search/match/v1`

#### Tags

- Addressing
- Data Quality
- Matching

#### Properties

- [Documentation](https://docs.os.uk/os-apis/accessing-os-apis/os-match-and-cleanse-api)

### OS Features API

OGC Web Feature Service (WFS 2.0.0) over OS MasterMap and premium feature data, with getCapabilities, describeFeatureType, and getFeature operations plus a product archive. XML/WFS rather than OpenAPI.

- **Human URL:** [https://docs.os.uk/os-apis/accessing-os-apis/os-features-api](https://docs.os.uk/os-apis/accessing-os-apis/os-features-api)
- **Base URL:** `https://api.os.uk/features/v1/wfs`

#### Tags

- WFS
- OGC
- Features
- Geospatial

#### Properties

- [Documentation](https://docs.os.uk/os-apis/accessing-os-apis/os-features-api)

### OS Maps API

Pre-rendered raster map tiles in multiple OS styles, served as OGC WMTS and as ZXY tiles.

- **Human URL:** [https://docs.os.uk/os-apis/accessing-os-apis/os-maps-api](https://docs.os.uk/os-apis/accessing-os-apis/os-maps-api)
- **Base URL:** `https://api.os.uk/maps/raster/v1`

#### Tags

- Mapping
- Raster Tiles
- WMTS

#### Properties

- [Documentation](https://docs.os.uk/os-apis/accessing-os-apis/os-maps-api)

### OS Vector Tile API

Vector tile service delivering detailed OS MasterMap data as styleable vector tiles.

- **Human URL:** [https://docs.os.uk/os-apis/accessing-os-apis/os-vector-tile-api](https://docs.os.uk/os-apis/accessing-os-apis/os-vector-tile-api)
- **Base URL:** `https://api.os.uk/maps/vector/v1/vts`

#### Tags

- Mapping
- Vector Tiles

#### Properties

- [Documentation](https://docs.os.uk/os-apis/accessing-os-apis/os-vector-tile-api)

### OS OAuth 2 API

OAuth 2.0 client credentials token service issuing time-limited access tokens for OS Data Hub APIs, so project API keys need not be embedded in browser code. Token URL is https://api.os.uk/oauth2/token/v1.

- **Human URL:** [https://docs.os.uk/os-apis/accessing-os-apis/oauth-2-api](https://docs.os.uk/os-apis/accessing-os-apis/oauth-2-api)
- **Base URL:** `https://api.os.uk/oauth2/token/v1`

#### Tags

- Authentication
- OAuth2

#### Properties

- [Documentation](https://docs.os.uk/os-apis/accessing-os-apis/oauth-2-api)
- [Authentication](https://docs.os.uk/os-apis/core-concepts/authentication)

## Common Properties

- [Website](https://www.ordnancesurvey.co.uk/)
- [Developer Portal](https://osdatahub.os.uk/)
- [Documentation](https://docs.os.uk/os-apis)
- [Authentication](https://docs.os.uk/os-apis/core-concepts/authentication)
- [Getting Started](https://docs.os.uk/os-apis/core-concepts/getting-started-with-an-api-project)
- [Rate Limits](https://docs.os.uk/os-apis/core-concepts/rate-limiting-policy)
- [Plans](https://osdatahub.os.uk/plans)
- [Open Data](https://api.os.uk/downloads/v1/products)
- [GitHub Organization](https://github.com/OrdnanceSurvey)
- [SDK](https://github.com/OrdnanceSurvey/osdatahub)
- [llms.txt](https://docs.os.uk/os-apis/llms.txt)

## Access Notes

- **Access gate:** self-serve. Free OS Data Hub account, project, and API key. The OS OpenData Plan is free and unlimited; the Premium Plan is self-serve with a free allowance of premium transactions up to £1,000 per month; the Public Sector Plan is restricted to Public Sector Geospatial Agreement (PSGA) members.
- **Auth model:** API key as `key` in query or header, or OAuth 2.0 client credentials against `https://api.os.uk/oauth2/token/v1` (no named scopes published). No OpenID Connect discovery document is served.
- **Open data:** yes. `https://api.os.uk/downloads/v1/products` answers anonymously with 26 open products, including OS Open UPRN, OS Open TOID, OS Open USRN, Code-Point Open, and Boundary-Line, with direct download URLs.
- **RESO:** no RESO reference found anywhere in the OS estate — no Web API or Data Dictionary certification, no OData `$metadata`, no UPI. The UK's universal property identifier is OS's own UPRN.
- **Webhooks/events:** none documented.

## Maintainers

- Kin Lane — kin@apievangelist.com
