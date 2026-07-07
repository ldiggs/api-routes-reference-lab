# Pattern 01 — Resource-Oriented Routing

## Goal

Design a route set for a hypothetical `orders` resource, justifying each route's method, path, and purpose, rather than routing by page/screen.

## Route Set

| Route | Purpose |
|---|---|
| `GET /api/orders` | List orders (paginated, filterable) |
| `GET /api/orders/:id` | Fetch a single order |
| `POST /api/orders` | Create a new order |
| `PATCH /api/orders/:id` | Update fields on an existing order |
| `DELETE /api/orders/:id` | Cancel/remove an order |
| `GET /api/orders/:id/items` | List line items belonging to an order (sub-resource) |

## Design Notes

- Routes are named after the resource (`orders`), not the page that consumes them (`checkout-page`), so the same route set serves any frontend.
- Sub-resources (`order_items`) get their own nested route rather than being folded into the parent payload by default, keeping response sizes predictable.

## Disclaimer

> This schema is a sanitized learning version based on independent development work. It does not contain production data, private credentials, proprietary logic, or real customer records.
