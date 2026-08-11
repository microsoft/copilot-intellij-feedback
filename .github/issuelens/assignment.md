# IssueLens Assignment Instructions

Use these instructions when assigning issues in `microsoft/copilot-intellij-feedback`.

## Assignment Rule

1. Process only open issues that have no assignees. Re-fetch the feedback issue immediately before assigning it; if it already has an assignee, leave it unchanged.
2. Check whether the feedback issue links to or references an issue in the internal `microsoft/copilot-intellij` repository.
3. For each linked internal issue, read its current assignees.
4. If at least one linked internal issue has assignees, assign the feedback issue to the same GitHub users. When multiple linked internal issues exist, use the de-duplicated union of their assignees.
5. Do not remove or replace existing assignees.

Leave the feedback issue unchanged when it has no linked `microsoft/copilot-intellij` issue, the linked issue has no assignees, the internal issue cannot be read, or the feedback issue became assigned before the update.