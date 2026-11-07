# Git Rules

## Commits

- Make one commit per theme. Keep a change in the same commit as the changes it needs to work, so that each commit leaves the project in a working state.
- Never add `Co-Authored-By: Claude` or any other AI attribution to commit messages, PR descriptions, or any other artifact, in any repository.

## Ignored Files

- In `.gitignore`, list only commonly ignored files and data files or folders that the repository's purpose clearly requires. Put everything else in `.git/info/exclude`.

## CI

- Run the project's lint, type check, and test commands in CI on pull requests and pushes to the default branch, and require them to pass before merging.
- Grant workflows read-only permissions by default, and pin third-party actions to full commit SHAs.
