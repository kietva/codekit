# Prototype Toolkit

The Prototype Toolkit creates fast, reviewable UI prototypes from a short Markdown request.

## Input

Create a package using the `P-<DOMAIN>-<NUMBER>` convention:

```text
prototype/P-BUILDING-001/request.md
```

The request should describe the screen, user goal, visible content, interactions, and references. It does not need to describe implementation details.

## Output

The AI creates a runnable prototype in the host application using existing architecture, layout, theme, and components. It records the route, changed prototype files, mock states, and open questions in `output.md`.

## Rules

- Reuse existing project components and patterns.
- Use mock data only.
- Make the main flow clickable.
- Include loading, empty, error, and success states when relevant.
- Do not change production API, database, authentication, or business logic.
- Do not create duplicate design-system components.

See `WORKFLOW.md` and `templates/request.md`.
