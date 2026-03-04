# Plan Feature into User Stories

Break down feature requests into well-structured user stories.

## When to Use

- When the user describes a feature, enhancement, or removal request
- When asked to plan, break down, or organize work into stories

## Input

The user will provide: **$ARGUMENTS**

## Action Types

Classify every request as one of:

| Action          | When                                        | Command              |
|-----------------|---------------------------------------------|----------------------|
| **New**         | A brand-new function or capability          | `/story-new`         |
| **Enhancement** | Improving or modifying an existing feature  | `/story-enhance`     |
| **Removal**     | Removing an existing feature                | `/story-remove`      |

## Workflow

1. **Classify** — Determine the action type from the table above.
2. **Execute** — Run the matching command. Each command handles its own story searching, creation/update, and validation.
3. **Summarise** — Output a summary table:

```
| Story ID  | Title | Action                  | Status |
|-----------|-------|-------------------------|--------|
| STORY-001 | ...   | created/updated/removed | ...    |
```
