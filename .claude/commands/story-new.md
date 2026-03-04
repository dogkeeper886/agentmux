# /story-new

Create new user stories from a feature request.

## Input

The user will provide: **$ARGUMENTS**

## Steps

1. Break the feature into distinct user stories containing:
   - **Title** — short descriptive name
   - **As a** [role], **I want** [capability], **so that** [benefit]
   - **Acceptance Criteria** — numbered list of testable conditions
   - **Technical Notes** — implementation hints relevant to this project
   - **Status** — `pending`
   - **Dependencies** — list any other stories this depends on
2. Save each story as a separate file in `docs/stories/` using the naming convention `STORY-<NNN>-<slug>.md`.
3. Auto-increment the story number from the highest existing `STORY-*.md`.
4. Use the template from `.claude/skills/story-template.md`.
5. Run `/story-validation` on every new file.
