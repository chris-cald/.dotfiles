# Global development instructions

For all code changes, default to TDD using the red-green-refactor loop:

1. Red: add or update a failing test that captures the desired behavior or bug.
2. Green: implement the smallest change that makes the focused test pass.
3. Refactor: clean up only after tests are green.
4. Validate with the focused test first, then relevant broader tests.

If TDD is impractical for a change, explicitly state why before implementing.

## Subagent execution limits

Do not add discretionary subagent token, cost, tool-call, spawn, or runtime limits. In particular, omit `usageBudget`, `costUsd`, and hard `toolBudget` values unless the user explicitly requests that specific limit. Before setting any non-default subagent execution limit, state it and obtain the user's approval. On a workflow failure, preserve and inspect the partial work; do not silently retry with altered limits or execution modes.
