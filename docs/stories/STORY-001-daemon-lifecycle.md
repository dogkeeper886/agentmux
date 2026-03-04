# STORY-001: Daemon Lifecycle

**Feature**: Daemon Lifecycle
**Status**: pending
**Created**: 2026-03-04

## User Story

As a developer, I want to start, stop, and check the status of the agentmux daemon via CLI commands, so that I can manage the background service without manual process management.

## Acceptance Criteria

1. `agentmux start` launches the daemon as a background process.
2. `agentmux stop` gracefully shuts down the running daemon.
3. `agentmux status` reports whether the daemon is running, its PID, and uptime.
4. Starting an already-running daemon prints an error instead of spawning a duplicate.
5. Stopping a daemon that is not running prints a clear message.
6. The daemon writes a PID file for process tracking.

## Technical Notes

- Consider using a PID file in a well-known location (e.g. `~/.agentmux/agentmux.pid`).
- Signal handling (SIGTERM, SIGINT) for graceful shutdown.
- This is the foundational story — all other features depend on the daemon running.

## Dependencies

- None
