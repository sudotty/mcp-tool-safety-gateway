# MCP Tool Safety Gateway

A secure MCP tool gateway for AI agents with schema validation, permission policies, dry-run execution, approval gates, idempotency keys, and audit logs.

This project treats tool calling as a production safety problem. The model should not be allowed to call arbitrary tools without validation, permissions, and traceability.

## Why this project exists

Agents become useful when they can use tools. They become risky when tool use is not governed.

A production tool layer must answer:

1. What tools exist?
2. Who can call them?
3. Are the arguments valid?
4. Is this action sensitive?
5. Should a human review it?
6. Can we audit what happened?

## MVP target

Build a small gateway that receives an agent-requested action, validates its arguments, checks policy, previews sensitive operations, and records the result.

```text
agent action -> schema validation -> policy check -> preview -> human review if needed -> execution record -> audit trail
```

## Prioritized roadmap

| Priority | Workstream | Outcome |
|---|---|---|
| P0 / MVP | Tool registry and risk model | Every external action has a clear contract |
| P0 / MVP | Argument validation | Bad calls are stopped before execution |
| P0 / MVP | Permission and audit model | Allowed and denied actions are explainable |
| P1 | Preview and approval flow | Sensitive operations can be reviewed first |
| P1 | MCP connector demos | The same safety layer works across domains |
| P1 | Safety tests and description quality | The gateway handles adversarial or vague inputs better |
| P2 | Interview notes and demo | The project is easy to explain to platform teams |

## Core features

| Feature | Purpose |
|---|---|
| Tool registry | Store tool name, description, schema, and risk level |
| MCP connector demos | File, database, GitHub/mock connectors |
| Schema validation | Stop bad arguments before execution |
| Policy checks | Access control for users, agents, and projects |
| Preview mode | Inspect sensitive actions safely |
| Approval gate | Human review for sensitive actions |
| Idempotency key | Avoid duplicate side effects |
| Audit log | Record every action and decision |
| Safety tests | Test confusing, hostile, or ambiguous inputs |

## Interview value

This project helps explain MCP vs function calling, safe enterprise tool use, permissions, auditability, and human review for sensitive actions.

## Status

Planning and scaffolding. Issues are used as the implementation roadmap.
