# FOUNDATION-ROLLBACK

This document covers rollback for changes made in this phase within `/home/runner/work/.github/.github`.

## General rollback rule

- Use follow-up commits that revert or restore prior file contents.
- Do not rewrite history.
- Do not delete issue history or PR discussion.
- Obtain owner approval before reverting any change that other repositories have already adopted.

## Rollback by change type

| Change type | Rollback method | Notes |
|---|---|---|
| Added documentation file | Remove the file in a follow-up commit or replace it with approved prior content | Safe and reversible |
| Updated existing markdown file | Restore the previous version from git history in a follow-up commit | Preserve audit trail |
| Added issue form | Remove or supersede the form in a follow-up commit | Verify template links still work |
| Updated issue form | Restore the prior YAML version from git history | Re-validate YAML after restoration |
| Updated PR template | Restore the previous template content from git history | Confirm reviewers retain required fields |
| Added CODEOWNERS | Remove or adjust the file in a follow-up commit if routing is incorrect | Coordinate with review owners |

## Recovery sequence

1. Identify the specific file or document to restore.
2. Inspect the previous committed version with git history.
3. Apply a focused revert commit on a feature branch.
4. Re-run YAML and markdown validation relevant to the reverted files.
5. Open a follow-up pull request documenting why the rollback is needed.
