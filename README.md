# Punk API (punkapi)

> **STATUS: DEPRECATED.** The public `api.punkapi.com/v2` endpoint was decommissioned by BrewDog in 2023. The source repositories `sammdec/punkapi-db` and `sammdec/punkapi-server` were archived on 2023-06-28. The dataset and contract remain available via the `punkapi-db` npm package and via community-hosted mirrors. The artifacts in this repo describe the historical v2 contract — the same contract that a self-hosted `punkapi-server` will continue to expose.

Punk API is a free, no-auth REST API exposing BrewDog's "DIY Dog" open-source beer recipe collection — 325 detailed homebrew recipes crowdsourced and transcribed from the BrewDog DIY Dog PDF. The v2 surface (api.punkapi.com/v2) offered three read-only endpoints: list beers (with rich query filtering on ABV, IBU, EBC, brew date, beer name, hops, malt, yeast, and food pairing), get a beer by id, and get a random beer. Each beer carries a full recipe — ABV, IBU, EBC/SRM colour, target gravities, mash temperature schedule, fermentation temperature, twist, malt and hop bills, yeast strain, food pairings, brewer's tips, and contributor attribution.

**URL:** [Visit APIs.json URL](https://punkapi.com)

**Run:** [Capabilities Using Naftiko](https://github.com/naftiko/fleet?utm_source=api-evangelist&utm_medium=readme&utm_campaign=opensource-api-evangelist&utm_content=repo)

## Tags

- Food And Drink, Beer, BrewDog, DIY Dog, Recipes, Open Source, Public APIs, REST, Deprecated

## Type

- **x-type:** opensource
- **x-tier:** 3 (free-deprecated-public-service-with-archived-open-source-source-code)
- **x-status:** deprecated
- **x-deprecated-on:** 2023
- **x-archived-on:** 2023-06-28
- **Replacement:** Self-host [sammdec/punkapi-server](https://github.com/sammdec/punkapi-server) against the [`punkapi-db`](https://www.npmjs.com/package/punkapi-db) npm dataset, or point clients at a community-maintained mirror.

## Timestamps

- **Created:** 2026-05-28
- **Modified:** 2026-05-29

## APIs

### Punk API — Beers

Read-only REST surface over the 325 BrewDog DIY Dog beer recipes. Three operations — list (with ABV/IBU/EBC/date/ingredient filters and page/per_page pagination up to 80 items), get-by-id, and random. No authentication. The historical baseURL (api.punkapi.com/v2) is no longer reachable; self-host sammdec/punkapi-server or run a mirror.

**Human URL:** [https://punkapi.com](https://punkapi.com)
**Base URL (historical):** `https://api.punkapi.com/v2`

#### Tags

- REST, Beer, Recipes, Deprecated

#### Properties

- [Documentation](https://punkapi.com)
- [OpenAPI](openapi/punkapi-openapi.yml)
- [JSONSchema — Beer Schema](json-schema/punkapi-beer-schema.json)
- [JSONSchema — Error Schema](json-schema/punkapi-error-schema.json)
- [JSONStructure — Beer Structure](json-structure/punkapi-beer-structure.json)
- [JSONStructure — Error Structure](json-structure/punkapi-error-structure.json)
- [JSONLD](json-ld/punkapi-context.jsonld)
- [Example — Beer](examples/punkapi-beer-example.json)
- [Example — Error](examples/punkapi-error-example.json)
- [NaftikoCapability — Beers](capabilities/punkapi-beers.yaml)

## Endpoints (Historical Contract)

| Method | Path | Description |
|--------|------|-------------|
| GET | `/beers` | List beers with filters (ABV/IBU/EBC ranges, brew dates, beer_name, hops, malt, yeast, food) + `page` / `per_page` pagination (per_page max 80) |
| GET | `/beers/{beerId}` | Get a single beer recipe by integer id (1-325) |
| GET | `/beers/random` | Get a uniformly random beer recipe |

## Common Properties

- [Website](https://punkapi.com)
- [GitHubRepository — punkapi-db (Recipe Dataset — archived 2023-06-28)](https://github.com/sammdec/punkapi)
- [GitHubRepository — punkapi-server (Express server — archived 2023-06-28)](https://github.com/sammdec/punkapi-server)
- [GitHubOrganization](https://github.com/sammdec)
- [SDK — punkapi-db (npm — recipe dataset)](https://www.npmjs.com/package/punkapi-db)
- [SDK — punkapi (C client)](https://github.com/apfohl/punkapi)
- [SDK — punkapi-ruby (Ruby client)](https://github.com/samjbmason/punkapi-ruby)
- [SDK — PunkApi (PHP client)](https://github.com/billythekid/PunkApi)
- [SDK — brewdog.js (JavaScript client)](https://github.com/mikefrancis/brewdog.js)
- [SDK — PunkAPI (Swift/iOS client)](https://github.com/Oni-zerone/PunkAPI)
- [SDK — VueDogs-API (Vue.js client)](https://github.com/yoohahn/VueDogs-API)
- [SDK — brewdog-recipe (Docker mirror)](https://hub.docker.com/r/yoohahn/brewdog-recipe)
- [SDK — brewdogr (R client)](https://github.com/phillc73/brewdogr)
- [PublicAPIsListing](https://github.com/public-apis/public-apis)
- [Plans](plans/punkapi-plans-pricing.yml)
- [RateLimits](rate-limits/punkapi-rate-limits.yml)
- [SpectralRules](rules/punkapi-rules.yml)
- [Vocabulary](vocabulary/punkapi-vocabulary.yml)

## Features

| Name | Description |
|------|-------------|
| 325 BrewDog DIY Dog Recipes | Crowdsourced transcription of the complete BrewDog DIY Dog PDF — every recipe from Punk IPA (#001) through the final published batch. |
| Full Brewing Recipe | Each beer carries ABV, IBU, EBC, SRM, target gravities, mash schedule, fermentation temperature, malt bill, hop bill, yeast strain, food pairings, and brewer's tips. |
| Recipe-Oriented Query Filters | List endpoint supports filters on ABV (gt/lt), IBU (gt/lt), EBC (gt/lt), brewed-before/after dates, and substring search on beer name, hops, malt, yeast, and food pairing. |
| Pagination | `page` (>=1) and `per_page` (1-80, default 25) on the list endpoint. |
| Random Beer | `/beers/random` returns a uniformly random recipe — useful for "beer of the day" demos. |
| No Authentication | Fully public — no API keys, OAuth, or signup required. |
| No Rate Limits Documented | Best-effort public service while it was live. Only the `per_page` ceiling of 80 is enforced. |
| MIT-Licensed Source | Both `punkapi-db` (dataset) and `punkapi-server` (Express app) are MIT-licensed — self-host or fork freely. |
| npm Distribution | The complete dataset is published as the `punkapi-db` package for direct in-process use without HTTP. |

## Use Cases

| Name | Description |
|------|-------------|
| Homebrewing Reference | Look up a recipe by ABV, hop, or malt to replicate or adapt a BrewDog beer at home-batch scale. |
| Sample / Tutorial API | Front-end and mobile tutorials use Punk API as a fun, schema-rich, no-auth REST target. |
| Beer Discovery App | Power beer recommendation apps, food-pairing tools, and BrewDog fan sites. |
| Search by Ingredient | Filter by hop (e.g. `hops=simcoe`) or malt (e.g. `malt=maris_otter`) to discover recipes using a specific ingredient. |
| Food Pairing Lookup | Filter by `food=spicy_food` to find beers explicitly recommended for spicy cuisine. |
| HTTP Client QA | Stable, well-defined schema makes Punk API a good fixture for codegen tools, OpenAPI tooling, and SDK builders. |

## Integrations

| Name | Description |
|------|-------------|
| BrewDog DIY Dog | The upstream source of every recipe — BrewDog's open-source DIY Dog homebrew PDF. |
| punkapi-db (npm) | The recipe dataset packaged for direct npm install — no HTTP needed. |
| punkapi-server (Express) | The reference Express + node server that exposes the dataset as the v2 REST API. |
| Community Mirrors | Several community-run instances of `punkapi-server` keep the v2 contract reachable after BrewDog's 2023 decommission. |
| Public APIs Catalog | Listed in [github.com/public-apis/public-apis](https://github.com/public-apis/public-apis) under the Food & Drink category. |

## Solutions

| Name | Description |
|------|-------------|
| Self-Host the Server | Clone `sammdec/punkapi-server`, `npm i`, `npm run dev` — get the full v2 contract on `http://localhost:3333`. |
| Embed the Dataset | `npm i --save punkapi-db` to pull the full 325-recipe `data.json` into your application without HTTP. |
| Static JSON Mirror | For purely read use cases, host `data.json` on a CDN and serve clients directly. |

## Artifacts

Machine-readable API specifications organized by format.

### OpenAPI

- [Punk API — Beers](openapi/punkapi-openapi.yml)

### JSON Schema

- [Beer Schema](json-schema/punkapi-beer-schema.json)
- [Error Schema](json-schema/punkapi-error-schema.json)

### JSON Structure

- [Beer Structure](json-structure/punkapi-beer-structure.json)
- [Error Structure](json-structure/punkapi-error-structure.json)

### JSON-LD

- [Punk API Context](json-ld/punkapi-context.jsonld)

### Examples

- [Beer Example](examples/punkapi-beer-example.json)
- [Error Example](examples/punkapi-error-example.json)

## Capabilities

Naftiko capabilities — one self-contained file per Punk API business surface, each exposing both a REST and an MCP adapter.

### Punk API

| Workflow | Operations | File |
|----------|-----------|------|
| Beers | 3 | [capabilities/punkapi-beers.yaml](capabilities/punkapi-beers.yaml) |

## Vocabulary

- [Punk API Vocabulary](vocabulary/punkapi-vocabulary.yml) — Unified taxonomy mapping 1 resource, 3 actions, 1 workflow, and 3 personas across operational (OpenAPI) and capability (Naftiko) dimensions, plus a brewing-domain ontology.

## Rules

- [Punk API Rules](rules/punkapi-rules.yml) — Spectral ruleset enforcing Punk API conventions (read-only surface, snake_case schema properties, beer-resource path constraint, deprecation status).

## Plans

- [Punk API Plans & Pricing](plans/punkapi-plans-pricing.yml) — API Commons Plans 0.1 description of the (single, free, historical) tier.

## Rate Limits

- [Punk API Rate Limits](rate-limits/punkapi-rate-limits.yml) — API Commons Rate Limits 0.1 description of the documented per_page ceiling and the historical undocumented best-effort service.

## Maintainers

**FN:** Kin Lane

**Email:** kin@apievangelist.com
