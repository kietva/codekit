# Component Library Guide

This guide helps the AI and developers locate and reuse the existing design system.

## Source of truth

- Component package/path: _Fill in._
- Theme/token package/path: _Fill in._
- Layout/navigation package/path: _Fill in._
- Storybook or visual catalog: _Fill in._

## Reuse rules

1. Search the existing library before creating a component.
2. Prefer composition and existing variants over one-off styling.
3. Extend a shared component only when the behavior is reusable across features.
4. Keep feature-specific composition inside the feature module.
5. Match existing spacing, typography, color, responsive, and accessibility conventions.

## Common mappings

| Need | Reuse | Location |
| --- | --- | --- |
| Page shell | _Existing layout_ | _Path_ |
| Data table | _Existing table_ | _Path_ |
| Form field | _Existing field_ | _Path_ |
| Confirmation dialog | _Existing dialog_ | _Path_ |
| Feedback/toast | _Existing feedback_ | _Path_ |

## Prototype rule

Prototypes must use the real layout and design-system components wherever practical. Mock data and simulated delays are allowed; production API integration is not.
