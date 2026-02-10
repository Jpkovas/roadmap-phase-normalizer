---
name: roadmap-phase-normalizer
description: Diagnose roadmap reality versus plan, identify abandoned or stale work, and normalize upcoming phases into execution-ready slices with explicit entry/exit criteria. Use when asked to check project roadmap status, find abandoned efforts, clean legacy dependency decisions, or rebuild next phases (roadmap, fase, abandonado, dependencias legadas, tech debt planning).
---

# Roadmap Phase Normalizer

Map current project reality to an actionable roadmap. Focus on evidence from code, docs, issues, and dependency manifests. Avoid speculation.

## Workflow

## 1) Collect Scope and Sources

Ask for or locate these sources:
- Roadmap artifacts (`README`, `docs/roadmap*`, project board exports, milestones, issue labels)
- Delivery signals (recent PRs, release notes, changelog)
- Dependency manifests (`package.json`, `requirements*.txt`, `pyproject.toml`, `go.mod`, lockfiles)
- Work backlog (`TODO`, `FIXME`, `WIP`, draft branches, stale issues)

If roadmap artifacts are missing, infer roadmap themes from implemented modules and open work items.

## 2) Build the Roadmap Reality Matrix

Create a matrix with one row per planned initiative and classify each row as:
- `Delivered`
- `In progress`
- `Planned but untouched`
- `Abandoned/stale`
- `Unknown`

Require evidence for each classification:
- File paths and line references
- Issue/PR IDs
- Commit recency and activity signals

## 3) Detect Abandoned Work

Flag an item as `Abandoned/stale` when at least two signals are true:
- Last relevant code change is old relative to active areas
- Open issue/epic has no meaningful movement
- Partial scaffolding exists but no integration path
- Dependency/tooling was introduced only for that unfinished effort

Document the likely abandonment reason as one of:
- Scope drift
- Priority change
- Technical blocker
- Ownership gap
- Cost > value

## 4) Audit Legacy Dependency Drift

Compare dependencies to actual use and current roadmap:
- Find direct imports/usages in source
- Cross-check scripts, CI, and build configs
- Identify packages installed for abandoned experiments

Classify each dependency:
- `Core`: required by current delivered/in-progress phases
- `Questionable`: low or indirect usage, needs owner confirmation
- `Legacy`: tied to abandoned work, candidate for removal

Never recommend installing or reintroducing dependencies only because they existed in the past.

## 5) Normalize Next Phases

Create concise, execution-ready phases. For each next phase define:
- Objective (one sentence)
- In-scope outcomes
- Out-of-scope guardrails
- Prerequisites and owners
- Entry criteria
- Exit criteria (Definition of Done)
- Kill criteria (when to stop and de-scope)

Split oversized phases into thin vertical slices that can be validated quickly.

## 6) Output Deliverable

Use the report template in `references/report-template.md`.
Keep recommendations high signal and evidence-linked.

## Quality Rules

- Prefer deterministic evidence over narrative guesses.
- Mark uncertainty explicitly as `Assumption`.
- Include file references whenever possible.
- Keep the plan biased to simplification and dependency minimization.
