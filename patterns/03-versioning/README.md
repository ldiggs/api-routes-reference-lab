# Pattern 03 — Versioning

## Goal

Draft and compare two versioning approaches for an API contract.

## Option A — Path-based

```
/api/v1/orders
/api/v2/orders
```

- Pros: explicit, cache-friendly, easy to route at the infrastructure layer.
- Cons: proliferates routes over time; easy to end up maintaining many versions in parallel.

## Option B — Header-based

```
GET /api/orders
Accept: application/vnd.example.v2+json
```

- Pros: keeps the URL stable; version is a negotiation detail, not a path segment.
- Cons: less visible/discoverable; harder to test manually without setting headers.

## Recommendation (Illustrative)

For an internal/admin-facing API with few consumers, path-based versioning is usually simpler to reason about and debug. Header-based versioning tends to pay off more for a public API with many independent external consumers.

## Disclaimer

> This schema is a sanitized learning version based on independent development work. It does not contain production data, private credentials, proprietary logic, or real customer records.
