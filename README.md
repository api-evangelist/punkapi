# Punk API (punkapi)

Punk API is a free, no-auth REST API exposing BrewDog's "DIY Dog" open-source beer recipe collection — 325 detailed homebrew recipes crowdsourced and transcribed from the BrewDog DIY Dog PDF. The v2 surface (api.punkapi.com/v2) offered three read-only endpoints: list beers (with rich query filtering on ABV, IBU, EBC, brew date, beer name, hops, malt, yeast, and food pairing), get a beer by id, and get a random beer. Each beer carries a full recipe — ABV, IBU, EBC/SRM colour, target gravities, mash temperature schedule, fermentation temperature, twist, malt and hop bills, yeast strain, food pairings, brewer's tips, and contributor attribution. STATUS — DEPRECATED. BrewDog decommissioned the public api.punkapi.com endpoint in 2023 and the source repositories (sammdec/punkapi-db, sammdec/punkapi-server) were archived on 2023-06-28. The dataset and server source remain MIT-licensed and available; community-hosted mirrors and the `punkapi-db` npm package preserve the contract documented here.

**APIs.json:** [https://punkapi.com](https://punkapi.com)

## Tags

- Food And Drink
- Beer
- BrewDog
- DIY Dog
- Recipes
- Open Source
- Public APIs
- REST
- Deprecated

## Timestamps

- **Created:** 2026-05-28
- **Modified:** 2026-05-29

## APIs

### Punk API — Beers

Read-only REST surface over the 325 BrewDog DIY Dog beer recipes. Three operations — list (with ABV/IBU/EBC/date/ingredient filters and page/per_page pagination up to 80 items), get-by-id, and random. No authentication. The historical baseURL (api.punkapi.com/v2) is no longer reachable; self-host sammdec/punkapi-server or run a mirror.

- **Human URL:** [https://punkapi.com](https://punkapi.com)
- **Base URL:** `https://api.punkapi.com/v2`

#### Tags

- REST
- Beer
- Recipes
- Deprecated

#### Properties

- [Documentation](https://punkapi.com)
- [OpenAPI](openapi/punkapi-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/punkapi.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/punkapi.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/punkapi-beer-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Schema](json-schema/punkapi-error-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Structure](json-structure/punkapi-beer-structure.json)
- [JSON Structure](json-structure/punkapi-error-structure.json)
- [JSON-LD](json-ld/punkapi-context.jsonld) — [JSON-LD](https://www.w3.org/TR/json-ld11/)
- [Example](examples/punkapi-beer-example.json)
- [Example](examples/punkapi-error-example.json)

## Common Properties

- [Website](https://punkapi.com)
- [GitHub Repository](https://github.com/sammdec/punkapi)
- [GitHub Repository](https://github.com/sammdec/punkapi-server)
- [GitHub Organization](https://github.com/sammdec)
- [SDK](https://www.npmjs.com/package/punkapi-db)
- [SDK](https://github.com/apfohl/punkapi)
- [SDK](https://github.com/samjbmason/punkapi-ruby)
- [SDK](https://github.com/billythekid/PunkApi)
- [SDK](https://github.com/mikefrancis/brewdog.js)
- [SDK](https://github.com/Oni-zerone/PunkAPI)
- [SDK](https://github.com/yoohahn/VueDogs-API)
- [SDK](https://hub.docker.com/r/yoohahn/brewdog-recipe)
- [SDK](https://github.com/phillc73/brewdogr)
- [Public APIs Listing](https://github.com/public-apis/public-apis)
- [Plans](plans/punkapi-plans-pricing.yml)
- [Rate Limits](rate-limits/punkapi-rate-limits.yml)
- [Spectral Rules](rules/punkapi-rules.yml)
- [Vocabulary](vocabulary/punkapi-vocabulary.yml)
- [Features](undefined)
- [Use Cases](undefined)
- [Integrations](undefined)
- [Solutions](undefined)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
