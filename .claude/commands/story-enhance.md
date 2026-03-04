# /story-enhance

Enhance existing user stories for a feature change.

## Input

The user will provide: **$ARGUMENTS**

## Steps

1. Find existing stories in `docs/stories/` related to the feature.
2. Update relevant stories:
   - Add an `## Updates` section at the bottom with the date and description of the change.
   - Revise acceptance criteria if scope changed.
   - Set **Status** to `updated`.
3. If new stories are needed, create them using `.claude/skills/story-template.md` and reference the originals under **Dependencies**.
4. Run `/story-validation` on every affected file.
