# Data Model

## Core tables

### tools

| Field | Purpose |
|---|---|
| id | Tool id |
| name | Stable tool name |
| description | Human-readable purpose |
| owner | Responsible team or module |
| input_schema | JSON input contract |
| output_schema | Optional output contract |
| level | read, write, external, high-impact |
| enabled | Whether tool can be used |

### tool_requests

| Field | Purpose |
|---|---|
| id | Request id |
| tool_id | Target tool |
| actor_type | user, agent, system |
| actor_id | Who initiated the request |
| raw_args | Original arguments |
| normalized_args | Cleaned arguments after validation |
| status | proposed, checked, denied, completed, failed |
| created_at | Request time |

### validation_results

| Field | Purpose |
|---|---|
| id | Validation id |
| request_id | Parent request |
| is_valid | Whether input passed checks |
| errors | Missing or invalid fields |
| warnings | Non-blocking concerns |

### access_results

| Field | Purpose |
|---|---|
| id | Access result id |
| request_id | Parent request |
| allowed | Whether request can continue |
| reason | Short reason |
| policy_name | Policy that matched |

### operation_records

| Field | Purpose |
|---|---|
| id | Record id |
| request_id | Parent request |
| preview | Preview text or structured payload |
| result | Final result or failure note |
| latency_ms | Runtime cost in time |
| created_at | Record time |

## MVP rule

Every tool request should leave a clear record. A reviewer should understand what was requested, what was checked, and what happened.
