# MCP Tool Safety Gateway

A control layer for AI agent tool use: register tools, validate inputs, check access, preview actions, and keep a clear operation record.

This project treats tool calling as a product and platform problem. The goal is not to connect as many tools as possible. The goal is to make each tool request understandable before it touches a real system.

## Why this project exists

Agents become useful when they can use tools. They also become harder to trust when tool use is hidden behind a model response.

A practical tool gateway should answer:

1. What tools exist?
2. What input does each tool accept?
3. Who or what is allowed to use the tool?
4. What will happen before the tool is used?
5. What record remains after the action?

## Product shape

The product should feel like a small operator console for agent tools.

Core screens:

| Screen | What it shows |
|---|---|
| Tool Registry | Tool name, description, owner, input fields, and level |
| Request Preview | Proposed tool name and arguments before execution |
| Input Check | Missing fields, wrong types, and normalized arguments |
| Access Result | Allowed or denied result with short reason |
| Human Check | Review step for higher-impact actions |
| Record View | What was requested, checked, and completed |

## MVP target

Build a small gateway that receives a proposed tool request, validates the input, checks access, previews the operation, and records the result.

```text
tool list -> request preview -> input check -> access result -> review step -> record view
```

The first demo should show that tool use is visible, typed, and controlled.

## Prioritized roadmap

| Priority | Workstream | Outcome |
|---|---|---|
| P0 / MVP | Tool registry and action model | Every external capability has a clear contract |
| P0 / MVP | Input validation | Bad requests are stopped before execution |
| P0 / MVP | Access and record model | Allowed and denied requests are explainable |
| P0 / MVP | Showcase path | One demo path from tool list to final record |
| P1 | Preview and review flow | Higher-impact actions can be reviewed first |
| P1 | MCP connector demos | The same layer works across several tool types |
| P1 | Quality checks for tool descriptions | Vague tool definitions become easier to find |
| P2 | Interview notes and demo script | The project is easy to explain to platform teams |

## Repository documents

- [Business Context](docs/business-context.md)
- [Roadmap](docs/roadmap.md)
- [Showcase Plan](docs/showcase-plan.md)
- [Design Gallery](docs/design-gallery.md)

## Demo narrative

1. Open the tool registry.
2. Select a simple example tool.
3. Show a proposed request.
4. Validate the input.
5. Show access result and preview.
6. Complete the request and open the record view.

## What this project demonstrates

- Practical understanding of MCP and tool calling boundaries.
- Ability to design a platform layer around AI tools.
- Input contracts, access checks, and reviewable operations.
- Business-aware engineering: tool use should be understandable, not magical.
- Strong interview signal for AI platform and agent infrastructure roles.

## Status

Planning and scaffolding. Issues are used as the implementation roadmap. The next build target is the P0 MVP showcase path.
