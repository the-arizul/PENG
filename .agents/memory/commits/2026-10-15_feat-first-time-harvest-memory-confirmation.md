# Commit Memory: feat(memory): add first-time harvest memory confirmation modal (v1.5.2)

- **Date:** 2026-10-15
- **Commit:** Bundled in primary commit (HEAD)
- **Author:** ARIZUL
- **Workflow:** `[10] [LEARN]` & `Pre-Flight Checks`
- **Taxonomy Tag:** `[FEAT]` / `[PREFERENCE]`

## Executive Summary
Integrated an interactive confirmation modal for first-time users to decide whether to automatically commit harvest memory into Git, gating future activation and generation of the `AGENTS.md` Harvest memory instruction upon their approval.

## Point-by-Point Changes
- **First-Time Harvest Memory Confirmation Modal:** Added Step A modal sequence in Pre-Flight Session Checks prompting first-time users whether to commit harvest memory (`.agents/memory/` records & ledger) into Git commits.
- **Preference Persistence in `state.json`:** Persist `commit_harvest_memory: true/false` alongside `preferred_language` in `$HOME/.peng/state.json` and `.agents/state.json`.
- **Conditional Future Directive Activation:** If approved, the Harvest memory instruction in `AGENTS.md` is actively used across all future workflows, bundling harvested records directly into primary commits; if declined, harvest memory remains local and uncommitted.
- **Workflow 1 Context Init Gate:** When generating `.agents/AGENTS.md` for a codebase, only include the active Harvest memory instruction if the user approved committing harvest memory.
- **Release Version Bump:** Bumped PENG release version to 1.5.2 with updated changelog and documentation.

## Impacted Files
- `.agents/AGENTS.md` (Updated State Verification and Git History Harvester directives)
- `.agents/skills/peng/SKILL.md` (Updated Step A, Workflow 1 & 10 directives, version bump to 1.5.2)
- `README.md` (Updated State Verification documentation)
- `.agents/memory/COMMITS.md` (Prepended commit record entry)
- `.agents/memory/commits/2026-10-15_feat-first-time-harvest-memory-confirmation.md` (This record)

## Deterministic Verification & Diagnostics
- Syntax & markdown structural integrity verified across all modified files.
- Zero breaking changes to existing 14 PENG workflows.

## Extracted Living Rules
- `[PREFERENCE]` First-time users are prompted for confirmation before committing harvest memory. User approval gates whether the Harvest memory instruction in `AGENTS.md` is active in future workflows.
