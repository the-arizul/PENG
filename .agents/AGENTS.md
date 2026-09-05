# AntiGravity PENG - Master Vibe Coding Toolkit

This repository contains the unified **PENG Master Vibe Coding System** for Antigravity IDE and universal AI coding agents.

## AUTONOMOUS VERSIONING & PRE-WRAP GIT COMMIT RULE (MANDATORY AGENT DIRECTIVE)

Whenever the user finishes working on this project, completes an update, or indicates a session wrap-up:
The agent MUST IMMEDIATELY trigger an interactive context menu using sk_question:

- **Question:**  You have made updates to PENG. Would you like to bump the release version and commit the changes to Git now?
- **Options:**
  1. Yes, bump patch version & commit (e.g., 1.2.0 -> 1.2.1)
  2. Yes, bump minor version & commit (e.g., 1.2.0 -> 1.3.0)
  3. Commit current changes without bumping version
  4. All good? Ensure it first (Run sanity audit, verify changes, and confirm readiness)
  5. No, keep uncommitted for now

### Execution Handlers when User selects Yes:
1. **Auto-Bump Version:** Update the Version: X.Y.Z in SKILL.md (and release date & changelog summary).
2. **Sync Mirrors:** Sync the updated SKILL.md to workspace copies.
3. **Git Commit:** Stage all changes and run git commit -m release: vX.Y.Z.
4. **Push Signal:** Inform the user that the release is sealed locally and ready to push to remote.

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
- **Smooth Post-Interaction Prompt Citation:** At the end of every interaction or session wrap-up, smoothly states the exact `SKILL.md` prompt and sub-option used (e.g. `📌 Executed via SKILL.md Prompt: [5] Deep Bug Hunter & Fixer → Security & Vulnerability Audit`).
- **Elevates Workflow Rigor:** Enforces PENG engineering standards (autopsy probes for bugs, layered architecture for features, impact matrix for architecture, clean test runs for pre-commit).
- **Interactive Resolution Sub-Menus:** If issues or failures are detected during execution, seamlessly launches the Level 3 (Resolution) and Level 4 (Wrap-Up) menus.
- **Smart Project Runner & Bundler Engine:** Every Level 4 Post-Resolution and Wrap-Up menu includes `Run the app/project`. Selecting this auto-detects the project type and launches the dev server or generates test packages (creates a clean `.zip` encapsulating all files inside a single parent folder while excluding `.git` for WordPress plugins/themes, `flutter run` for Flutter, `php artisan serve` for Laravel, `npm run dev`/`npm start` for NPM apps).
- **Interactive Verification & Manual Testing Engine:** Every Level 4 Post-Resolution and Wrap-Up menu includes `How do I check or test the changes?`. Selecting this provides an exhaustive, step-by-step manual test walkthrough tailored to the project (web, mobile, backend API, CLI, or library). Immediately after outputting the test steps, it re-invokes the Level 4 Context Menu with `Run the app/project` as Option 1 so the user can instantly run or package the app.
- **End-to-End Revert Engine:** Every Level 4 Post-Resolution and Wrap-Up menu includes `Revert changes`. Selecting this surgically undoes all file modifications (`git restore`), deletes created files, rolls back command side-effects (e.g. uninstalls newly added packages, rolls back migrations), and restores the exact pre-interaction state without affecting unrelated work.

### 2. Standalone & Mid-Conversation Context-Aware Invocation (When no prompt is provided)
When you type `/peng` or `peng` by itself:
- **Context-Aware Sub-Menu Detection:** Checks active conversation state. If an active workflow, unresolved diagnostic scan, or post-resolution wrap-up state exists in the current conversation, automatically re-opens the corresponding **Level 2, Level 3, or Level 4 Contextual Sub-Menu** directly (with a `Return to Top-Level Primary Menu` option).
- **Primary Menu Launch:** If in a fresh conversation or clean state without active context, opens the Level 1 Primary Menu immediately via `ask_question`.
- **Smart Contextual Sub-Menus:** Prompts you through Level 2 specialization with mandatory `What is this for?` explainers.

### Quick Reference & Usage Matrix

| Option | Workflow | When to Use (Usage Time) | Goal & Impact |
| :--- | :--- | :--- | :--- |
| **[1]** | **Autonomous Context Init** | First chat in a new codebase or restructuring agent context. | Deep scan manifests, architectures, quirks, and generate living .agents/ setup. |
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

## Where the Prompts Live
All prompts and workflows are documented and maintained in:
- [SKILL.md](file:///C:/Users/ARIZUL/Documents/GitHub/PENG/.agents/skills/peng/SKILL.md)