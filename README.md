# roadmap-phase-normalizer skill repo

Repository ready for installation with `npx skills`.

## Structure

- `roadmap-phase-normalizer/SKILL.md`
- `roadmap-phase-normalizer/agents/openai.yaml`
- `roadmap-phase-normalizer/references/report-template.md`

## Important Changes Documented

- Added deterministic workflow to diagnose roadmap reality vs. plan.
- Added abandoned/stale work detection with evidence rules.
- Added dependency drift classification (`Core`, `Questionable`, `Legacy`).
- Added normalized next-phase model with entry/exit/kill criteria.
- Added report template: `roadmap-phase-normalizer/references/report-template.md`.

## Installation via npx skills

After publishing this repository to GitHub:

```bash
npx skills add Jpkovas/roadmap-phase-normalizer
```

To install directly without an interactive prompt:

```bash
npx skills add Jpkovas/roadmap-phase-normalizer --skill roadmap-phase-normalizer -y
```

## Quick verification

List skills available in the repository:

```bash
npx skills add Jpkovas/roadmap-phase-normalizer --list
```
