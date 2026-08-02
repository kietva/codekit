# C-<DOMAIN>-<NUMBER>: <Feature name>

This is the only human-authored coder input file. Complete it after the matching prototype is approved.

## Feature description

### Problem and goal

_What problem does this feature solve? What is the desired outcome?_

### Users and permissions

- User/role: _Who uses it?_
- Permission: _Who can view or perform each action?_

### Scope

#### In scope

- _Capability_

#### Out of scope

- _Non-goal_

### Acceptance criteria

- [ ] _Observable result_
- [ ] _Observable result_

### Constraints and references

- _Compatibility, performance, security, or business constraint._

## Fields and data

| Field | Type | Required | Source | Validation | Display rule | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| `<field>` | _Type_ | _Yes/No_ | _API/derived/user input_ | _Rule_ | _Format_ | _Notes_ |

### Relationships and states

_Entities, status values, transitions, and derived fields._

## Actions and behavior

| ID | Actor | Trigger | Preconditions | Input | API operation | Success | Failure |
| --- | --- | --- | --- | --- | --- | --- | --- |
| `ACT-001` | _Role_ | _Event_ | _Rule_ | _Payload_ | _Endpoint_ | _Effect_ | _Feedback_ |

For each action, define permission, confirmation, loading/disabled behavior, validation, optimistic behavior, side effects, and audit requirements.

## API contract

### `<METHOD> <PATH>`

Purpose: _Description._

Authorization: _Role/permission._

Request:

```json
{}
```

Success response:

```json
{}
```

Errors: _Status/code, meaning, and client behavior._

Notes: _Pagination, retry, caching, idempotency, and compatibility._

## Assets

Actual assets remain in the matching prototype folder or the host project. Record feature-specific assets here when needed.

| Path/reference | Type | Purpose | Source/license |
| --- | --- | --- | --- |
| _Path_ | _Type_ | _Purpose_ | _Source_ |

## Open questions and assumptions

- **Question:** _Question_
- **Assumption:** _Assumption_
