# Showcase Plan

## Product form

A small control console for agent tool use. The project should show that tool calls are not hidden magic. They have names, input contracts, access rules, review steps, and logs.

## MVP screens

1. Tool registry: list tools, descriptions, input fields, and owner.
2. Request preview: show the proposed tool call before execution.
3. Validation result: show missing or invalid fields.
4. Access result: show allowed or denied with a reason.
5. Review step: show approve or reject for higher-impact actions.
6. Log view: show what happened and why.

## Demo flow

1. Register three simple tools.
2. Let an agent propose one valid tool call.
3. Show validation and access result.
4. Preview the action.
5. Send it through review.
6. Show the final log.

## Good demo points

- Tool calls are visible and typed.
- Bad inputs are stopped early.
- Review is part of the product, not an afterthought.
- The system has a record of each decision.
- The project shows platform thinking, not only prompt work.

## First-version boundary

Do not integrate many real services first. Use mock tools and make the control layer excellent.
