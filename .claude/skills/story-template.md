# Story Template

The canonical template for user story files in `docs/stories/`.

## Template

```markdown
# STORY-<NNN>: <Title>

**Feature**: <parent feature name>
**Status**: pending
**Created**: <YYYY-MM-DD>

## User Story

As a [role], I want [capability], so that [benefit].

## Acceptance Criteria

1. ...
2. ...
3. ...

## Technical Notes

- ...

## Dependencies

- None
```

## Naming Convention

- Filename pattern: `STORY-<NNN>-<slug>.md`
- `<NNN>` — zero-padded to 3 digits
- `<slug>` — lowercase, hyphen-separated, no special characters
- Number in filename must match the title heading
