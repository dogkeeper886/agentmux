# STORY-006: Container Image

**Feature**: Container Image
**Status**: pending
**Created**: 2026-03-04

## User Story

As a developer, I want a ready-to-use Docker image that extends the existing webtop with agentmux and all coding agents pre-installed, so that I can spin up a complete agentmux environment with a single `docker compose up`.

## Acceptance Criteria

1. Dockerfile extends `linuxserver/webtop:fedora-mate` as the base image.
2. Claude Code CLI is pre-installed and available on PATH.
3. Cursor IDE (AppImage, extracted) is pre-installed with a desktop entry.
4. Cursor CLI is pre-installed and available on PATH.
5. Zed editor is pre-installed and available on PATH.
6. agentmux daemon is installed at build time and available on PATH.
7. A `docker-compose.yml` is provided with volume mounts, port mapping, timezone, and locale settings.
8. A `Makefile` is provided with `build`, `up`, `down`, `logs`, and `setup` targets.
9. The container starts successfully and all installed tools are functional.
10. Bot tokens (Teams/Slack) are configurable via environment variables or `.env` file.

## Technical Notes

- Follow the existing pattern from `/home/jack/src/docker-compose/webtop/` (Dockerfile, docker-compose.yml, install-apps.sh, Makefile).
- Reuse the install-apps.sh approach for Cursor (AppImage extraction), Zed (`zed.dev/install.sh`), and Claude Code (`claude.ai/install.sh`).
- Consider baking app installs into the Dockerfile (multi-stage or RUN steps) instead of a post-start script for a fully self-contained image.
- Expose port 3001 for web-based desktop access.
- Mount `/config` volume for persistent user data.
- Set `TZ=Asia/Taipei`, `LANG=en_US.UTF-8`, `LC_ALL=en_US.UTF-8` as defaults.

## Dependencies

- STORY-001
