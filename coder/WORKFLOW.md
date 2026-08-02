# Coder Toolkit Workflow

## Step 1: Prepare the feature package

Copy the coder package template to `coder/C-<DOMAIN>-<NUMBER>/`. Complete one file:

- `input.md`: feature scope, acceptance criteria, fields, actions, API contract, constraints, and assumptions.

The prototype reference is automatic. For `coder/C-BUILDING-001/`, the AI must load `prototype/P-BUILDING-001/`. The prototype must be approved before planning.

## Step 2: Prepare and plan

The AI checks the single input file, prototype approval, scans the existing codebase, identifies reusable code, and writes `implementation.md` with:

- Files to change or create
- Existing components/services to reuse
- Data flow and API integration
- Task sequence
- Test strategy
- Risks and questions

The team lead approves this plan before coding starts.

## Step 3: Implement

The developer follows `implementation.md`, keeps changes inside scope, updates task status, adds tests, and reports verification. The developer must stop when the codebase conflicts with the approved package.

## Step 4: Review

The reviewer checks behavior, data mapping, action rules, API integration, reuse, error states, security, accessibility, tests, and scope. Findings go into `review.md` with severity and evidence.

## Quality gate

A feature is ready only when:

- Every acceptance criterion is mapped to code and verification.
- Prototype behavior is preserved or the difference is approved.
- Fields and API responses are mapped without undocumented assumptions.
- Actions enforce permissions, validation, loading, success, and failure behavior.
- Relevant tests, lint, typecheck, and build checks pass.
- Review has no unresolved Critical or Major findings.
