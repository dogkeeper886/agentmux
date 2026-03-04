# STORY-003: Slack Integration

**Feature**: Slack Integration
**Status**: pending
**Created**: 2026-03-04

## User Story

As a developer, I want agentmux to connect to Slack using a bot token, so that I can send coding tasks and receive agent responses directly in Slack threads.

## Acceptance Criteria

1. The daemon authenticates with Slack using a configured bot token.
2. Incoming messages mentioning the bot are received and parsed.
3. Agent responses are posted back as threaded replies in the originating conversation.
4. Connection errors are logged and the daemon retries with backoff.
5. Configuration supports setting the Slack token via environment variable or config file.

## Technical Notes

- Use the Slack Bolt SDK or Slack Web API with Socket Mode for receiving events.
- Token should be configurable via environment variable (`AGENTMUX_SLACK_TOKEN`).
- Consider supporting both Socket Mode (no public URL needed) and Events API (webhook-based).

## Dependencies

- STORY-001
