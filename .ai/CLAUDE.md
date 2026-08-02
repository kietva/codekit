# CodeKit AI Working Agreement

## Mission

Help operate two workflows: the Prototype Toolkit for fast UI exploration and the Coder Toolkit for controlled production implementation. Stable project conventions live under `docs/`.

## Required workflow

1. Read this file and the relevant documents under `docs/`.
2. For Prototype Toolkit work, read `prototype/<P-ID>/request.md` and inspect the host architecture/components.
3. For Coder Toolkit work, read the complete `coder/<C-ID>/` package.
4. Inspect existing source, routes, components, services, utilities, and tests before proposing code.
5. Reuse existing patterns and state assumptions explicitly.
6. Prototype work uses mock data only and must not change production behavior.
7. Coder work requires an approved prototype and complete `input.md` before implementation.
8. Verify with relevant tests, lint, typecheck, build, and manual checks when available.
9. Report changed files, verification, assumptions, and remaining risks.

## Scope rules

- Do not generate application business code while bootstrapping this kit.
- Do not create duplicate components, services, or utilities.
- Do not add dependencies without explaining why existing code is insufficient.
- Do not expand scope from a prototype or coder input without approval.
- Do not implement against incomplete coder inputs when the feature depends on data, actions, or API behavior.
- If coder input, prototype, API contract, or existing architecture conflict, pause and report the conflict.

## Output style

Use concise sections: Understanding, Findings, Plan, Changes, Verification, Risks, and Open Questions. Never claim a check passed unless it was actually run.

## Source-of-truth hierarchy

1. Explicit user decision or approved module artifacts
2. Existing project architecture and behavior
3. Existing design system and coding guidelines
4. Coder input and approved prototype
5. Coder implementation plan and mock fixtures
6. Documented assumptions, clearly labeled
