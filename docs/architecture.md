# Architecture Guide

This document records stable architectural decisions for the host project. Keep it short and update it when a decision changes.

## System context

- Product: _Describe the product and its primary users._
- Runtime: _Specify frontend, backend, mobile, or other runtimes._
- Deployment: _Describe environments and release flow._

## Architectural principles

- Read and reuse existing code before introducing new abstractions.
- Keep feature behavior close to its feature boundary.
- Keep shared code genuinely generic and independently reusable.
- Prefer explicit data flow and small, reviewable changes.
- Preserve backwards compatibility unless a breaking change is approved.

## Boundaries

Document the major modules, ownership, and allowed dependencies here.

```text
feature/module -> application services -> domain rules -> infrastructure/API
```

## State and data flow

_Describe the state-management approach, server-state strategy, caching, and error propagation._

## Integration conventions

See `docs/api-guidelines.md` for request, response, error, and authentication conventions.

## Decision log

| Date | Decision | Rationale | Status |
| --- | --- | --- | --- |
| YYYY-MM-DD | _Decision_ | _Why_ | Accepted |

## Change policy

When a task conflicts with this document, stop and call out the conflict before implementation. Update this guide only when the architectural decision itself has changed.
