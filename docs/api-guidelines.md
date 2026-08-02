# API Guidelines

Fill in the conventions used by the host project. Module API contracts should reference this document rather than copying it.

## General

- Base URL/versioning: _Fill in._
- Authentication: _Fill in._
- Authorization/error policy: _Fill in._
- Date/time and identifier formats: _Fill in._

## Request and response conventions

```json
{
  "data": {},
  "meta": {}
}
```

Document pagination, filtering, sorting, partial updates, and nullable fields here.

## Errors

Document the stable error shape, user-safe messages, error codes, retry policy, and observability requirements.

## Contract rules

- Treat the approved module contract as the input for implementation.
- Do not infer undocumented fields when a contract can be clarified.
- Keep mock fixtures representative of successful, empty, validation-error, authorization-error, and server-error responses.
- Verify generated client types or schemas when the project supports them.
