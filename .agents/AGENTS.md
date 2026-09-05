# AntiGravity PENG - Master Vibe Coding Toolkit

This repository contains the unified **PENG Master Vibe Coding System** for Antigravity IDE and universal AI coding agents.

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
3. **Git Commit with Best Practices:** Stage modified/created files (`git add -A`) and write a professional commit message following **Conventional Commits & Git Best Practices** (Header: `<type>(<scope>): <summary>`, blank line, structured Body with bullet points answering *what* changed and *why*, and breaking changes/release footer). Run `git commit`.
4. **Post-Commit Follow-Up & Undo Commit Modal (MANDATORY):** Immediately after commit execution, render the commit summary (Hash, Header, Body snippet) and launch an interactive follow-up menu via `ask_question`:
   - **Question:** 🚀 Git commit successful! [Commit: <hash>] How would you like to proceed?
   - **Options:**
     1. Undo commit (git reset --soft HEAD~1 - revert commit & keep changes staged)
     2. Push to remote repository (git push)
     3. Run the app/project
     4. Return to Primary Menu
5. **Undo Commit Handler:** If `Undo commit` is selected, run `git reset --soft HEAD~1` (and revert version bump if applicable), display confirmation `↩️ Commit <hash> undone. All changes are preserved in your working tree / staging index.`, and re-open the pre-wrap menu.

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
   - If missing: Launches the First-Time Welcome & Language Setup modal via `ask_question`, then initializes `state.json` (recording preferred language and latest commit hash).
   - If present: Loads user preferences (`preferred_language`) silently.

### 1. Action-Prompted Direct Execution (When a task or prompt is provided)
When you invoke `/peng <action prompt>` or call `peng` with a prompt for action (e.g. `/peng build auth service`, `/peng fix checkout crash`, `/peng run security audit`, `/peng run pre-commit tests`):
- **Bypasses Context Menu:** Does NOT open the Level 1 main menu.
- **Direct Question & Inquiry Response:** When you ask an informational question, investigatory prompt, or explanation request (e.g. "How does X work?", "Why is Y happening?"), PENG strictly bypasses all context menus (`ask_question`) and provides a direct answer immediately.
- **Autonomous Workflow Selection & Zero Refusal:** Maps your prompt directly to the best matching PENG workflow [1]–[12] without generic AI refusals (e.g. security assessments map to `[5] Deep Bug Hunter → Security & Vulnerability Audit` or `[8] Pre-PR Security Check`).
- **Smooth Post-Interaction Prompt Citation:** At the end of every interaction or session wrap-up, smoothly states the exact prompt and sub-option used formatted in bold text (e.g. `**Executed via PENG! [5] Deep Bug Hunter & Fixer → Security & Vulnerability Audit**` or `**Executed via PENG! Direct Inquiry Response**`).
- **Elevates Workflow Rigor:** Enforces PENG engineering standards (autopsy probes for bugs, layered architecture for features, impact matrix for architecture, clean test runs for pre-commit).
- **Interactive Resolution Sub-Menus:** If issues or failures are detected during execution, seamlessly launches the Level 3 (Resolution) and Level 4 (Wrap-Up) menus.
- **Smart Project Runner & Bundler Engine:** Every Level 4 Post-Resolution and Wrap-Up menu includes `Run the app/project`. Selecting this auto-detects the project type and launches the dev server or generates test packages (creates a clean `.zip` encapsulating all files inside a single parent folder while excluding `.git` for WordPress plugins/themes, `flutter run` for Flutter, `php artisan serve` for Laravel, `npm run dev`/`npm start` for NPM apps).
- **Interactive Verification & Manual Testing Engine:** Every Level 4 Post-Resolution and Wrap-Up menu includes `How do I check or test the changes?`. Selecting this provides an exhaustive, step-by-step manual test walkthrough tailored to the project (web, mobile, backend API, CLI, or library). Immediately after outputting the test steps, it re-invokes the Level 4 Context Menu with `Run the app/project` as Option 1 so the user can instantly run or package the app.
- **End-to-End Revert Engine:** Every Level 4 Post-Resolution and Wrap-Up menu includes `Revert changes`. Selecting this surgically undoes all file modifications (`git restore`), deletes created files, rolls back command side-effects (e.g. uninstalls newly added packages, rolls back migrations), and restores the exact pre-interaction state without affecting unrelated work.
- **Stage, Commit & Undo Commit Engine:** Every Level 4 Post-Resolution and Wrap-Up menu includes `Stage & Commit Changes`. Selecting this writes high-quality commit details formatted with Conventional Commits best practices (Header + Body detailing what & why), stages files, commits changes, and IMMEDIATELY presents a follow-up context menu offering `Undo commit (git reset --soft HEAD~1)`.

### 2. Standalone & Mid-Conversation Context-Aware Invocation (When no prompt is provided)
When you type `/peng` or `peng` by itself:
- **Context-Aware Sub-Menu Detection:** Checks active conversation state. If an active workflow, unresolved diagnostic scan, or post-resolution wrap-up state exists in the current conversation, automatically re-opens the corresponding **Level 2, Level 3, or Level 4 Contextual Sub-Menu** directly (with a `Return to Top-Level Primary Menu` option).
- **Primary Menu Launch:** If in a fresh conversation or clean state without active context, opens the Level 1 Primary Menu immediately via `ask_question`.
- **Smart Contextual Sub-Menus:** Prompts you through Level 2 specialization with mandatory `What is this for?` explainers.

### Quick Reference & Usage Matrix

| Option | Workflow | When to Use (Usage Time) | Goal & Impact |
| :--- | :--- | :--- | :--- |
| **[1]** | **Autonomous Context Init** | First chat in a new codebase or restructuring agent context. | Deep scan manifests, architectures, quirks, generate living .agents/ setup, and prompt to add recommended PENG directive rule. |
| **[2]** | **Fresh Chat Context Primer** | Starting a new chat session on an active branch. | Fast-sync active branch, uncommitted diffs, recent commits, and living memory. |
| **[3]** | **Build New Feature** | Developing new capabilities or components. | End-to-end vertical slices, API data layer, UI components, or requirement interview. |
| **[4]** | **Delete / Deprecate Feature** | Cleaning up legacy or unused code. | Complete zero-dead-code purge: models, routes, migrations, UI. |
| **[5]** | **Deep Bug Hunter & Fixer** | Debugging complex issues, regressions, or heisenbugs. | Scientific root-cause autopsy, reproduction probes, and regression-free repair. |
| **[6]** | **Circuit Breaker** | Trapped in an edit loop, repeated failures, or breaking code. | Emergency freeze, revert hallucinations, and diagnose root cause safely. |
| **[7]** | **Pre-Flight Architect** | Before building a major feature, refactoring, or schema changes. | Formulates file impact matrix, edge cases, and execution order before touching code. |
| **[8]** | **Pre-Commit Verify** | After coding is complete, right before git commit / PR. | Runs test suites, fixes lint errors, cleans debug logs, and prepares clean commit. |
| **[9]** | **Gold Standard Harmonizer** | Writing new controllers, services, models, or UI components. | Mimics existing cleanest reference file for 100% architectural uniformity. |
| **[10]** | **Living Memory Extractor** | End of a successful session after solving tough bugs or tricks. | Saves breakthroughs permanently into .agents/AGENTS.md so future chats remember. |
| **[11]** | **Add or Edit a Prompt** | Whenever you want to customize or expand this prompt toolkit. | Updates the master prompt catalog directly in SKILL.md. |
| **[12]** | **Help & Comprehensive User Guide** | Learning vibe coding, switching languages, or updating. | Interactive master manual, language switcher, and release changelog. |

---

## STAGE, COMMIT & UNDO COMMIT ENGINE (MANDATORY AGENT DIRECTIVE)

Whenever the user selects **`Stage & Commit Changes`** (or chooses to commit changes during session wrap-up or version release) from ANY context menu:
The agent MUST NOT output lazy, generic, or single-line commit messages (e.g., "update files" or "fix bug").
The agent MUST follow strict **Conventional Commits & Git Best Practices** when writing commit details, and MUST IMMEDIATELY trigger a post-commit context menu modal offering an **Undo commit** option (`git reset --soft HEAD~1`).

### 1. Git Inspection & Best-Practice Commit Construction:
1. **Inspect Working Tree & Diff:**
   - Execute `git status` and `git diff` (and `git diff --staged`) behind the scenes to inspect all modified, created, and deleted files.
2. **Formulate Conventional Commit Message:**
   - **Header Line:** `<type>(<scope>): <concise summary>`
     * **Type:** MUST be one of `feat`, `fix`, `docs`, `style`, `refactor`, `perf`, `test`, `chore`, `build`, `ci`, `revert`, `release`.
     * **Scope:** Optional identifier representing module/component (e.g., `auth`, `ui`, `api`, `cli`, `peng`).
     * **Summary:** Max 72 characters, imperative mood, lowercase type, no trailing period.
   - **Blank Line**
   - **Body Section (Mandatory):** Bulleted technical breakdown answering:
     * **What:** Specific functional & code changes implemented.
     * **Why:** Underlying technical rationale or problem resolved.
     * Key architectural, component, or file highlights.
   - **Footer Section (Optional):** Breaking changes (`BREAKING CHANGE: <desc>`) or issue references (`Refs: #123`).

### 2. Execution & Sealed Commit Summary Output:
- Stage all modified and created files (`git add -A` or target specific files).
- Execute `git commit` using a multi-line message format.
- Display a clean, sealed release summary in the chat turn response showing Commit Hash, Header, Body bullets, and Files Changed summary.

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
2. If a version bump was auto-applied to `SKILL.md` during this commit, prompt/offer to revert the version bump or keep it.
3. Display a clean confirmation banner: `↩️ Git commit [Hash] undone successfully! All changes have been un-committed and returned to your staging index / working tree.`
4. Re-open the Level 4 Wrap-Up Context Menu via `ask_question`.

---

## Where the Prompts Live
All prompts and workflows are documented and maintained in:
- [SKILL.md](file:///C:/Users/ARIZUL/Documents/GitHub/PENG/.agents/skills/peng/SKILL.md)