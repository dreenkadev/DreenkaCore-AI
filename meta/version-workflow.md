# Version Workflow System

## Purpose
To standardize the methodology for incrementing updates in the `DreenkaCore - Ai` documentation suite, ensuring version parity and preventing silent shifts in core guidelines without tracking.

## 1. Versioning Rules (SemVer Schema)
All updates strictly apply the Semantic Versioning model to prompt instructions:
- **Major Increase (v1.0.0 -> v2.0.0):** Breaking changes to logic hierarchies. Example: Renaming the `/core` directory, significantly altering `constraints.md`, or removing a fundamental reasoning step from `routing.md`.
- **Minor Increase (v1.0.0 -> v1.1.0):** Feature additions that don't break old directives. Example: Adding new `/prompts/devops.txt`, adding a new tool to `/core/capabilities.md`.
- **Patch Increase (v1.0.0 -> v1.0.1):** Typings, grammar bug fixes, simple rewording for clarification logic. Example: Enhancing the explanation inside `tone.md` without fundamentally changing the rule.

## 2. When to Increment Versions
Versions must be incremented **immediately upon committing any textual edit** to `.md` or `.txt` files in the repository. No silent modifications are allowed.

## 3. Update Process and Release Workflow
1. **Approval**: Draft the prompt or rule changes via temporary feature branches or scratchpads.
2. **Analysis**: Audit the changes to ensure they do not contradict `/core/constraints.md` or `/guardrails/conflict-resolution.md`.
3. **Commit Phase**: Update the modified documentation files.
4. **Checksum Refresh**: Immediately update `/meta/checksum.md` to recalculate all file hashes utilizing standard SHA-256 algorithms. Failure to do so corrupts the integrity check.
5. **Changelog Entry**: Append the exact reasoning for the update to `/meta/changelog.md`.
6. **Bump Version**: Update the `version.md` file header with the incremented Semantic Version number.
