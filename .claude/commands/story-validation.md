# Story Validation

Validate all story files in `docs/stories/`.

1. Read every `STORY-*.md` file in `docs/stories/`.
2. Apply all checks below to each file.
3. Output the validation report table.
4. If any check fails, fix it automatically and re-validate until all pass.

## Required Fields

Every story file MUST contain:

1. **Title line** — `# STORY-<NNN>: <Title>` as first heading
2. **Feature** — non-empty value
3. **Status** — one of: `pending`, `in_progress`, `updated`, `removed`
4. **Created** — valid `YYYY-MM-DD` date
5. **User Story** section — "As a [role], I want [capability], so that [benefit]" format
6. **Acceptance Criteria** section — at least one numbered item
7. **Dependencies** section — must exist (can be "None")

## Naming Convention

- Filename pattern: `STORY-<NNN>-<slug>.md`
- `<NNN>` zero-padded to 3 digits
- `<slug>` lowercase, hyphen-separated, no special characters
- Number in filename must match title heading

## Cross-Story Checks

- No duplicate story numbers
- Dependencies must reference existing story IDs
- No circular dependencies

## Enhancement / Removal Checks

- Updated stories must have `## Updates` section with a dated entry
- Removed stories must keep original content intact above Updates

## Validation Output Format

```
Story Validation Report
=======================
| Story ID  | Check           | Result |
|-----------|-----------------|--------|
| STORY-001 | required fields | pass   |
| STORY-001 | naming          | pass   |
| STORY-001 | dependencies    | pass   |
```

If any check fails, show the reason, fix automatically, and re-validate until all pass.
