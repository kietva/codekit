# Coding Guidelines

These are project-wide defaults. Existing local patterns take precedence when they are intentional and documented.

## Working style

- Inspect relevant source, tests, and documentation before editing.
- Make the smallest complete change that satisfies the approved input.
- Do not refactor unrelated code.
- Reuse existing components, hooks, services, utilities, and test helpers.
- Avoid adding dependencies when the current stack can solve the problem.

## Implementation quality

- Use clear names and keep functions focused.
- Validate external input at system boundaries.
- Handle loading, empty, success, and error states where applicable.
- Preserve accessibility, keyboard behavior, and responsive behavior.
- Keep business rules out of presentation-only components.

## Testing and verification

- Add or update regression coverage for changed behavior.
- Run the narrowest relevant tests first, then the project-required checks.
- Report commands run and any checks that could not be executed.

## Change boundaries

Do not silently change public contracts, permissions, persistence behavior, or user-visible copy. Record assumptions and unresolved questions in the module package.
