# MCP Tool Safety Gateway

A secure MCP tool gateway for AI agents with schema validation, permission policies, dry-run execution, approval gates, idempotency keys, and audit logs.

This project treats tool calling as a production safety problem. The model should not be allowed to call arbitrary tools without validation, permissions, and traceability.

## Why this project exists

Agents become useful when they can use tools. They become risky when tool use is not governed.

A production tool layer must answer:

1. What tools exist?
2. Who can call them?
3. Are the arguments valid?
4. Is this action risky?
5. Should a human approve it?
6. Can we audit what happened?

## Core workflow

```text
Agent proposes tool call
  ↓
Validate JSON schema
  ↓
Check user and agent permissions
  ↓
Classify risk level
  ↓
Run dry-run for risky write actions
  ↓
Pause for approval when required
  ↓
Execute tool with idempotency key
  ↓
Record audit log and observation
```

## Core features

| Feature | Purpose |
|---|---|
| Tool registry | Store tool name, description, schema, risk level |
| MCP connector demos | File, Postgres, GitHub/mock connectors |
| JSON Schema validation | Stop bad arguments before execution |
| Policy checks | RBAC / ABAC style access control |
| Dry-run mode | Preview write actions safely |
| Approval gate | Human approval for risky tool calls |
| Idempotency key | Avoid duplicate side effects |
| Audit log | Record every tool call and decision |
| Prompt-injection tests | Test malicious tool-use instructions |

## Interview value

This project helps explain MCP vs function calling, safe enterprise tool use, permissions, auditability, and human approval for risky actions.

## Status

Planning and scaffolding. Issues are used as the implementation roadmap.
