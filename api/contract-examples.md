# Contract Examples — api-routes-reference-lab

## Success Response

```json
{
  "data": [
    { "id": "ord_001", "status": "completed", "orderDate": "2026-06-01T12:00:00Z" }
  ],
  "pagination": {
    "page": 1,
    "pageSize": 25,
    "totalItems": 132
  },
  "error": null
}
```

## Error Response

```json
{
  "data": null,
  "pagination": null,
  "error": {
    "code": "NOT_FOUND",
    "message": "order not found",
    "field": null
  }
}
```

## Disclaimer

> This schema is a sanitized learning version based on independent development work. It does not contain production data, private credentials, proprietary logic, or real customer records.
