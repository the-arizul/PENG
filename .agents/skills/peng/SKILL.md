---
name: peng
description: PENG Master Vibe Coding Prompt Toolkit. Access, manage, edit, or execute battle-tested prompts (Init, Circuit Breaker, Architect, Verify, Harmonize, Learn, Help) and easily add new custom prompts.
user-invocable: true
---

# PENG Master Vibe Coding Toolkit

A unified system for all high-leverage vibe coding workflows and pre-made prompts.

## ZERO-MEMORY INTERACTIVE MENU (MANDATORY AGENT RULE)
When the user invokes /peng or asks about peng without specifying a clear prompt:
The agent MUST IMMEDIATELY present the interactive selection menu with numbered options:
1. [1] Autonomous Context Init (Scan codebase & build .agents/ setup)
2. [2] Circuit Breaker (Halt all edits, revert hallucinations, isolate bug)
3. [3] Pre-Flight Architect (Formulate impacted files plan before coding)
4. [4] Pre-Commit Verify (Run tests, fix lint errors, clean git commit)
5. [5] Gold Standard Harmonizer (Mirror reference files conventions)
6. [6] Living Memory / Learn (Save session breakthrough to memory)
7. [7] Add or Edit a Prompt (Update this catalog)
8. [8] Help & Comprehensive User Guide (Detailed usage guidelines & best practices)

The user only needs to click the option or type the number (1-8). The user does NOT need to remember any keywords.

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

### 2. [CIRCUIT-BREAKER] Emergency Halt & Root-Cause Diagnosis
- **Trigger:** /peng 2 or select 2 from /peng
- **When to Use:**
  - When the agent is trapped in an edit loop and failing to fix the same error repeatedly.
  - When a bug fix breaks 2-3 other unrelated files or features.
  - When you suspect the agent is hallucinating APIs or missing the actual root cause.
- **Goal & Value:**
  - Prevents codebase destruction and saves hours of debugging time.
  - Discards uncommitted bad edits and forces a scientific diagnostic approach.
- **Workflow:**
  1. Immediate Code Freeze: Stop all production edits. Revert or discard uncommitted changes made during this failure loop.
  2. False Assumption Autopsy: Explicitly state the incorrect assumption that caused the failure.
  3. Two Alternative Hypotheses: Formulate 2 distinct hypotheses explaining the issue.
  4. Isolated Verification: Write a minimal, temporary diagnostic script or targeted logging to verify the true hypothesis before touching production code.
  5. Wait for user review and signal.

---

### 3. [ARCHITECT] Strict Pre-Flight Architecture Review
- **Trigger:** /peng 3 or select 3 from /peng
- **When to Use:**
  - Before building any major feature or multi-file module.
  - Before large refactorings, database schema alterations, or major dependency upgrades.
  - Whenever you want strict control over what the agent is allowed to touch.
- **Goal & Value:**
  - Eliminates unintended side-effects and prevents the agent from modifying out-of-scope files.
  - Gives you complete visibility and veto power before a single line of code is written.
- **Workflow:**
  1. Scope Definition: Analyze feature requirements and determine minimal touchpoints.
  2. Impact Matrix: List exact files to create, modify, or delete.
  3. Dependency Mapping: Identify affected APIs, database models, background queues, and state management flows.
  4. Risk Assessment: Identify 2 potential breaking changes or edge cases.
  5. Execution Sequence: Outline sequential steps.
  6. Gatekeeper Approval: STOP and wait for explicit user review and approval before generating code.

---

### 4. [VERIFY] Self-Correction & Pre-Commit Audit
- **Trigger:** /peng 4 or select 4 from /peng
- **When to Use:**
  - Immediately after code generation is complete, right before committing to Git.
  - Before opening a Pull Request or deploying code.
  - When you want to ensure zero regression across the existing test suite.
- **Goal & Value:**
  - Ensures production readiness without manual code scanning.
  - Cleans up leftover debug logs, temporary print statements, and lint warnings.
- **Workflow:**
  1. Automated Verification: Run the project test suites, static analyzers, and build tools (e.g., phpunit, flutter test, npm test, npm run build).
  2. Autonomous Correction: If any test fails, diagnose and fix the error autonomously without changing business logic.
  3. Hygiene Cleanup: Remove all debug prints, dd(), dump(), console.log(), and temporary test scripts.
  4. Audit Report: Present final test status and clean git diff summary.

---

### 5. [HARMONIZE] Gold Standard Style Harmonizer
- **Trigger:** /peng 5 or select 5 from /peng
- **When to Use:**
  - Writing a new controller, service, repository, model, or UI component.
  - When working on a team project with strict code style conventions.
  - When you notice the agent writing generic code that does not match your codebase vibe.
- **Goal & Value:**
  - Prevents 'Style Drift' and maintains 100% architectural uniformity.
  - Guarantees that new files look like they were written by the original author.
- **Workflow:**
  1. Reference Identification: Locate the designated Gold Standard file in .agents/AGENTS.md or as specified by the user.
  2. Pattern Extraction: Analyze naming conventions, error handling, validation structures, return types, dependency injection, and styling tokens.
  3. Faithful Replication: Write new code strictly mirroring that exact structure and elegance without introducing unapproved patterns or packages.

---

### 6. [LEARN] Session Living Memory Extractor
- **Trigger:** /peng 6 or select 6 from /peng
- **When to Use:**
  - At the end of a session where a tough, elusive bug was solved.
  - After completing a complex setup or discovering an undocumented repo quirk.
  - Right before closing a chat window so future chats remember the discovery.
- **Goal & Value:**
  - Turns temporary session insights into permanent repository memory.
  - Guarantees the agent will never repeat the same mistake in future chats.
- **Workflow:**
  1. Insight Extraction: Summarize the key architectural decision, trick, or edge-case in 2-3 concise bullet points.
  2. Living Docs Update: Add a high-density 1-2 line rule to .agents/AGENTS.md to prevent future regressions.
  3. Workflow Persistence: If a multi-step procedure was discovered, save or update a reusable skill in .agents/skills/.
  4. Persistence Confirmation: Confirm what was saved to project memory.

---

### 7. [CUSTOM] Add or Edit a Prompt
- **Trigger:** /peng 7 or select 7 from /peng
- **When to Use:**
  - Whenever you have a new repetitive prompt workflow you want to standardize.
  - When modifying any existing prompt rule or instructions.
- **Goal & Value:**
  - Keeps the prompt toolkit alive, extensible, and tailored specifically to your workflow.
- **Workflow:**
  1. Ask user for prompt name, when to use, goal, and workflow details.
  2. Append or update the prompt section in this file directly.

---

### 8. [HELP] Help & Comprehensive User Guide
- **Trigger:** /peng 8 or select 8 from /peng
- **When to Use:**
  - When you want an in-depth understanding of how to maximize Vibe Coding productivity.
  - When deciding which workflow to choose for your current task.
  - When troubleshooting agent drift, token bloat, or context degradation.
- **Goal & Value:**
  - Serves as the ultimate master manual for pairing with AI coding agents.
  - Teaches practical best practices on context lifecycle, git hygiene, and steering techniques.
- **Workflow:**
  1. Present the comprehensive Vibe Coding Master Guide covering:
     - Core Vibe Coding Philosophy: Steering vs. typing, and maintaining engineering rigor.
     - Context Hygiene: The lifecycle rule (Plan -> Code -> Verify -> Git Commit -> Clean Chat).
     - Workflow Matrix: Detailed breakdown of when and why to trigger Options 1 through 7.
     - Autonomous Memory System: How .agents/AGENTS.md, skills, and rules cooperate without overwhelming token limits.
     - Troubleshooting Guide: What to do when an agent loops, hallucinates, or breaks code.
