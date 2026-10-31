# Ordnance Survey

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Ordnance Survey is Great Britain's national mapping agency, a government-owned company that maintains the addressing and mapping layer the UK property market runs on - the Unique Property Reference Number (UPRN), the TOID, AddressBase, and the OS National Geographic Database. The UK has no MLS; residential listings sit behind the Rightmove/Zoopla duopoly and agency CRM software, so the open layer in this market is public-sector rather than private, and OS is one half of it alongside HM Land Registry. Its API posture is unusually honest for this sector - the OS Data Hub is a self-serve developer portal with real machine-readable contracts, including OGC-conformant OpenAPI 3.0 documents served live and anonymously at api.os.uk for OS NGD API - Features and Tiles, plus published OpenAPI for the OS Downloads and OS Net APIs. The split that matters is licensing, not reachability: OS OpenData products (OS Open UPRN, OS Open TOID, Code-Point Open, OS Open Names, Boundary-Line, OS Open Linked Identifiers) are free and downloadable with no API key at all through the OS Downloads API, while the premium addressing and mapping products behind OS Places API, OS Features API, and the NGD collections require a paid Premium plan or Public Sector Geospatial Agreement (PSGA) membership. RESO plays no part here - the Real Estate Standards Organization standards are a US MLS construct and appear nowhere in the OS estate. Home market is the United Kingdom.

**Areas:** Real Estate · United Kingdom · Land Registry · Geospatial · Addressing · Open Data · Property Data · PropTech · Government · Mapping · OGC · UPRN

## Ordnance Survey on APIs.io

Everything profiled for Ordnance Survey is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/ordnance-survey/](https://apis.io/providers/ordnance-survey/)** — or go straight to one of the APIs or properties below.

### APIs (25)

- [OS Match & Cleanse API (withdrawn)](https://apis.io/apis/ordnance-survey/os-match-and-cleanse-api/) — Matched and cleansed supplied address strings against OS authoritative addressing data, returning a matched AddressBase record and confidence score.…
- [OS OAuth 2 API](https://apis.io/apis/ordnance-survey/os-oauth2-api/) — OAuth 2.0 client credentials token service issuing time-limited access tokens for OS Data Hub APIs, so project API keys need not be embedded in browser…
- [Ordnance Survey Bounding box API](https://apis.io/apis/ordnance-survey/ordnance-survey-bounding-box-api/) — Find all addresses inside a bounding box.
- [Ordnance Survey Collections API](https://apis.io/apis/ordnance-survey/ordnance-survey-collections-api/) — Retrieve information about collections
- [Ordnance Survey Data Collections API](https://apis.io/apis/ordnance-survey/ordnance-survey-data-collections-api/) — The Data Collections API from Ordnance Survey — 2 operation(s) for data collections.
- [Ordnance Survey Data Packages API](https://apis.io/apis/ordnance-survey/ordnance-survey-data-packages-api/) — Operations providing access to data packages. To access data packages you must supply a valid API key or OAuth 2 access token.
- [Ordnance Survey Features API](https://apis.io/apis/ordnance-survey/ordnance-survey-features-api/) — Retrieve features
- [Ordnance Survey Find API](https://apis.io/apis/ordnance-survey/ordnance-survey-find-api/) — A free string text search of OS Names, intended to be an ambiguous/fuzzy search.
- [Ordnance Survey Landing Page API](https://apis.io/apis/ordnance-survey/ordnance-survey-landing-page-api/) — Ordnance Survey NGD API – Features
- [Ordnance Survey Nearest API](https://apis.io/apis/ordnance-survey/ordnance-survey-nearest-api/) — Find the features closest to a given point.
- [Ordnance Survey Open Data API](https://apis.io/apis/ordnance-survey/ordnance-survey-opendata-api/) — Operations providing access to OpenData products.
- [Ordnance Survey OS OpenData Users API](https://apis.io/apis/ordnance-survey/ordnance-survey-os-opendata-users-api/) — Operations available to customers using the OpenData plan
- [Ordnance Survey Polygon API](https://apis.io/apis/ordnance-survey/ordnance-survey-polygon-api/) — Find all addresses in a polygon or multi-polygon object.
- [Ordnance Survey Radius API](https://apis.io/apis/ordnance-survey/ordnance-survey-radius-api/) — Find all addresses that intersect a given circle.
- [Ordnance Survey Rinex API](https://apis.io/apis/ordnance-survey/ordnance-survey-rinex-api/) — The Rinex API from Ordnance Survey — 5 operation(s) for rinex.
- [Ordnance Survey Service Metadata API](https://apis.io/apis/ordnance-survey/ordnance-survey-service-metadata-api/) — Service Metadata for OS Vector Tiles API
- [Ordnance Survey Stations API](https://apis.io/apis/ordnance-survey/ordnance-survey-stations-api/) — The Stations API from Ordnance Survey — 5 operation(s) for stations.
- [Ordnance Survey Styles API](https://apis.io/apis/ordnance-survey/ordnance-survey-styles-api/) — The Styles API from Ordnance Survey — 5 operation(s) for styles.
- [Ordnance Survey Tile Request API](https://apis.io/apis/ordnance-survey/ordnance-survey-tile-request-api/) — Access and download data for a specific tile
- [Ordnance Survey Tiling Schemes API](https://apis.io/apis/ordnance-survey/ordnance-survey-tiling-schemes-api/) — The Tiling Schemes API from Ordnance Survey — 2 operation(s) for tiling schemes.
- [Ordnance Survey UPRN API](https://apis.io/apis/ordnance-survey/ordnance-survey-uprn-api/) — A search that takes a UPRN as the search parameter.
- [Ordnance Survey Vector Tiles API](https://apis.io/apis/ordnance-survey/ordnance-survey-vector-tiles-api/) — The Vector Tiles API from Ordnance Survey — 2 operation(s) for vector tiles.
- [Ordnance Survey Get Capabilities API](https://apis.io/apis/ordnance-survey/ordnance-survey-get-capabilities-api/) — Returns a metadata document describing the WFS service provided by the server as well as valid WFS operations and parameters.
- [Ordnance Survey Post Code API](https://apis.io/apis/ordnance-survey/ordnance-survey-post-code-api/) — A search based on a property’s postcode
- [Ordnance Survey Tilesets API](https://apis.io/apis/ordnance-survey/ordnance-survey-tilesets-api/) — The Tilesets API from Ordnance Survey — 2 operation(s) for tilesets.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [ordnance-survey](https://apis.io/servers/ordnance-survey/ordnance-survey/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Ordnance Survey Agentic Access](https://apis.io/agentic-access/ordnance-survey/ordnance-survey-agentic-access/)

#### Collections (18)

Postman and Open Collection request collections.

- [OS Features API](https://apis.io/collections/ordnance-survey/open-ordnance-survey-features-wfs/)
- [OS Linked Identifiers API](https://apis.io/collections/ordnance-survey/open-ordnance-survey-linked-identifiers/)
- [OS Maps API](https://apis.io/collections/ordnance-survey/open-ordnance-survey-maps/)
- [OS Names API](https://apis.io/collections/ordnance-survey/open-ordnance-survey-names/)
- [OS NGD API – Features](https://apis.io/collections/ordnance-survey/open-ordnance-survey-ngd-features/)
- [OS NGD API - Tiles](https://apis.io/collections/ordnance-survey/open-ordnance-survey-ngd-tiles/)
- [OS Places API](https://apis.io/collections/ordnance-survey/open-ordnance-survey-places/)
- [OS Vector Tiles API](https://apis.io/collections/ordnance-survey/open-ordnance-survey-vector-tile/)
- [Ordnance Survey Download API](https://apis.io/collections/ordnance-survey/postman-ordnance-survey-downloads/)
- [OS Features API](https://apis.io/collections/ordnance-survey/postman-ordnance-survey-features-wfs-openapi/)
- [OS Linked Identifiers API](https://apis.io/collections/ordnance-survey/postman-ordnance-survey-linked-identifiers-openapi/)
- [OS Maps API](https://apis.io/collections/ordnance-survey/postman-ordnance-survey-maps-openapi/)
- [OS Names API](https://apis.io/collections/ordnance-survey/postman-ordnance-survey-names-openapi/)
- [OS NGD API – Features](https://apis.io/collections/ordnance-survey/postman-ordnance-survey-ngd-features-openapi/)
- [OS NGD API - Tiles](https://apis.io/collections/ordnance-survey/postman-ordnance-survey-ngd-tiles-openapi/)
- [OS Net API](https://apis.io/collections/ordnance-survey/postman-ordnance-survey-osnet/)
- [OS Places API](https://apis.io/collections/ordnance-survey/postman-ordnance-survey-places-openapi/)
- [OS Vector Tiles API](https://apis.io/collections/ordnance-survey/postman-ordnance-survey-vector-tile-openapi/)

#### Overlays (10)

OpenAPI overlays, including conversational phrasing for each operation.

- [Ordnance Survey Downloads Overlay](https://apis.io/overlays/ordnance-survey/ordnance-survey-downloads-overlay/)
- [Ordnance Survey Features Wfs Overlay](https://apis.io/overlays/ordnance-survey/ordnance-survey-features-wfs-overlay/)
- [Ordnance Survey Linked Identifiers Overlay](https://apis.io/overlays/ordnance-survey/ordnance-survey-linked-identifiers-overlay/)
- [Ordnance Survey Maps Overlay](https://apis.io/overlays/ordnance-survey/ordnance-survey-maps-overlay/)
- [Ordnance Survey Names Overlay](https://apis.io/overlays/ordnance-survey/ordnance-survey-names-overlay/)
- [Ordnance Survey Ngd Features Overlay](https://apis.io/overlays/ordnance-survey/ordnance-survey-ngd-features-overlay/)
- [Ordnance Survey Ngd Tiles Overlay](https://apis.io/overlays/ordnance-survey/ordnance-survey-ngd-tiles-overlay/)
- [Ordnance Survey Osnet Overlay](https://apis.io/overlays/ordnance-survey/ordnance-survey-osnet-overlay/)
- [Ordnance Survey Places Overlay](https://apis.io/overlays/ordnance-survey/ordnance-survey-places-overlay/)
- [Ordnance Survey Vector Tile Overlay](https://apis.io/overlays/ordnance-survey/ordnance-survey-vector-tile-overlay/)

#### Security (3)

Authentication, trust centre, and vulnerability disclosure.

- [Ordnance Survey Authentication](https://apis.io/security/ordnance-survey/ordnance-survey-authentication/)
- [Ordnance Survey Domain Security](https://apis.io/security/ordnance-survey/ordnance-survey-domain-security/)
- [Ordnance Survey Vulnerability Disclosure](https://apis.io/security/ordnance-survey/ordnance-survey-vulnerability-disclosure/)

#### OAuth scopes (1)

The permissions the API asks for.

- [Ordnance Survey Scopes](https://apis.io/scopes/ordnance-survey/ordnance-survey-scopes/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Ordnance Survey Plans](https://apis.io/plans/ordnance-survey/ordnance-survey-plans/)

#### Rate limits (1)

Published request limits.

- [Ordnance Survey Rate Limits](https://apis.io/rate-limits/ordnance-survey/ordnance-survey-rate-limits/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.ordnancesurvey.co.uk/)
- [Documentation](https://docs.os.uk/os-apis)
- [Getting started](https://docs.os.uk/os-apis/core-concepts/getting-started-with-an-api-project)
- [API reference](https://docs.os.uk/os-apis/accessing-os-apis)
- [Pricing](https://osdatahub.os.uk/plans)
- [Sign up](https://osdatahub.os.uk/register)
- [Support](https://osdatahub.os.uk/support)
- [Changelog](https://docs.os.uk/os-apis/service-and-data-status/change-log)
- [Blog](https://www.ordnancesurvey.co.uk/blog)
- [Security](https://www.ordnancesurvey.co.uk/governance/policies/vulnerability-disclosure)
- [Terms of service](https://osdatahub.os.uk/legal/termsConditions)
- [Privacy policy](https://www.ordnancesurvey.co.uk/governance/policies/privacy)
- [GitHub](https://github.com/OrdnanceSurvey)
- [Status](https://osdatahub.os.uk/support/status)

## API Evangelist rating

**Kin Score 54.4** — strong · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 75.0 |
| Contract quality | 41.6 |
| Contract governance | 18.2 |
| Operational transparency | 68.4 |
| Developer ergonomics | 64.9 |
| Access clarity | 48.7 |

**Agent readiness 30.4** — agent-ready

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | — |
| MCP Server | — |
| Auth Clarity | bearer (partial credit) |
| Idempotency | — |
| Error Semantics | verified |
| OpenAPI Examples | partial |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | — |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | yes |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | — |
| Operation Distinctiveness | mostly |

**Regulatory alignment 36.3** — Government & Public Sector

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/ordnance-survey/](https://apis.io/providers/ordnance-survey/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Ordnance Survey: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/ordnance-survey/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
