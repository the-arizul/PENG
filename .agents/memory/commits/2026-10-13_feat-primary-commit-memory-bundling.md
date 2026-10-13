# Commit Memory: feat(memory): enforce primary commit bundling for commit and harvest memory (v1.5.1)

- **Date:** 2026-10-13
- **Commit:** Bundled in primary commit (HEAD)
- **Author:** ARIZUL
- **Workflow:** `[10] [LEARN]` & `Stage & Commit Engine`
- **Taxonomy Tag:** `[FEAT]` / `[CONTRACT]`

## Executive Summary
Enforced strict primary commit bundling for all automated commit memories and harvested git history, permanently prohibiting separate secondary memory commits and eliminating post-commit disk modifications that cause dirty working tree states.

## Point-by-Point Changes
- **Primary Commit Bundling (Zero Separate Commits):** Codified that `.agents/memory/commits/` records and `.agents/memory/COMMITS.md` entries must always be generated BEFORE committing and bundled directly inside the primary commit alongside code changes.
- **Harvest Memory Bundling:** Ensured that historical git commits harvested into living memory during a session or alongside code modifications are staged and sealed inside the primary commit rather than committed separately.
- **Eliminated Post-Commit Disk Dirtying:** Removed instructions that modified the memory record on disk after committing to record the hash, preventing dirty working trees that misled agents into triggering separate commits.
- **Release Version Bump:** Bumped PENG release version to 1.5.1 with updated changelogs.

## Impacted Files
- `.agents/AGENTS.md` (Updated Automated Commit Memory directive, Stage & Commit Engine, and Pre-Wrap handlers)
- `.agents/skills/peng/SKILL.md` (Updated Tip block, Stage & Commit Engine, Workflows [1] & [10] directives, version bump to 1.5.1)
- `README.md` (Updated feature description for atomic primary commit bundling)
- `.agents/memory/COMMITS.md` (Prepended commit record entry)
- `.agents/memory/commits/2026-10-13_feat-primary-commit-memory-bundling.md` (This record)

## Deterministic Verification & Diagnostics
- Syntax & markdown structural integrity verified across all modified files.
- Zero breaking changes to existing 14 PENG workflows.

## Extracted Living Rules
- `[CONTRACT]` Commit memory and harvest memory records MUST ALWAYS be generated before running `git commit` and sealed inside the single primary commit. Agents must NEVER execute a separate or follow-up commit for memory files.
