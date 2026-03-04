# /story-remove

Mark existing user stories as removed.

## Input

The user will provide: **$ARGUMENTS**

## Steps

1. Find existing stories in `docs/stories/` related to the feature.
2. Update each related story:
   - Set **Status** to `removed`.
   - Add an `## Updates` section with the date and removal reason.
3. Do NOT delete files — mark as removed for traceability.
4. Run `/story-validation` on every affected file.
