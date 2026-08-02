# Prototype Workflow

## Step 1: Create input

Copy `templates/request.md` to `prototype/P-<DOMAIN>-<NUMBER>/request.md` and describe the screen in product language.

## Step 2: Generate

Run the prototype AI workflow. It must first inspect:

- `docs/architecture.md`
- `docs/component-library.md`
- Existing routes, layouts, theme, and components
- The package `request.md`

Then it creates a runnable UI with mock data.

## Step 3: Review

Review the actual screen with the team. Record approval, changes, and open questions in `output.md`.

## Step 4: Handoff

After approval, create a matching coder package named `C-<DOMAIN>-<NUMBER>` and link the prototype in `prototype-ref.md`.

## Prototype done criteria

- Main screen and primary flow are runnable.
- Existing architecture and components are reused.
- Mock data represents important UI states.
- No production integration was added.
- Review feedback is recorded.
