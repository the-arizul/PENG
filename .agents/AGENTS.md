# AntiGravity PENG - Master Vibe Coding Toolkit

This repository contains the unified **PENG Master Vibe Coding System** for Antigravity IDE and universal AI coding agents.

## TOP-PRIORITY CAREFUL EXECUTION & MANDATORY SYNTAX RECHECK DIRECTIVE (ABSOLUTE HIGHEST RULE)
**ABSOLUTE HIGHEST PRIORITY DIRECTIVE:** When executing ANY task with PENG (feature development, bug fixes, refactoring, deletions, or configuration changes):
1. **Extreme Care & Diligence on All Code Changes:** Every code edit, modification, refactor, and addition across every file MUST be executed with extreme care. No existing working function, feature, API contract, UI behavior, or application logic may EVER be broken. The agent must verify existing functionality and guarantee zero regressions on every task.
2. **Mandatory Syntax Error & Diagnostics Recheck (Always Before Ending Task):** Before declaring ANY task finished, handing off to the user, or ending an interaction, the agent MUST ALWAYS thoroughly recheck all modified and related files for syntax errors, compile errors, parse errors, unclosed brackets/tags, missing imports, or linter regressions.
3. **Automated & Static Probe Verification:** Run relevant language-specific syntax checks, diagnostic probes, linters, or typecheckers (e.g. `php -l` for PHP, `node --check` / `tsc --noEmit` / linter for JS/TS, `python -m py_compile` for Python, `cargo check` for Rust, `go vet` for Go, etc.) or check IDE diagnostic feedback before presenting completion to the user. No task may ever conclude with unverified code or silent syntax breakages.

## MANDATORY DEEP SCAN & COMPLETE FEATURE REMOVAL DIRECTIVE
Whenever the user asks to remove, delete, clean up, or purge ANY feature, component, route, service, module, or code artifact:
1. **Deep Scan First (Full Discovery):** The agent MUST execute a comprehensive deep scan across the entire codebase (routes, controllers, models, services, migrations, config files, frontend components, templates, styles, imports, event listeners, seeders, tests, and documentation).
2. **List Associated Files:** Prior to deleting or during the purge report, explicitly present the complete list of all associated files, references, database touchpoints, and imports discovered.
3. **Complete & Clean Purge:** Completely remove them and surgically clean all dead imports, unused registrations, and references so no broken links or half-deleted artifacts remain.
4. **Mandatory Rescan Prompt:** Immediately after completion, the agent MUST present/ask the user to run a rescan (`Rescan - if there's any leftover (that can cause issues in future)`) via the Level 4 Context Menu to verify blast radius and guarantee zero leftover dead code or broken references.

## MANDATORY CONTENT TEXT RENDERING BEFORE CONTEXT MENU MODAL DIRECTIVE (ZERO-GHOSTING / NO-FALSE-CLAIM RULE)
**CRITICAL MANDATORY DIRECTIVE:** Whenever ANY context menu option is selected that produces an output, guide, explanation, autopsy report, impact matrix, rescan summary, or commit breakdown (e.g. `How do I check or test the changes?`, `What is this for?`, `Rescan - if there's any leftover`, `Stage & Commit Changes`, `Save Breakthrough to Living Memory`, `Circuit Breaker Autopsy`, `Pre-Flight Architect Impact Matrix`, etc.):
1. **Mandatory Full Text Output First:** The agent MUST write and render the complete, comprehensive markdown text of that guide, report, explanation, or summary directly in the chat turn response text FIRST.
2. **Never Skip or Suppress Text Output:** Under NO circumstances may the agent launch `ask_question` with a generic claim (such as *"Verification guide generated! How would you like to proceed?"* or *"Report ready!"*) without displaying the actual full step-by-step content text on screen in the exact same response!
3. **Execution Sequence:** Always write out the detailed text content in the chat turn response FIRST, and THEN launch the follow-up context menu (`ask_question`). Ghosting content or claiming something was generated without printing it in the chat response is strictly FORBIDDEN as a false-output violation.

## SCOPE BOUNDING & ZERO-SILENT-EXPANSION DIRECTIVE (ORGANIC DEVELOPMENT PRINCIPLE)
**MANDATORY DIRECTIVE:** The agent MUST strictly bound its execution to the requested and authorized scope:
1. **Read-Only Inquiries & Explorations:** Explanations, architectural reviews, investigations, and questions are strictly READ-ONLY. The agent MUST NOT alter code during an investigation unless explicit implementation authorization is provided.
2. **Zero Silent Expansion:** When unexpected bugs, latent defects, edge cases, or refactoring opportunities are discovered during an authorized task, the agent MUST NEVER silently expand scope or perform unprompted rewrites.
3. **Observation Logging & Controlled Follow-Up:** Log all discovered side-items in the **Discovered Observations / Future Items** section of the wrap-up summary and offer them as follow-up choices via the interactive context menu.

## DETERMINISTIC VERIFICATION RECEIPT DIRECTIVE (PROOF OF INTEGRITY)
**MANDATORY DIRECTIVE:** Whenever concluding ANY feature implementation, bug fix, refactoring, or pre-commit verification (prior to triggering the Level 4 Wrap-Up Context Menu), the agent MUST output a structured **Verification Receipt** markdown table/block in the chat response text:
1. **Scope Authorization:** Stated bounds of what was requested and authorized.
2. **Automated & Static Probes:** Explicit record of syntax checks (`php -l`, `node --check`, `python -m py_compile`, etc.), linters, type checks, or test suites executed with passing status.
3. **Functional & Contract Proof:** Evidence that existing APIs, routes, UI components, and contracts remain intact.
4. **Zero-Regression & Blast-Radius Status:** Verified that untouched code/features have zero side-effect breakages.
5. **Discovered Observations / Future Items:** Non-blocking findings recorded for later consideration.

## 3-TIER HYPER-MEMORY & DUAL-LAYER STORAGE DIRECTIVE
**MANDATORY DIRECTIVE:** Project and session memory MUST be organized across a 3-tier hyperdimensional taxonomy:
1. **Tier 1 — Episodic Memory (Session Fixes & Autopsies):** Captured in session histories, autopsy records, and memory entries detailing specific bug fixes, quirks, and gotchas (`[FIX/TRICK]`).
2. **Tier 2 — Semantic Memory (Active Project Truth):** Structured living rules in `.agents/rules/` (`architecture.md`, `design-system.md`, `backend-api.md`, `adr-*.md`) detailing visual tokens, API schemas, and architectural boundaries (`[DECISION]`, `[CONTRACT]`, `[CONVENTION]`).
3. **Tier 3 — Procedural Memory (Behavioral Preferences & Style):** Developer preferences, commit styles, testing modes, and review rigor captured in `state.json` or `.agents/rules/preferences.md` (`[PREFERENCE]`).
4. **Contradiction & Superseded Tracking (`[SUPERSEDES]`):** When an architectural decision evolves, the new record MUST explicitly link to the superseded pattern (`[SUPERSEDES: ADR-XXX]`) so the agent never resurrects abandoned patterns.
5. **Dual-Layer Sync Engine:** Git-synced `.agents/` files are the primary, portable single source of truth. When an MCP memory daemon (such as `iai-memory`) is detected in the environment, the agent automatically mirrors memory captures and recalls cross-session context via MCP stdio.

## AUTOMATED LIVING MEMORY & COGNITIVE SALIENCE DIRECTIVE (HIPPO-STYLE HEURISTICS)
**MANDATORY DIRECTIVE:** The agent MUST continuously and passively observe all workflow operations, diagnostic runs, code modifications, and user instructions for salient architectural and episodic insights without requiring manual prompting:
1. **Continuous Passive Observation (5 Sensory Triggers):**
   - **Trigger 1: Error-to-Green Transition (`[FIX/TRICK]`):** When a compiler error, diagnostic probe, or test failure is subsequently resolved by a targeted code change, the agent automatically captures the symptom, root cause, and remedy as a Tier 1 episodic trick.
   - **Trigger 2: Explicit Architectural Directives (`[CONTRACT]` / `[PREFERENCE]`):** When the user states hard architectural or behavioral constraints (e.g., *"always"*, *"never"*, *"from now on"*, *"convention is"*, *"must return"*, or commit/test formatting rules), the agent immediately abstracts them into Tier 2 living rules (`.agents/rules/`) or Tier 3 preferences (`state.json` / `preferences.md`).
   - **Trigger 3: Architectural Choices & ADRs (`[DECISION]`):** When new packages, database schemas, migration files, route structures, or state paradigms are introduced, the agent automatically synthesizes an Architectural Decision Record skeleton.
   - **Trigger 4: Superseded Conventions (`[SUPERSEDES: ADR-XXX]`):** When an established convention or rule is deliberately replaced by a new pattern, the agent explicitly marks the old standard as superseded to prevent regression loops.
   - **Trigger 5: Anti-Pattern Lessons (`[LESSON]`):** When the user corrects a mistaken assumption or hallucinated API, the agent extracts a negative constraint preventing future repetitions.
2. **Cognitive Salience Filter (Noise Gate):**
   - Automatically discards trivial edits (syntax typo fixes, routine formatting, boilerplate getters/setters).
   - Automatically cross-checks and deduplicates against existing `.agents/rules/` and `.agents/memory/` to avoid redundancy.
3. **Auto-Populated Wrap-Up Presentation (Zero User Authoring):**
   - Prior to opening any Level 4 Post-Resolution or Wrap-Up Context Menu, the agent renders a **`🧠 Auto-Detected Living Memory (Hippo Engine)`** summary block directly in the chat response text detailing any detected insights.
   - Pre-formulates the memory entries so the user has zero typing overhead, and offers 1-click consolidation into `.agents/rules/` or dedicated `.agents/memory/commits/` records.
4. **Single Atomic Primary Commit Bundling:**
   - Any auto-detected memory files or rule updates are staged alongside all code changes (`git add -A`) and sealed directly INSIDE the primary commit. ZERO separate memory commits.

## AUTOMATED COMMIT MEMORY & EPISODIC LEDGER DIRECTIVE (PURE MARKDOWN, ZERO-DB)
**MANDATORY DIRECTIVE:** All git commits executed via PENG MUST be automatically recorded as structured episodic memory records without external databases:
1. **Dedicated Commit Record Files (`.agents/memory/commits/`):** For every commit, create `.agents/memory/commits/YYYY-MM-DD_<slug>.md` capturing full metadata (date, author, workflow, taxonomy tag, commit slug), executive summary, point-by-point what & why, affected files with diff statistics, deterministic verification receipts, and living rules (`[DECISION]`, `[FIX/TRICK]`, `[CONTRACT]`).
2. **Master Chronological Ledger (`.agents/memory/COMMITS.md`):** Maintain a reverse-chronological markdown table (`Date | Commit | Tag | Workflow | Title | Memory Record`) linking to each individual commit memory record.
3. **Single Atomic Primary Commit Bundling (Zero-Separate-Commit Rule):**
   - The commit memory file and master ledger update (`.agents/memory/`) MUST be generated BEFORE running `git commit`, staged together with all code/project changes via `git add -A`, and sealed directly INSIDE the primary commit.
   - **STRICT PROHIBITION:** The agent MUST NEVER perform a separate, secondary, or follow-up commit for commit memory or harvest memory (e.g., NEVER commit code first and then run `git commit -m "docs: record commit memory"` or `git commit -m "chore: harvest git history"`).
   - The memory record is sealed in the primary commit from its inception. Do NOT attempt to modify the memory file on disk after `git commit` to insert the commit hash, as doing so dirties the working tree and triggers unwanted secondary commits. The commit hash is displayed in the sealed release summary in chat and can be viewed via `git log`.
4. **Git History Harvester & Harvest Memory Bundling:** Workflows [1], [2], and [10] provide an automated scanner to backfill past commits into `.agents/memory/commits/` and build `COMMITS.md` without requiring Hippo Memory or SQLite.
   - **First-Time Approval Gate:** First-time users see an interactive confirmation modal asking whether to commit harvest memory into Git. If approved (recorded as `commit_harvest_memory: true` in `state.json`), this instruction in `AGENTS.md` will be actively used in the future: whenever git history is harvested during an active session alongside other changes, the harvested memory files MUST be included directly inside the primary commit alongside all other work. If executed as a standalone task with no pending code edits, it is committed as a single primary commit (`docs(memory): harvest git commit history into living memory`), NEVER split across multiple commits.
   - If declined, harvest memory remains local and uncommitted.
5. **Surgical Undo Rollback:** When `Undo commit` (`git reset --soft HEAD~1`) is executed, the agent MUST automatically delete the created commit memory file and remove its row from `COMMITS.md` to ensure zero stale or desynced memory records.

## AUTONOMOUS VERSIONING & PRE-WRAP GIT COMMIT RULE (MANDATORY AGENT DIRECTIVE)

**STRICT RULE:** The agent MUST NOT update or bump the version in `SKILL.md` in advance before asking the user! The version in `SKILL.md` must only be updated AFTER the user responds to the `ask_question` modal.

Whenever the user finishes working on this project, completes an update, or indicates a session wrap-up:
The agent MUST IMMEDIATELY trigger an interactive context menu using `ask_question`:

- **Question:**  You have made updates to PENG. Would you like to bump the release version and commit the changes to Git now?
- **Options:**
  1. Yes, bump patch version & commit (e.g., 1.2.0 -> 1.2.1)
  2. Yes, bump minor version & commit (e.g., 1.2.0 -> 1.3.0)
  3. Commit current changes without bumping version
  4. All good? Ensure it first (Run sanity audit, verify changes, and confirm readiness)
  5. No, keep uncommitted for now

### Execution Handlers when User selects an option:
1. **Auto-Bump Version (Only if Option 1 or 2 selected):** Update the Version: X.Y.Z in SKILL.md (and release date & changelog summary).
2. **Sync Mirrors:** Sync the updated SKILL.md to workspace copies.
3. **Generate Commit Memory & Ledger (Pre-Commit):** Generate dedicated commit memory file `.agents/memory/commits/YYYY-MM-DD_<slug>.md` and prepend to `.agents/memory/COMMITS.md`.
4. **Git Commit with Best Practices (Single Atomic Primary Commit):** Stage all modified/created files AND memory files together (`git add -A`) and write a clean, professional commit message following **Conventional Commits & Git Best Practices** (Short Header: `<type>(<scope>): <short summary>`, blank line, structured Body with easy-to-understand point-by-point bullet points answering *what* changed and *why*, and breaking changes/release footer). Run `git commit`. The commit memory is sealed directly inside this primary commit — ZERO separate memory commits.
5. **Post-Commit Follow-Up & Undo Commit Modal (MANDATORY):** Immediately after commit execution, render the commit summary (Hash, Header, Body snippet) and launch an interactive follow-up menu via `ask_question`:
   - **Question:** 🚀 Git commit successful! [Commit: <hash>] How would you like to proceed?
   - **Options:**
     1. Undo commit (git reset --soft HEAD~1 - revert commit & keep changes staged)
     2. Push to remote repository (git push)
     3. Run the app/project
     4. Return to Primary Menu
6. **Undo Commit Handler:** If `Undo commit` is selected, run `git reset --soft HEAD~1` (and revert version bump if applicable), display confirmation `↩️ Commit <hash> undone. All changes are preserved in your working tree / staging index.`, and re-open the pre-wrap menu.

---

## ZERO-FILE-READ INSTANT EXECUTION DIRECTIVE (MANDATORY PERFORMANCE RULE)
- **Instant In-Memory Execution:** All PENG workflows, menus, prompts, and execution instructions are natively pre-loaded in active context memory through `AGENTS.md`.
- **Skip `view_file` on `SKILL.md`:** When the user selects an option from any level of the PENG context menu (Level 1, Level 2, Level 3, Level 4, or Help Guide), or invokes `/peng <action>`, the agent MUST NOT execute a `view_file` tool call to re-read `SKILL.md`.
- **Immediate Response:** Respond INSTANTLY to menu selections, prompts, and options using the context and rules already present in active memory. Only invoke `view_file` on `SKILL.md` if the user explicitly asks to edit, audit, or view the raw `SKILL.md` file itself.

---

## Invocation Modes: /peng

PENG supports two intelligent invocation modes, both preceded by automatic pre-flight checks on new conversations:

### Pre-Flight Session Checks (Every New Conversation)
Whenever `/peng` or `peng` is invoked at the start of a conversation:
- **Zero Command Clutter Directive:** Must execute as **EXACTLY ONE single combined probe command** behind the scenes. Never spam individual commands in the user's terminal/accordion.
- **Strict Execution Flow:** Update / Git check and State check occur **FIRST**. If updates exist, the update prompt is rendered first. Once resolved (or if already up to date), it transitions directly into the Level 1 Primary Menu.

1. **Push-Based Update Detection (`npx skills`):**
   - PENG does not require GitHub Releases or tags. It directly tracks commits pushed to `the-arizul/PENG` on GitHub via `git ls-remote`.
   - In projects using PENG as an installed skill, when newly pushed commits are detected, prompts via `ask_question`:
     * *"🚀 New updates have been pushed to PENG on GitHub! Would you like to update the skill now using npx skills?"*
     * Options: `Yes, update project skill (npx skills update peng -y)`, `Yes, update global skill (npx skills update peng -g -y)`, `No, keep current version for now`.
   - In the PENG source repo itself: If local is behind `origin/main`, prompts for instant `git pull`.
2. **State Verification (`state.json`):**
   - Verifies if `state.json` exists (`$HOME/.peng/state.json` or `.agents/state.json`).
   - If missing (First-Time User):
     * Launches the First-Time Welcome & Language Setup modal via `ask_question`.
     * Launches the **First-Time Harvest Memory Confirmation modal** via `ask_question`:
       - *Question:* "Would you like PENG to automatically commit harvest memory (.agents/memory/ records and ledger) into Git?"
       - *Options:*
         1. `Yes, commit harvest memory into primary commits (Recommended)`
         2. `No, keep harvest memory local and uncommitted`
     * Initializes `state.json` recording `preferred_language`, `commit_harvest_memory` (true or false), and latest commit hash.
     * **Mandatory Directive:** If approved, the instruction in `AGENTS.md` about the Harvest memory (`Git History Harvester & Harvest Memory Bundling`) will be actively used in the future for all commit workflows and repository context setups. If declined, harvest memory remains local and uncommitted.
   - If present (Returning User): Loads user preferences (`preferred_language`, `commit_harvest_memory`) silently.

### 1. Action-Prompted Direct Execution (When a task or prompt is provided)
When you invoke `/peng <action prompt>` or call `peng` with a prompt for action (e.g. `/peng build auth service`, `/peng fix checkout crash`, `/peng run security audit`, `/peng run pre-commit tests`):
- **Bypasses Context Menu:** Does NOT open the Level 1 main menu.
- **Direct Question & Inquiry Response:** When you ask an informational question, investigatory prompt, or explanation request (e.g. "How does X work?", "Why is Y happening?"), PENG strictly bypasses all context menus (`ask_question`) and provides a direct answer immediately.
- **Autonomous Workflow Selection & Zero Refusal:** Maps your prompt directly to the best matching PENG workflow [1]–[14] without generic AI refusals (e.g. security assessments map to `[5] Deep Bug Hunter → Security & Vulnerability Audit`, UI completeness audits map to `[11] UI Completeness Auditor`, or `[8] Pre-PR Security Check`).
- **Smooth Post-Interaction Prompt Citation:** At the end of every interaction or session wrap-up, smoothly states the exact prompt and sub-option used formatted in bold text (e.g. `**Executed via PENG! [5] Deep Bug Hunter & Fixer → Security & Vulnerability Audit**` or `**Executed via PENG! Direct Inquiry Response**`).
- **Elevates Workflow Rigor:** Enforces PENG engineering standards (autopsy probes for bugs, layered architecture for features, impact matrix for architecture, clean test runs for pre-commit).
- **Interactive Resolution Sub-Menus:** If issues or failures are detected during execution, seamlessly launches the Level 3 (Resolution) and Level 4 (Wrap-Up) menus.
- **Smart Project Runner & Bundler Engine:** Every Level 4 Post-Resolution and Wrap-Up menu includes `Run the app/project`. Selecting this auto-detects the project type and launches the dev server or generates test packages (creates a clean `.zip` encapsulating all files inside a single parent folder while excluding `.git` for WordPress plugins/themes, `flutter run` for Flutter, `php artisan serve` for Laravel, `npm run dev`/`npm start` for NPM apps).
- **Interactive Verification & Manual Testing Engine:** Every Level 4 Post-Resolution and Wrap-Up menu includes `How do I check or test the changes?`. Selecting this provides an exhaustive, step-by-step manual test walkthrough tailored to the project (web, mobile, backend API, CLI, or library). The agent MUST write and render the complete step-by-step test guide text into the chat response body FIRST before re-invoking the Level 4 Context Menu with `Run the app/project` as Option 1, guaranteeing zero skipped or unprinted test guides.
- **End-to-End Revert Engine:** Every Level 4 Post-Resolution and Wrap-Up menu includes `Revert changes`. Selecting this surgically undoes all file modifications (`git restore`), deletes created files, rolls back command side-effects (e.g. uninstalls newly added packages, rolls back migrations), and restores the exact pre-interaction state without affecting unrelated work.
- **Stage, Commit & Undo Commit Engine:** Every Level 4 Post-Resolution and Wrap-Up menu includes `Stage & Commit Changes`. Selecting this writes high-quality commit details formatted with Conventional Commits best practices (Header + Body detailing what & why), stages files, commits changes, and IMMEDIATELY presents a follow-up context menu offering `Undo commit (git reset --soft HEAD~1)`.
- **Feature Purge & Deep Scan Protocol:** When removing or purging any feature or artifact, PENG automatically executes an exhaustive deep scan across all layers, lists all associated files and references, purges them completely, and immediately prompts with `Rescan - if there's any leftover (that can cause issues in future)` to verify zero dead code or broken links remain.
- **Rescan Engine Directive:** Every Level 4 Post-Resolution and Wrap-Up menu always includes `Rescan - if there's any leftover` (or `Rescan & Verify`). Selecting this re-executes automated diagnostic probes, linters, and checks across modified files to guarantee zero remaining issues, syntax errors, or leftover debug artifacts.

### 2. Standalone & Mid-Conversation Context-Aware Invocation (When no prompt is provided)
When you type `/peng` or `peng` by itself:
- **Context-Aware Sub-Menu Detection:** Checks active conversation state. If an active workflow, unresolved diagnostic scan, or post-resolution wrap-up state exists in the current conversation, automatically re-opens the corresponding **Level 2, Level 3, or Level 4 Contextual Sub-Menu** directly (with a `Return to Top-Level Primary Menu` option).
- **Primary Menu Launch:** If in a fresh conversation or clean state without active context, opens the Level 1 Primary Menu immediately via `ask_question`.
- **Smart Contextual Sub-Menus:** Prompts you through Level 2 specialization with mandatory `What is this for?` explainers.

### Quick Reference & Usage Matrix

| Option | Workflow | When to Use (Usage Time) | Goal & Impact |
| :--- | :--- | :--- | :--- |
| **[1]** | **Autonomous Context Init** | First chat in a new codebase or restructuring agent context. | Deep scan manifests, visual tokens & contracts; generate progressive .agents/ AI Knowledge System (AGENTS.md + targeted .agents/rules/). |
| **[2]** | **Fresh Chat Context Primer** | Starting a new chat session on an active branch. | Fast-sync active branch, uncommitted diffs, recent commits, and living memory. |
| **[3]** | **Build New Feature** | Developing new capabilities or components. | End-to-end vertical slices, API data layer, UI components, or requirement interview. |
| **[4]** | **Delete / Deprecate Feature** | Cleaning up legacy or unused code. | Complete zero-dead-code purge: models, routes, migrations, UI. |
| **[5]** | **Deep Bug Hunter & Fixer** | Debugging complex issues, regressions, or heisenbugs. | Scientific root-cause autopsy, reproduction probes, and regression-free repair. |
| **[6]** | **Circuit Breaker** | Trapped in an edit loop, repeated failures, or breaking code. | Emergency freeze, revert hallucinations, and diagnose root cause safely. |
| **[7]** | **Pre-Flight Architect** | Before building a major feature, refactoring, or schema changes. | Formulates file impact matrix, edge cases, and execution order before touching code. |
| **[8]** | **Pre-Commit Verify** | After coding is complete, right before git commit / PR. | Runs test suites, fixes lint errors, cleans debug logs, and prepares clean commit. |
| **[9]** | **Gold Standard Harmonizer** | Writing new controllers, services, models, or UI components. | Mimics existing cleanest reference file for 100% architectural uniformity. |
| **[10]** | **Living Memory & Hippo Engine** | Continuous cognitive detection or session wrap-up after breakthroughs. | Automatically detects and consolidates breakthroughs, rules, and fixes into .agents/rules/ and .agents/memory/. |
| **[11]** | **UI & Feature Completeness Auditor** | Identifying disconnected UI elements, broken buttons, stubbed handlers, or half-implemented features. | Deep scan entire UI/UX layer, inspect forms/actions/states, report itemized audit table without altering code. |
| **[12]** | **Design System & Anti-Hardcode Architect** | Inconsistent UI, hardcoded values, arbitrary Tailwind classes, or duplicated logic. | Standardize on shared shadcn/ui components, eliminate hardcoding ("hardcoding is a crime"), extract clean abstractions. |
| **[13]** | **Add or Edit a Prompt** | Whenever you want to customize or expand this prompt toolkit. | Updates the master prompt catalog directly in SKILL.md. |
| **[14]** | **Settings, State Config & User Guide** | Managing PENG state config, toggling harvest memory, switching languages, or reading manual. | Interactive state.json manager, harvest memory toggle, language switcher, and master manual. |

---

## STAGE, COMMIT & UNDO COMMIT ENGINE (MANDATORY AGENT DIRECTIVE)

Whenever the user selects **`Stage & Commit Changes`** (or chooses to commit changes during session wrap-up or version release) from ANY context menu:
The agent MUST NOT output lazy, generic, or single-line commit messages (e.g., "update files" or "fix bug").
The agent MUST follow strict **Conventional Commits & Git Best Practices** when writing commit details, and MUST IMMEDIATELY trigger a post-commit context menu modal offering an **Undo commit** option (`git reset --soft HEAD~1`).

### 1. Git Inspection & Best-Practice Commit Construction:
1. **Inspect Working Tree & Diff:**
   - Execute `git status` and `git diff` (and `git diff --staged`) behind the scenes to inspect all modified, created, and deleted files.
2. **Formulate Conventional Commit Message:**
   - **Header Line (Title):** `<type>(<scope>): <short concise summary>`
     * **Type:** MUST be one of `feat`, `fix`, `docs`, `style`, `refactor`, `perf`, `test`, `chore`, `build`, `ci`, `revert`, `release`.
     * **Scope:** Optional identifier representing module/component (e.g., `auth`, `ui`, `api`, `cli`, `peng`).
     * **Title:** Must be short, concise, and punchy (under 50-72 characters), imperative mood, lowercase type, no trailing period.
   - **Blank Line**
   - **Body Section (Description - Point by Point & Easy to Understand):**
     * Clear, easy-to-read bullet points breaking down changes simply:
       - *What changed:* Specific functional & code changes implemented.
       - *Why:* Underlying technical rationale or problem resolved in simple terms.
       - Key architectural, component, or file highlights.
   - **Work-Unit Commit Discipline (Mandatory):**
     * **Atomic Delivery:** NEVER commit by file type alone (e.g. `models`, then `services`, then `tests`). A commit MUST represent a complete, functional behavior unit with its code, tests, and documentation bundled together.
     * **400-Line Slicing Guard:** If a planned task or feature forecasts >400 authored lines, slice the work into reviewable, sequential work-unit commits before executing.
   - **Footer Section (Optional):** Breaking changes (`BREAKING CHANGE: <desc>`) or issue references (`Refs: #123`).

### 2. Execution, Automated Commit Memory Recording & Sealed Commit Summary Output:
1. **Automated Commit Memory Generation (Pure Markdown, Zero DB) - BEFORE Commit:**
   - Ensure the directory `.agents/memory/commits/` exists (create if missing).
   - Generate a dedicated commit memory markdown file BEFORE running `git commit`:
     `.agents/memory/commits/YYYY-MM-DD_<slug>.md` (e.g., `.agents/memory/commits/2026-10-13_feat-auth.md`).
   - The file MUST capture:
     * **Header Metadata:** Date/time, author, active workflow (e.g., `[3] Feature Builder`), taxonomy tag (`[FEAT]`, `[FIX/TRICK]`, `[DECISION]`, `[CONTRACT]`, `[REFACTOR]`, `[PERF]`, `[DOCS]`), commit status (`Bundled in primary commit`).
     * **Executive Summary:** Short concise summary of the work unit.
     * **Point-by-Point Changes:** Structured bullets explaining *what* changed, *why*, and key architecture/file highlights.
     * **Impacted Files & Diff Stats:** List of modified, created, and deleted files with diff statistics (+/- lines).
     * **Deterministic Verification Receipt:** Syntax probes run (`php -l`, `node --check`, etc.), automated tests executed, zero-regression status.
     * **Living Rules / Extracted Learnings:** Any architectural decisions (`[DECISION]`), non-obvious fixes (`[FIX/TRICK]`), or data contracts (`[CONTRACT]`) discovered during this change.
2. **Master Chronological Ledger Update (`.agents/memory/COMMITS.md`):**
   - If `.agents/memory/COMMITS.md` does not exist, initialize it with a markdown table:
     `| Date | Commit | Tag | Workflow | Title | Memory Record |`
   - Prepend the new commit record row to the top of the ledger table linking to the dedicated file:
     `| YYYY-MM-DD | `HEAD` (bundled) | `[TAG]` | `[Workflow]` | <title> | [View Record](commits/<filename>.md) |`
3. **Atomic Work-Unit Staging & Single Primary Commit (ZERO Separate Memory Commits):**
   - Stage all code changes, version updates, AND the generated `.agents/memory/` files together in one single operation: `git add -A`.
   - Execute `git commit` ONCE using the multi-line Conventional Commit message format.
   - **STRICT PROHIBITION (Zero Separate Memory Commits):** Commit memory and harvest memory MUST ALWAYS be inside the primary commit. NEVER execute a separate or follow-up commit for memory. Do NOT modify the memory file on disk after committing (as modifying it creates dirty working tree changes that prompt secondary commits). The record is already sealed directly inside the primary commit itself.
4. **Display Sealed Release Summary:**
   - Output the clean, sealed release summary in the chat response showing Commit Hash (from `git rev-parse --short HEAD`), Header, Body bullets, Files Changed summary, and the clickable file link: `**Commit Memory Recorded (Bundled in Primary Commit):** [.agents/memory/commits/<filename>.md](file:///<absolute-path-to-file>)`.

### 3. Mandatory Post-Commit Follow-Up Context Menu (`Undo commit`):
- **IMMEDIATELY** after outputting the sealed commit summary, trigger an interactive context menu modal via `ask_question`:
  * **Question:** 🚀 Changes committed successfully! [Commit: <hash>] How would you like to proceed?
  * **Options:**
    1. Undo commit (git reset --soft HEAD~1 - revert commit & keep changes staged)
    2. Push changes to remote repository (git push)
    3. Run the app/project (Launch dev server or create test package)
    4. Save Breakthrough to Living Memory (Record pattern into .agents/AGENTS.md)
    5. Return to Primary Menu (Select another workflow)

### 4. Undo Commit Execution Handler:
When the user selects **Undo commit (git reset --soft HEAD~1)**:
1. Execute `git reset --soft HEAD~1`. This surgically undoes the commit while preserving all modified, created, and staged files intact in the staging index.
2. **Automated Commit Memory Rollback:** Surgically delete the generated commit memory file in `.agents/memory/commits/` and remove its corresponding row from `.agents/memory/COMMITS.md`, guaranteeing that no orphan or desynced memory records remain.
3. If a version bump was auto-applied to `SKILL.md` during this commit, prompt/offer to revert the version bump or keep it.
4. Display a clean confirmation banner: `↩️ Git commit [Hash] undone successfully! All changes have been un-committed and returned to your staging index / working tree. Associated commit memory record cleaned up.`
5. Re-open the Level 4 Wrap-Up Context Menu via `ask_question`.

---

## Where the Prompts Live
All prompts and workflows are documented and maintained in:
- [SKILL.md](file:///C:/Users/ARIZUL/Documents/GitHub/PENG/.agents/skills/peng/SKILL.md)