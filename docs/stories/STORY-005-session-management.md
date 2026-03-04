# STORY-005: Session Management

**Feature**: Session Management
**Status**: pending
**Created**: 2026-03-04

## User Story

As a developer, I want agentmux to maintain per-user or per-channel agent sessions, so that context is preserved across multiple messages in a conversation.

## Acceptance Criteria

1. Each user or channel gets a dedicated agent session that persists across messages.
2. Session state is maintained for the lifetime of the daemon (in-memory).
3. A session can be explicitly reset by the user (e.g. `@agentmux reset`).
4. Idle sessions are cleaned up after a configurable timeout.
5. Multiple concurrent sessions are supported without cross-contamination.

## Technical Notes

- Key sessions by a composite of platform + channel/user ID.
- Store session state in-memory; persistence to disk is a future enhancement.
- The session timeout should be configurable (`AGENTMUX_SESSION_TIMEOUT`).

## Dependencies

- STORY-001
- STORY-004
