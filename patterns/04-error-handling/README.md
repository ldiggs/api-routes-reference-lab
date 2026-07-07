# Pattern 04 — Error Handling

## Goal

Define one consistent error-response shape and apply it across success and failure cases for the same envelope used in pagination.

## Error Response Shape

```json
{
  "data": null,
  "pagination": null,
  "error": {
    "code": "VALIDATION_ERROR",
    "message": "quantity must be a positive integer",
    "field": "quantity"
  }
}
```

## Design Notes

- Every response — success or failure — uses the same top-level envelope (`data`, `pagination`, `error`), so client code can check one field (`error`) rather than branching on HTTP status alone.
- Error `code` values are a stable, documented enum (`VALIDATION_ERROR`, `NOT_FOUND`, `UNAUTHORIZED`, etc.), not free-form strings, so clients can branch on them reliably.

## Disclaimer

> This schema is a sanitized learning version based on independent development work. It does not contain production data, private credentials, proprietary logic, or real customer records.
