# Pattern 02 — Pagination and Filtering

## Goal

Define one consistent pagination/filtering contract and apply it across multiple resources, rather than inventing a new shape per route.

## Query Contract

```
GET /api/orders?page=1&pageSize=25&status=completed&sortBy=order_date&sortDir=desc
```

## Response Envelope

```json
{
  "data": [ /* array of resource objects */ ],
  "pagination": {
    "page": 1,
    "pageSize": 25,
    "totalItems": 132
  }
}
```

## Design Notes

- `page`/`pageSize` (offset-based) is simple and sufficient for admin-style lists; cursor-based pagination would be the next step for very large, frequently-changing datasets.
- Filter parameters are always optional query params, never part of the path, so the same base route supports zero or many filters.

## Disclaimer

> This schema is a sanitized learning version based on independent development work. It does not contain production data, private credentials, proprietary logic, or real customer records.
