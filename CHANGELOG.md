# Changelog

## 2026-03-07
- Hardened the skill against indirect prompt injection from issues, PRs, project boards, milestones, changelogs, and similar collaboration artifacts.
- Added an explicit source trust model and required cross-checking untrusted metadata against trusted local repository evidence.
- Updated the reporting contract so untrusted collaboration data is referenced as sanitized context, not as executable or authoritative instructions.
