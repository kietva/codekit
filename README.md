# CodeKit

CodeKit is split into two toolkits for a prototype-first team workflow.

```text
PROTOTYPE TOOLKIT                         CODER TOOLKIT
request.md -> runnable UI -> review       prototype + feature docs -> implement -> review
```

## 1. Prototype toolkit

Use it when a screen or flow needs to be explored quickly.

```text
prototype/
└── P-BUILDING-001/
    ├── request.md
    └── output.md
```

You write `request.md`. The AI reads the host project's architecture, layout, theme, and components, then creates a runnable prototype. It uses mock data and does not implement production API or business logic.

## 2. Coder toolkit

Use it after the prototype is approved and the feature is ready for a developer.

```text
coder/
└── C-BUILDING-001/
    ├── input.md
    ├── implementation.md
    └── review.md
```

The team lead or developer defines the feature description, fields, actions, and API in one `input.md`. The coder workflow automatically finds the matching prototype and turns the input into an implementation plan, guides development, and checks the result.

## Handoff

```text
P-BUILDING-001/request.md
        ↓
Prototype UI review and approval
        ↓
C-BUILDING-001/input.md
        ↓
input.md: feature + fields + actions + API
        ↓
implementation.md
        ↓
developer implementation
        ↓
review.md
```

Project-wide architecture and coding conventions remain under `docs/`. This repository contains workflow templates, not product business code.
