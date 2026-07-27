---
name: Authenticate against the OS Data Hub APIs
description: >-
  Get a working credential for any Ordnance Survey API - project API key in a
  query parameter or header, or an OAuth 2.0 client-credentials Bearer token -
  and tell a credential problem apart from a licensing problem.
api: openapi/ordnance-survey-places-openapi.json
base_url: https://api.os.uk
operations:
  - 'POST https://api.os.uk/oauth2/token/v1'
generated: '2026-07-26'
method: generated
source: >-
  https://docs.os.uk/os-apis/core-concepts/authentication,
  https://docs.os.uk/os-apis/accessing-os-apis/oauth-2-api/technical-specification,
  authentication/ordnance-survey-authentication.yml
---

# Authenticate against the OS Data Hub APIs

Every OS API accepts the same three credentials. There are **no scopes** — a
key is scoped by which APIs sit in its project, not by permission strings.

## 1. Get a project

Credentials belong to an **API Project** in the OS Data Hub
(<https://osdatahub.os.uk/>), not to a user. A project holds a set of APIs, one
**Project API Key** and one **Project API Secret**. OS recommends separate
projects so usage can be monitored per project, and keys can be regenerated in
place if leaked.

Projects run in **development mode** (50 transactions/minute per API) or **live
mode** (600 transactions/minute per API). Both hit production data on the same
host — development mode is a rate limit, not an isolated environment.

## 2. Pick a credential

**API key in a query parameter** — simplest, but the key ends up in URLs, logs
and referrers:

```
GET https://api.os.uk/search/places/v1/find?query=...&key=YOUR_PROJECT_KEY
```

**API key in a header** — same key, better hygiene. The header name is `key`:

```
GET https://api.os.uk/search/places/v1/find?query=...
key: YOUR_PROJECT_KEY
```

**OAuth 2.0 client credentials** — the right choice for browser-side code,
because the long-lived key never leaves your server:

```
POST https://api.os.uk/oauth2/token/v1
Authorization: Basic base64(PROJECT_API_KEY:PROJECT_API_SECRET)
Content-Type: application/x-www-form-urlencoded

grant_type=client_credentials
```

Response: `access_token`, `expires_in`, `issued_at`, `token_type` (always
`Bearer`). The documented example `expires_in` is **299 seconds** — roughly
five minutes. Then:

```
Authorization: Bearer <accessToken>
```

## 3. Know which failure you are looking at

- **401 Unauthorized** — no credential, or a bad/expired one. Re-issue the
  token; check the `key` spelling (it is lowercase).
- **403 Forbidden** — the credential is fine but you are **not entitled**: the
  API is not in your OS Data Hub plan, or not added to this project. Add the
  API to the project, or check whether you need a Premium Plan, Public Sector
  Plan or PSGA membership.

That distinction is the single most common source of confusion with OS.

## What is not there

- No named OAuth scopes, no consent screen, no user-delegated flow — client
  credentials only.
- No `/.well-known/openid-configuration` and no RFC 8414 authorization-server
  metadata. `api.os.uk` answers 200 with a catch-all landing document for those
  paths; do not treat that as discovery.
- No refresh tokens — request a new token when the old one expires.

Follow OS's own guidance: keep keys secure, rotate periodically, watch usage
patterns in the API Dashboard and alert on anomalies.
