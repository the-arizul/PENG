---
name: peng
description: PENG Master Vibe Coding Prompt Toolkit. Access, manage, edit, or execute battle-tested prompts (Init, Circuit Breaker, Architect, Verify, Harmonize, Learn, Fresh Chat Context, Build Feature, Delete Feature, Deep Bug Hunter, Help) and easily add new custom prompts.
user-invocable: true
---

# PENG Master Vibe Coding Toolkit

A unified system for all high-leverage vibe coding workflows and pre-made prompts.

## ZERO-MEMORY INTERACTIVE MENU (MANDATORY AGENT RULE)
When the user invokes /peng or asks about peng without specifying a clear prompt:
The agent MUST IMMEDIATELY present the interactive selection menu with numbered options:
1. [1] Autonomous Context Init (Scan codebase & build .agents/ setup)
2. [2] Fresh Chat Context Primer (Quick-sync memory, active branch, and recent state)
3. [3] Build New Feature (Strict requirements breakdown, edge cases, and surgical execution)
4. [4] Delete / Deprecate Feature (Zero-dead-code purge: models, routes, migrations, UI, and tests)
5. [5] Deep Bug Hunter & Fixer (Scientific root-cause diagnosis and regression-free repair)
6. [6] Circuit Breaker (Halt all edits, revert hallucinations, isolate bug)
7. [7] Pre-Flight Architect (Formulate impacted files plan before coding)
8. [8] Pre-Commit Verify (Run tests, fix lint errors, clean git commit)
9. [9] Gold Standard Harmonizer (Mirror reference files conventions)
10. [10] Living Memory / Learn (Save session breakthrough to memory)
11. [11] Add or Edit a Prompt (Update this catalog)
12. [12] Help & Comprehensive User Guide (Detailed usage guidelines & best practices)

The user only needs to click the option or type the number (1-12). The user does NOT need to remember any keywords.

---

## Master Prompt Catalog & Usage Guide

### 1. [INIT] Autonomous Context Generator
- **Trigger:** /peng 1 or select 1 from /peng
- **When to Use:** 
  - First conversation after cloning or opening any new codebase.
  - When existing agent context feels outdated, fragmented, or unstructured.
  - When you want the agent to self-discover folder structures and gold standard files.
- **Goal & Value:**
  - Performs deep reconnaissance across package managers, frameworks, and architecture.
  - Discovers 2-3 cleanest 'Gold Standard' reference files to establish coding baselines.
  - Builds a compact, high-density .agents/AGENTS.md (< 150 lines) with an autonomous self-evolution directive.
- **Workflow:**
  1. Deep Codebase Reconnaissance: Detect runtimes, frameworks, directory structure, architectural patterns, project-specific quirks, test/lint commands, and identify 2-3 Gold Standard reference files.
  2. Initialize .agents/ Architecture: Ensure .agents/AGENTS.md, .agents/rules/, and .agents/skills/ exist.
  3. Generate .agents/AGENTS.md (< 150 lines) containing project summary, key commands, reference files, and self-evolution directive.
  4. Suggest user to commit .agents/ and start a fresh chat session for peak token efficiency.

---

### 2. [CONTEXT-PRIMER] Fresh Chat Context Primer
- **Trigger:** /peng 2 or select 2 from /peng
- **When to Use:**
  - Very first message when opening a new chat window.
  - After switching git branches or pulling remote updates.
  - When you want the agent aligned with the exact current state of the repo without wasting tokens.
- **Goal & Value:**
  - Prevents hallucination of outdated files or methods.
  - Fast-syncs current git status, recent commits, and core .agents/AGENTS.md guidelines.
- **Workflow:**
  1. Inspect Git & Environment State: Check current branch, uncommitted diffs, and recent commits.
  2. Ingest Living Memory: Read .agents/AGENTS.md and any active .agents/rules/.
  3. Context Confirmation: Provide a 3-bullet executive summary of the current repo posture and confirm readiness for the next task.

---

### 3. [FEATURE-BUILDER] Build New Feature (Surgical Implementation)
- **Trigger:** /peng 3 or select 3 from /peng
- **When to Use:**
  - Adding a brand-new end-to-end feature or business capability.
  - Implementing an API endpoint with UI components and database schema.
- **Goal & Value:**
  - Avoids haphazard code dumps.
  - Enforces requirements clarity, schema safety, and layered architecture.
- **Workflow:**
  1. Requirements Deconstruction: Ask user for feature specs if unclear; outline core user stories.
  2. Architectural Mapping: Define Database Layer -> Business Logic/Service Layer -> Controller/API -> Frontend/UI.
  3. Pre-Flight Approval: List exact new files and modified files. Wait for user green light.
  4. Surgical Execution: Write clean, type-safe, and validated code mirroring Gold Standard conventions.
  5. Verification: Trigger test suites and confirm feature works end-to-end.

---

### 4. [FEATURE-PURGE] Delete / Deprecate Feature (Zero Dead-Code Purge)
- **Trigger:** /peng 4 or select 4 from /peng
- **When to Use:**
  - Sunsetting an old feature, obsolete API, or deprecated UI screen.
  - Removing a third-party integration or payment gateway completely.
- **Goal & Value:**
  - Prevents 'code rot' and ghost references that silently break future builds.
  - Thoroughly identifies all dependencies, imports, database columns, route definitions, and test fixtures.
- **Workflow:**
  1. Blast-Radius Audit: Deeply grep for all references across routes, controllers, models, views, styles, seeders, and tests.
  2. Deletion Impact Matrix: Present the exact list of lines and files to be removed, plus database migration needed to drop obsolete columns/tables.
  3. Safe Execution: Delete obsolete code and run migrations.
  4. Dead-Code Verification: Run static analysis and linters to guarantee zero broken imports or orphaned references.

---

### 5. [BUG-HUNTER] Deep Bug Hunter & Fixer
- **Trigger:** /peng 5 or select 5 from /peng
- **When to Use:**
  - When encountering an elusive bug, race condition, 500 error, or unexpected UI glitch.
  - Before making blind guesses or random trial-and-error edits.
- **Goal & Value:**
  - Applies first-principles debugging. Isolates root cause before touching core files.
  - Guarantees that the fix does not create regressions elsewhere.
- **Workflow:**
  1. Symptom & Environment Ingestion: Analyze error logs, stack traces, and reproduction steps.
  2. Root-Cause Analysis: Identify the exact logical gap or mismatch causing the behavior.
  3. Isolated Reproduction: Formulate a reproducing test case or diagnostic probe to confirm the bug.
  4. Surgical Patch: Apply the minimal, cleanest fix necessary.
  5. Regression Check: Run the full test suite to verify the bug is eliminated without side effects.

---

### 6. [CIRCUIT-BREAKER] Emergency Halt & Root-Cause Diagnosis
- **Trigger:** /peng 6 or select 6 from /peng
- **When to Use:**
  - When the agent is trapped in an edit loop and failing to fix the same error repeatedly.
  - When a bug fix breaks 2-3 other unrelated files or features.
- **Goal & Value:**
  - Prevents codebase destruction and saves hours of debugging time.
  - Discards uncommitted bad edits and forces an isolated diagnostic approach.
- **Workflow:**
  1. Immediate Code Freeze: Stop all production edits. Discard uncommitted changes from this loop.
  2. False Assumption Autopsy: State the incorrect assumption that caused the failure.
  3. Two Hypotheses: Formulate 2 distinct hypotheses explaining the issue.
  4. Isolated Verification: Write a temporary diagnostic script or targeted logging to verify the true hypothesis before touching production code.
  5. Wait for user review and signal.

---

### 7. [ARCHITECT] Strict Pre-Flight Architecture Review
- **Trigger:** /peng 7 or select 7 from /peng
- **When to Use:**
  - Before building any major feature or multi-file module.
  - Before large refactorings, database schema alterations, or major dependency upgrades.
- **Goal & Value:**
  - Eliminates unintended side-effects and prevents touching out-of-scope files.
  - Gives you complete visibility and veto power before code is written.
- **Workflow:**
  1. Scope Definition: Analyze feature requirements and determine minimal touchpoints.
  2. Impact Matrix: List exact files to create, modify, or delete.
  3. Dependency Mapping: Identify affected APIs, database models, queues, and state flows.
  4. Risk Assessment: Identify 2 potential breaking changes or edge cases.
  5. Execution Sequence: Outline sequential steps.
  6. Gatekeeper Approval: STOP and wait for approval before generating code.

---

### 8. [VERIFY] Self-Correction & Pre-Commit Audit
- **Trigger:** /peng 8 or select 8 from /peng
- **When to Use:**
  - Immediately after code generation is complete, right before committing to Git.
  - Before opening a Pull Request or deploying code.
- **Goal & Value:**
  - Ensures production readiness without manual code scanning.
  - Cleans up leftover debug logs, temporary print statements, and lint warnings.
- **Workflow:**
  1. Automated Verification: Run project test suites, static analyzers, and build tools (e.g., phpunit, flutter test, npm test, npm run build).
  2. Autonomous Correction: Diagnose and fix errors autonomously without changing business logic.
  3. Hygiene Cleanup: Remove all debug prints, dd(), dump(), console.log(), and temporary scripts.
  4. Audit Report: Present final test status and clean git diff summary.

---

### 9. [HARMONIZE] Gold Standard Style Harmonizer
- **Trigger:** /peng 9 or select 9 from /peng
- **When to Use:**
  - Writing a new controller, service, repository, model, or UI component.
  - When you notice the agent writing generic code that does not match your codebase vibe.
- **Goal & Value:**
  - Prevents 'Style Drift' and maintains 100% architectural uniformity.
  - Guarantees that new files look like they were written by the original author.
- **Workflow:**
  1. Reference Identification: Locate the designated Gold Standard file in .agents/AGENTS.md.
  2. Pattern Extraction: Analyze naming conventions, error handling, validation structures, return types, dependency injection, and styling tokens.
  3. Faithful Replication: Write new code strictly mirroring that exact structure and elegance.

---

### 10. [LEARN] Session Living Memory Extractor
- **Trigger:** /peng 10 or select 10 from /peng
- **When to Use:**
  - At the end of a session where a tough, elusive bug was solved.
  - After completing a complex setup or discovering an undocumented repo quirk.
- **Goal & Value:**
  - Turns temporary session insights into permanent repository memory.
  - Guarantees the agent will never repeat the same mistake in future chats.
- **Workflow:**
  1. Insight Extraction: Summarize key decisions, tricks, or edge-cases in 2-3 concise bullet points.
  2. Living Docs Update: Add a high-density 1-2 line rule to .agents/AGENTS.md to prevent future regressions.
  3. Workflow Persistence: Save or update a reusable skill in .agents/skills/.
  4. Persistence Confirmation: Confirm what was saved to project memory.

---

### 11. [CUSTOM] Add or Edit a Prompt
- **Trigger:** /peng 11 or select 11 from /peng
- **When to Use:**
  - Whenever you have a new repetitive prompt workflow you want to standardize.
  - When modifying any existing prompt rule or instructions.
- **Goal & Value:**
  - Keeps the prompt toolkit alive, extensible, and tailored specifically to your workflow.
- **Workflow:**
  1. Ask user for prompt name, when to use, goal, and workflow details.
  2. Append or update the prompt section in this file directly.

---

### 12. [HELP] Help & Comprehensive User Guide
- **Trigger:** /peng 12 or select 12 from /peng
- **When to Use:**
  - When you want an in-depth understanding of how to maximize Vibe Coding productivity.
  - When deciding which workflow to choose for your current task.
- **Goal & Value:**
  - Serves as the ultimate master manual for pairing with AI coding agents.
  - Teaches practical best practices on context lifecycle, git hygiene, and steering techniques.
- **Workflow:**
  1. Present the comprehensive Vibe Coding Master Guide covering:
     - Core Vibe Coding Philosophy: Steering vs. typing, and maintaining engineering rigor.
     - Context Hygiene: The lifecycle rule (Plan -> Code -> Verify -> Git Commit -> Clean Chat).
     - Workflow Matrix: Detailed breakdown of when and why to trigger Options 1 through 11.
     - Autonomous Memory System: How .agents/AGENTS.md, skills, and rules cooperate without overwhelming token limits.
     - Troubleshooting Guide: What to do when an agent loops, hallucinates, or breaks code.
