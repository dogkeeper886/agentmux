# STORY-004: Agent Routing

**Feature**: Agent Routing
**Status**: pending
**Created**: 2026-03-04

## User Story

As a developer, I want agentmux to forward incoming chat messages to Claude Code or Cursor CLI and stream responses back, so that I can drive AI coding agents from my chat app.

## Acceptance Criteria

1. The daemon spawns and communicates with Claude Code CLI as a subprocess.
2. The daemon spawns and communicates with Cursor CLI as a subprocess.
3. A routing mechanism selects the target agent (default or per-message override).
4. Agent output is captured incrementally and streamed back to the chat platform.
5. Agent errors and timeouts are handled and reported to the user.
6. The default agent is configurable via config file or environment variable.

## Technical Notes

- Use subprocess stdin/stdout for communicating with CLI agents.
- Consider a common agent adapter interface so new agents can be added later.
- Stream long responses in chunks to avoid chat platform message size limits.

## Dependencies

- STORY-001
