# Architecture

## Goal

Build a small gateway that makes AI agent tool use visible, typed, checked, and recorded.

## System boundary

The first version should use mock tools and simple connectors. The control layer matters more than the number of real integrations.

## Components

| Component | Responsibility |
|---|---|
| Web UI | Tool registry, request preview, input check, access result, review step, record view |
| Gateway API | Receives proposed tool requests and returns structured results |
| Tool registry | Stores tool contracts, owners, input schema, output shape, and level |
| Input validator | Checks required fields, type rules, and normalized arguments |
| Access checker | Decides whether a user, project, or agent can use a tool |
| Preview runner | Shows what would happen before the action is completed |
| Execution adapter | Calls mock or real tools behind the gateway |
| Record store | Keeps request, checks, result, timing, and notes |

## MVP flow

```text
Register tool
  -> receive proposed request
  -> validate input
  -> check access
  -> show preview
  -> record result
  -> display record view
```

## Recommended first stack

- Frontend: React / Next.js / Tailwind
- Backend: FastAPI or Spring Boot
- Schema: JSON Schema or Zod-style contracts
- Database: PostgreSQL or SQLite first
- Tool adapters: mock file search, mock database query, mock GitHub issue lookup

## Design principle

The gateway should make every external action understandable before it is completed. The main product value is transparency and control, not connector count.
