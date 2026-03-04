# agentmux

A daemon that bridges Microsoft Teams and Slack to AI coding agents (Claude Code, Cursor CLI), letting you drive development directly from your chat app.

## Overview

agentmux runs as a background service inside a [webtop](https://github.com/linuxserver/docker-webtop) container. It listens for messages from Teams or Slack, forwards them to a coding agent CLI, and streams the agent's responses back to the chat thread.

```
Teams/Slack  ──>  agentmux (daemon)  ──>  Claude Code / Cursor CLI
     <──  responses  <──
```

## Features

- **Chat-to-agent proxy** — Send coding tasks from Teams or Slack without leaving your chat
- **Multi-agent support** — Route to Claude Code or Cursor CLI
- **Daemon mode** — Runs in the background inside a webtop container
- **Threaded responses** — Agent replies are posted back to the originating chat thread
- **Session management** — Maintains agent sessions per user or channel

## Getting Started

### Prerequisites

- A webtop container (or any Linux environment with a desktop)
- Claude Code (`claude`) and/or Cursor CLI installed
- A Teams or Slack bot/app token

### Installation

```bash
# TODO
```

### Configuration

```bash
# TODO
```

### Usage

```bash
# Start the daemon
agentmux start

# Check status
agentmux status

# Stop the daemon
agentmux stop
```

From Teams or Slack, message the bot:

```
@agentmux add a login endpoint to the users API
```

The agent picks up the task, works on it, and reports back in the thread.

## Architecture

```
┌─────────────────────────────────────────────┐
│  Webtop Container                           │
│                                             │
│  ┌───────────┐    ┌──────────────────────┐  │
│  │ agentmux  │───>│ Claude Code / Cursor │  │
│  │  daemon   │<───│       CLI            │  │
│  └─────┬─────┘    └──────────────────────┘  │
│        │                                    │
└────────┼────────────────────────────────────┘
         │ (webhooks / websocket)
         │
   ┌─────┴─────┐
   │ Teams /   │
   │ Slack API │
   └───────────┘
```

## License

MIT
