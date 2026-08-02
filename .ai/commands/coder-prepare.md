# Coder Toolkit: Prepare

Input: `coder/C-<DOMAIN>-<NUMBER>/`.

Read `coder/C-<DOMAIN>-<NUMBER>/input.md`. Automatically derive and load `prototype/P-<DOMAIN>-<NUMBER>/` by replacing the leading `C-` with `P-`. Stop if the prototype folder is missing or not approved. Check that acceptance criteria are observable, fields map to the prototype, actions have complete rules, and the API contract covers success and failure. Scan the codebase for reusable components/services and record gaps, assumptions, and questions. Do not implement production code.
