# STORY-002: Teams Integration

**Feature**: Teams Integration
**Status**: pending
**Created**: 2026-03-04

## User Story

As a developer, I want agentmux to connect to Microsoft Teams using a bot/app token, so that I can send coding tasks and receive agent responses directly in Teams threads.

## Acceptance Criteria

1. The daemon authenticates with Microsoft Teams using a configured bot/app token.
2. Incoming messages mentioning the bot are received and parsed.
3. Agent responses are posted back as threaded replies in the originating conversation.
4. Connection errors are logged and the daemon retries with backoff.
5. Configuration supports setting the Teams token via environment variable or config file.

## Technical Notes

- Use the Microsoft Bot Framework SDK or REST API.
- Webhook-based or long-polling approach for receiving messages.
- Token and app ID should be configurable via environment variables (`AGENTMUX_TEAMS_TOKEN`, etc.).

## Dependencies

- STORY-001
