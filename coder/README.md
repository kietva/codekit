# Coder Toolkit

The Coder Toolkit converts an approved prototype into an implementation-ready feature package and provides a consistent developer/reviewer workflow.

## Input package

Use the `C-<DOMAIN>-<NUMBER>` convention:

```text
coder/C-BUILDING-001/
├── input.md
├── implementation.md
└── review.md
```

The team lead or developer owns one `input.md` containing the feature description, fields, actions, and API definition. The AI may complete missing technical detail from the existing project, but it must mark assumptions and ask for clarification when behavior or contracts are ambiguous.

## Automatic prototype reference

The prototype is resolved by naming convention:

```text
coder/C-BUILDING-001/  ->  prototype/P-BUILDING-001/
```

The AI replaces the leading `C-` with `P-` and searches for that folder. No `prototype-ref.md` is required. If the matching folder does not exist or is not approved, the coder workflow must stop.

## Workflow

```text
Prepare -> Plan -> Implement -> Self-check -> Review -> Accept or Fix
```

- `prepare`: validate that the prototype and feature documents are complete.
- `plan`: inspect the codebase and create `implementation.md`.
- `implement`: code only the approved scope and update implementation status.
- `review`: compare code with the prototype, fields, actions, API, and acceptance criteria; record findings in `review.md`.

See `WORKFLOW.md` and `templates/`.
