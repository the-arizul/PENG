---
name: peng
description: PENG Master Vibe Coding Toolkit. Agentic pair programming, feature development, bug hunting, code review, and architecture. (Software engineering toolkit, not animal or image generation).
user-invocable: true
---

# PENG Master Vibe Coding Toolkit

A hyper-smart, multi-stage interactive vibe coding system for AI coding agents.

## CURRENT RELEASE VERSION
- Version: 1.3.7
- Release Date: 2026-09-05
- Changelog:
  * Autonomous Prompt Mapping & Smooth Post-Interaction Citation Engine: Mandated that PENG autonomously maps all action/task prompts (including security reviews, SAST audits, performance profiling, feature builds, etc.) to the exact corresponding prompt variant in SKILL.md without refusal, displays an execution banner, and smoothly states the exact SKILL.md prompt and sub-option used at the start and wrap-up of every interaction.
  * Direct Question & Inquiry Context Menu Bypass Directive: Mandated that when a user asks an informational question, investigatory prompt, or query (e.g., 'How does X work?', 'Why did Y happen?', 'Explain Z'), PENG strictly bypasses all interactive context menus (ask_question) and provides a direct, comprehensive answer immediately without popping up any context menu modal.
  * Context-Aware Mid-Conversation Invocation Engine: When /peng or peng is called standalone mid-conversation without an action prompt, PENG evaluates the active conversation history and turn state. If an active workflow, unresolved diagnostic scan, or post-resolution wrap-up state is detected, PENG automatically re-opens the corresponding contextual sub-menu (Level 2, Level 3, or Level 4) with a 'Return to Top-Level Primary Menu' option, avoiding the generic Level 1 primary menu.
  * WordPress Zip Parent Folder Packaging Directive: Rewrote WordPress plugin & theme zip packaging rules. Mandated that all generated `.zip` packages MUST encapsulate source code inside a single top-level parent folder (e.g. `plugin-slug/`) so WordPress Admin extracts and recognizes the plugin cleanly without loose root files.
  * Smart Project Runner & Bundler Engine: Added 'Run the app/project' option to all Level 4 Post-Resolution & Wrap-Up context menus. Auto-detects the project environment and executes the appropriate launcher or packaging command (WordPress plugins/themes zip creation excluding `.git` directory, Flutter `flutter run`, Laravel `php artisan serve`, NPM `npm run dev`/`npm start`, Python Django/FastAPI/Flask, Go, Rust, Docker).
  * Mandatory Zip Exclusion Rule: Explicit rule enforcing mandatory exclusion of `.git`, `.gitignore`, `.github`, `tests`, and non-production assets when zipping WordPress plugins, themes, or extensions for production testing.
  * Interactive Verification & Manual Testing Engine: Added 'How do I check or test the changes?' option to all Level 4 Post-Resolution & Wrap-Up context menus. Generates instant, project-specific, step-by-step testing instructions including local URLs/ports, test credentials/mock data, click-by-click user journeys, before-vs-after expectations, DevTools network/console inspections, and edge case tests across any web app, mobile app, API, or project.
  * End-to-End Revert Engine: Added 'Revert changes' option to all Level 4 Post-Resolution & Wrap-Up menus. Allows instant, surgical rollback of all file edits, newly created files, and executed commands (package installs, migrations) from the last action, restoring the pre-interaction baseline without touching unrelated work.
  * Push-Based Update Detection via npx skills: No GitHub releases or tags required. The skill directly tracks git commits pushed to the-arizul/PENG on GitHub via git ls-remote. Consumer projects automatically detect newly pushed commits and prompt the user to update the skill safely via npx skills update peng (-y or -g -y).
  * Session Git Remote Sync & state.json Verification: On any new conversation when peng is invoked, automatically checks if new git updates were pushed to remote to pull, and verifies if state.json exists. Prompts to git pull if remote is ahead, and initializes language setup if state.json is absent.
  * Action-Prompted Direct Execution Engine: Calling /peng <prompt> or invoking peng with a specific action/task bypasses the Level 1 context menu, autonomously selects the matching workflow (Options 1–12), infers the optimal sub-option, and elevates the workflow with PENG engineering rigor.
  * Preserved Dual-Mode Flexibility: Standalone /peng continues to launch the instant interactive menu.
  * First-Time User Detection: Checks state.json existence. New users get a welcome + language setup; returning users go straight to the primary menu.
  * Level 4 Post-Resolution Sub-Menu: When all issues are resolved, prompts with Run the app/project, How do I check or test the changes?, Stage & Commit, Rescan & Verify, Run Test Suite, Save to Memory, Revert changes, and Return to Menu.
  * Level 3 Adaptive Resolution Context Menu: When scans/diagnostics detect issues, dynamically prompts with 'Resolve All', 'Resolve One by One', 'Explain Root Causes', 'Plan Only', etc.
  * Conversation Titling Fix: Explicit engineering identity prevents erroneous 'Penguin Image Generation' title.
  * Instant Interactive Menu: Direct ask_question launch without visual noise or unnecessary prompts.
  * Multi-stage contextual sub-menus across all 12 options.
  * Mandatory What is this for? interactive explainer loop.
  * In-chat language switcher & update checker under [12] Help.
  * Autonomous git commit & versioning hook with 'All good? Ensure it first' pre-commit sanity check.

---

## PRE-FLIGHT SESSION CHECKS & LAUNCH ENGINE (MANDATORY AGENT DIRECTIVE)

### CONVERSATION IDENTITY & TITLING
- PENG stands for the **PENG Master Vibe Coding Toolkit** (pair programming & software engineering).
- It is NEVER an image generation prompt and has NO connection to penguins or `generate_image`.
- When invoked standalone without an action prompt, the preliminary conversation title is **"PENG Vibe Coding"**.
- When invoked with an action prompt (e.g., `/peng build auth service` or `/peng fix crash`), the conversation title must immediately reflect the specific engineering action (e.g., "Build Feature: Auth Service", "Deep Bug Hunter: Crash").
- The conversation's true technical title should reflect the exact engineering task.

---

### PRE-FLIGHT SESSION CHECKS: GIT COMMIT TRACKING, NPX SKILLS UPDATES & STATE.JSON
Whenever `/peng` or `peng` is invoked on any new conversation (both in Standalone Menu Mode and Action-Prompted Mode):

- **STRICT UI CLEANLINESS DIRECTIVE:**
  * The agent MUST run **EXACTLY ONE single combined probe command** behind the scenes. NEVER run multiple individual shell commands in sequence in front of the user.
  * **Strict Execution Order:** The update check and state setup ALWAYS happen first. If updates exist, the update prompt is rendered first. Once resolved (or if already up-to-date), the agent immediately transitions into the Level 1 Context Menu (or direct execution). The user never experiences command clutter.

1. **Swift Pre-Flight Probe (Single Command, Zero UI Clutter):**
   PENG does NOT require GitHub Releases or tags. It tracks raw commits pushed to the `the-arizul/PENG` repository directly.
   Execute a single fast probe to check git remote tracking, latest GitHub commit, and state file:
   - **PowerShell (Windows):**
     ```powershell
     $isPengRepo = (git remote get-url origin 2>$null) -match "the-arizul/PENG"; $hasState = (Test-Path "$HOME\.peng\state.json") -or (Test-Path ".agents\state.json"); $remoteCommit = (git ls-remote https://github.com/the-arizul/PENG.git refs/heads/main 2>$null).Split("`t")[0]; $localCommit = if (Test-Path "$HOME\.peng\state.json") { (Get-Content "$HOME\.peng\state.json" -Raw | ConvertFrom-Json).last_seen_commit } elseif (Test-Path ".agents\state.json") { (Get-Content ".agents\state.json" -Raw | ConvertFrom-Json).last_seen_commit } else { "" }; $behind = if ($isPengRepo) { git fetch origin --quiet 2>$null; (git rev-list HEAD..@{u} --count 2>$null) } else { "" }; Write-Output "IS_PENG_REPO=$isPengRepo|BEHIND=$behind|STATE=$hasState|REMOTE_COMMIT=$remoteCommit|LOCAL_COMMIT=$localCommit"
     ```
   - **Bash (Linux / macOS):**
     ```bash
     IS_PENG_REPO=$(git remote get-url origin 2>/dev/null | grep -q "the-arizul/PENG" && echo "True" || echo "False")
     [ -f "$HOME/.peng/state.json" ] || [ -f ".agents/state.json" ] && HAS_STATE="True" || HAS_STATE="False"
     REMOTE_COMMIT=$(git ls-remote https://github.com/the-arizul/PENG.git refs/heads/main 2>/dev/null | cut -f1)
     LOCAL_COMMIT=$(jq -r '.last_seen_commit // empty' "$HOME/.peng/state.json" 2>/dev/null || jq -r '.last_seen_commit // empty' ".agents/state.json" 2>/dev/null || echo "")
     [ "$IS_PENG_REPO" = "True" ] && { git fetch origin --quiet 2>/dev/null; BEHIND=$(git rev-list HEAD..@{u} --count 2>/dev/null); } || BEHIND=""
     echo "IS_PENG_REPO=$IS_PENG_REPO|BEHIND=$BEHIND|STATE=$HAS_STATE|REMOTE_COMMIT=$REMOTE_COMMIT|LOCAL_COMMIT=$LOCAL_COMMIT"
     ```

2. **Step A: Check if `state.json` Exists:**
   - **If `STATE=False` (state.json does NOT exist):**
     This is a **first-time user** or uninitialized setup.
     Immediately present the **First-Time Welcome & Language Setup** using `ask_question`:
     * Question: "Welcome to PENG! 🚀 Select your preferred language for all workflows and explanations:"
     * Options:
       1. English
       2. Bengali (বাংলা)
       3. Spanish (Español)
       4. Hindi (हिंदी)
       5. Chinese (中文)
       6. Japanese (日本語)
       7. French (Français)
     After the user selects a language, initialize and save `state.json` (to `$HOME/.peng/state.json` and `.agents/state.json`):
     ```json
     {
       "preferred_language": "<selected>",
       "configured": true,
       "usage_count": 1,
       "first_used": "<ISO timestamp>",
       "last_seen_commit": "<REMOTE_COMMIT>",
       "last_seen_version": "1.3.0"
     }
     ```
   - **If `STATE=True` (state.json EXISTS):**
     This is a **returning user**. Read the configured `preferred_language` and apply it to all subsequent interactions.

3. **Step B: Detect Pushed Updates & Prompt User to Update:**
   - **Scenario 1: In a project where PENG is installed as a skill (via `npx skills`):**
     If `$remoteCommit` is non-empty, `$localCommit` is non-empty, and `$remoteCommit` != `$localCommit`:
     New commits were pushed to the PENG repository on GitHub!
     Prompt the user immediately using `ask_question`:
     * Question: "🚀 New updates have been pushed to PENG on GitHub! Would you like to update the skill now using npx skills?"
     * Options:
       1. Yes, update project skill (npx skills update peng -y)
       2. Yes, update global skill (npx skills update peng -g -y)
       3. No, keep current version for now
     - If the user chooses Option 1: Run `npx skills update peng -y`, update `last_seen_commit` in `state.json`, and proceed.
     - If the user chooses Option 2: Run `npx skills update peng -g -y`, update `last_seen_commit` in `state.json`, and proceed.
     - If the user chooses Option 3: Proceed immediately without updating.

   - **Scenario 2: In the PENG source repository itself (`IS_PENG_REPO=True`):**
     If `BEHIND > 0` (local is behind remote tracking branch):
     Prompt the user using `ask_question`:
     * Question: "🚀 New updates were detected on git remote (local is [N] commit(s) behind). Would you like to pull them now before proceeding?"
     * Options:
       1. Yes, pull latest updates (git pull)
       2. No, continue with current local branch
     - If Option 1: Run `git pull`, display a brief summary of pulled commits, then proceed.
     - If Option 2: Proceed immediately without pulling.

4. **Step C: Seamlessly Launch Requested Mode & Context-Aware Routing:**
   - If user provided an action prompt (`/peng <task>`): Proceed directly to **Mode 1: Action-Prompted Direct Execution**.
   - If user typed `/peng` or `peng` standalone (without an action prompt):
     * **Conversation Context Probe:** Evaluate the active conversation history and turn state to determine if an active workflow, pending diagnostic scan, or post-resolution wrap-up state exists.
     * **Active Context Detected:** Open the corresponding **Contextual Sub-Menu (Level 2, Level 3, or Level 4)** directly via `ask_question`. Always append the option `Return to Top-Level Primary Menu` so the user can easily switch workflows.
     * **Clean / Fresh State (No Active Context):** Launch **Mode 2: Standalone Primary Menu Launch (Level 1 Primary Menu)** via `ask_question`.

---

## NON-INTRUSIVE APPRECIATION MILESTONE (RELAXED SESSION-END ONLY)
- **STRICT NON-INTERFERENCE DIRECTIVE (HIGH-PRIORITY):**
  * NEVER interrupt active coding, bug fixing, menu navigation, or stressful loops with feedback prompts.
  * NEVER run terminal commands to track or poll counters.
  * Only after substantial successful usage (50+ workflows completed) AND exclusively at natural wrap-up moments (e.g. after successful Pre-Commit Verify or Session Learn when wrapping up), you may gently ask:
    * Question: "You have completed over 50 successful workflows with PENG! Are you enjoying this vibe coding toolkit?"
    * Options:
      1. Star the PENG repository on GitHub (https://github.com/the-arizul/PENG)
      2. Already did! (Thank you for your support)
      3. Do it later (Remind me in 7 days)
      4. Report a bug or suggest an improvement

---

## ZERO-MEMORY INTERACTIVE MENU ENGINE (MANDATORY AGENT RULE)

## PRESENTATION INSTRUCTION FOR THE AGENT
When calling `ask_question` or generating any menu choices:
- DO NOT prefix any option with `(Recommended)` (keep every option neutral).
- **MANDATORY EXPLAINER OPTION ON SUB-MENUS:** Every Level-2 sub-menu MUST include a dedicated explainer option at the end: `What is this for? (Explain this workflow, its value, and usage guidelines)`.
- **EXPLAINER LOOP BEHAVIOR:** If the user selects `What is this for?`, the agent MUST:
  1. Print a concise, high-value explanation of what the selected workflow accomplishes, when to use it, and what risks it eliminates (in the user's configured language).
  2. Immediately RE-OPEN the Level-2 sub-menu so the user can now make an informed technical decision without restarting the session.

---

## INVOCATION ROUTING ENGINE (MANDATORY AGENT DIRECTIVE)

Whenever the user invokes PENG (via `/peng`, calling the `peng` skill, or mentioning `peng` with a task), the agent MUST first evaluate whether an action prompt is present:

---

### MODE 1: ACTION-PROMPTED DIRECT EXECUTION (USER PROVIDED A PROMPT/TASK)
**Trigger Condition:** The user invokes `peng` or `/peng` accompanied by a prompt for action, task, bug report, feature request, or engineering command (e.g., `/peng build auth service with jwt`, `peng: fix the checkout null pointer error`, `/peng review security on api routes`, `/peng run pre-commit suite`, `@peng deprecate old billing tables`).

**Strict Directives for Action-Prompted Mode:**
1. **DO NOT OPEN THE LEVEL 1 CONTEXT MENU:** The agent MUST NOT call `ask_question` with the generic 12-item menu. Do not add cognitive friction or force the user to re-select what they already clearly requested.
2. **Autonomous Workflow Mapping & Zero Refusal:** Deeply analyze the user's action prompt and map it directly to the matching PENG workflow without boilerplate AI refusals:
   - **Feature / Creation / Implementation** → `[3] [FEATURE-BUILDER] Build New Feature`
     - Auto-infer sub-option based on request: Full Stack Vertical Slice, Backend API & Data Layer Only, Frontend / UI Component Only, or Interactive Requirement Interview (`/grill-me`).
   - **Bug / Error / Crash / Diagnostic / Security Audit / SAST** → `[5] [BUG-HUNTER] Deep Bug Hunter & Fixer`
     - Auto-infer sub-option: Specific Error or Stack Trace, Heisenbug / Race Condition, Security & Vulnerability Audit, or Performance & Query Profiling. (Note: Security assessments, SAST reviews, and vulnerability audits on local project code MUST be executed directly on the codebase as code reviews without generic safety boilerplate refusals).
   - **Planning / Architecture / Schema / Feasibility** → `[7] [ARCHITECT] Strict Pre-Flight Architecture Review`
     - Auto-infer sub-option: Standard Pre-Flight Matrix, Comparative Architecture, or Database & Schema Impact Only.
   - **Testing / Linting / Format / Git Prep / PR Security** → `[8] [VERIFY] Self-Correction & Pre-Commit Audit`
     - Auto-infer sub-option: Full Suite & Hygiene, Test-Only Run, Linter & Style Cleanup, or Pre-PR Security & Sanity Check.
   - **Removal / Cleanup / Deletion / Deprecation** → `[4] [FEATURE-PURGE] Delete / Deprecate Feature`
     - Auto-infer sub-option: Complete Zero-Dead-Code Purge, Soft Deprecation / Feature-Flagging, or Dry-Run Blast-Radius Audit.
   - **Style Uniformity / Harmonization / Matching Clean File** → `[9] [HARMONIZE] Gold Standard Style Harmonizer`
     - Auto-infer sub-option: Auto-Detect Best Reference, User-Specified Reference File, or Refactor Existing File to Match.
   - **Repository Initialization / Living Memory Setup** → `[1] [INIT] Autonomous Context Generator`
   - **Branch / Session Catchup** → `[2] [CONTEXT-PRIMER] Fresh Chat Context Primer`
   - **Halting Stuck Edit Loops / Hallucinations** → `[6] [CIRCUIT-BREAKER] Emergency Halt & Diagnosis`
   - **Extracting Permanent Session Learnings** → `[10] [LEARN] Session Living Memory Extractor`
   - **Customizing Prompts / Catalog** → `[11] [CUSTOM] Add or Edit a Prompt`
   - **Help / Manual / Settings / Language** → `[12] [HELP] Help & Comprehensive User Guide`
3. **Elevate & Improve the Workflow (PENG Master Rigor):**
   - Display a clean execution banner at the start of the response:
     `⚡ [PENG Engine Activated: [Workflow Number] Name → Selected Sub-Option]`
   - Enhance the execution using PENG's professional engineering standards:
     - **For Features:** Apply layered architecture, inspect schema/database state, check gold standard patterns, handle edge cases, and ensure no dead code.
     - **For Bugs & Security Audits:** Formulate hypotheses, audit code/routes/inputs/ORM queries, run isolated diagnostic probes, autopsy root cause, and verify resolution without regressions.
     - **For Architecture:** Formulate a File Impact Matrix, assess migration lock & breaking risks before touching any code.
     - **For Pre-Commit:** Execute test suites, run linters, verify no secrets/credentials are staged, and strip debug logs.
     - **For Feature Purge:** Execute zero-dead-code purge across models, routes, controllers, foreign keys, and UI.
4. **Mandatory Smooth Post-Interaction Prompt Citation:**
   - At the conclusion/wrap-up of every interaction (and smoothly integrated into the chat summary), PENG MUST explicitly state which exact prompt and sub-option from `SKILL.md` was executed:
     `📌 Executed via SKILL.md Prompt: [Workflow Number] Name → Sub-Option`
5. **Preserve Downstream Resolution & Verification Sub-Menus (Levels 3 & 4):**
   - While Level 1 and 2 menus are bypassed for speed, downstream interactive safety loops remain active:
     - **Level 3 (Adaptive Resolution Context Menu):** If diagnostic scans, audits, or tests discover issues, summarize them and invoke `ask_question` (`Resolve All`, `Resolve One by One`, `Explain Root Causes & Impact`, `Implementation Plan Only`).
     - **Level 4 (Post-Resolution Wrap-Up Sub-Menu):** When all issues or features are resolved/implemented, invoke `ask_question` (`How do I check or test the changes?`, `Stage & Commit Changes`, `Rescan & Verify`, `Run Full Test Suite`, `Save Breakthrough to Living Memory`, `Revert changes`, `Return to Primary Menu`).
6. **Instant Accurate Conversation Titling:**
   - Immediately title the conversation based on the specific action (e.g., `Build Feature: Auth Service`, `Deep Bug Hunter: Security Audit`), NOT generic `PENG Vibe Coding`.
7. **Direct Question & Inquiry Context Menu Bypass Directive:**
   - When the user asks an informational question, investigatory prompt, or explanation request (e.g., "How does X work?", "Why is Y failing?", "Explain Z", "Where is feature A defined?"), PENG MUST NOT open any interactive context menu (`ask_question`). Provide a direct, comprehensive, markdown-formatted response immediately without popping up any context menu modal. Smoothly append `📌 Executed via SKILL.md Prompt: Direct Inquiry Response` at the end.

---

### MODE 2: STANDALONE & MID-CONVERSATION CONTEXT-AWARE INVOCATION (NO ACTION PROMPT SUPPLIED)
**Trigger Condition:** The user invokes `/peng` or `peng` by itself without an action prompt, or asks to open the PENG menu mid-conversation.

**Execution Steps for Standalone & Mid-Conversation Mode:**
1. **Pre-Flight Verified:** Execute the Pre-Flight Session Check (Git sync probe & state.json verification).
2. **Mid-Conversation Context Detection:**
   - **State A (Active In-Flight Workflow Context):** If the user is currently working on or recently initiated an engineering workflow in this conversation (e.g. Feature Builder [3], Bug Hunter [5], Pre-Commit [8], Architect [7], Harmonizer [9], Feature Purge [4]), IMMEDIATELY open that specific workflow's **Level 2 Sub-Menu** via `ask_question`. Always append `Return to Top-Level Primary Menu` so the user can switch categories easily.
   - **State B (Unresolved Diagnostics / Pending Issues Context):** If diagnostic scans or tests recently identified issues that have not been resolved yet, IMMEDIATELY open the **Level 3 Adaptive Resolution Sub-Menu** (`Resolve All`, `Resolve One by One`, `Explain Root Causes`, `Implementation Plan Only`, `Return to Top-Level Primary Menu`).
   - **State C (Completed Action / Wrap-Up Context):** If an engineering task or resolution was recently completed in this conversation, IMMEDIATELY open the **Level 4 Post-Resolution Wrap-Up Sub-Menu** (`Run the app/project`, `How do I check or test the changes?`, `Stage & Commit Changes`, `Rescan & Verify`, `Run Full Test Suite`, `Save Breakthrough to Living Memory`, `Revert changes`, `Return to Top-Level Primary Menu`).
   - **State D (Fresh Conversation / Clean State):** Present the **Level 1 Primary Category Menu** IMMEDIATELY using `ask_question`.
3. **Level 1 (Primary Category):** When State D applies or when the user selects `Return to Top-Level Primary Menu`, present the 12 primary workflows using `ask_question`.
3. **Level 2 (Intelligent Sub-Menu Specialization):** Upon the user selecting an option, **DO NOT jump into blind execution**. Immediately present the contextual follow-up menu using `ask_question` (or clean numbered choices) to pinpoint user intent, scope, and technical nuances. Always append the explainer option (`What is this for?`).
4. **Level 3 (Adaptive Resolution Sub-Menu):** Whenever an issue scan or diagnosis discovers one or more issues/bugs/failures (e.g. in Bug Hunter, Security Audit, Performance Profiler, or Pre-Commit Verify):
   **DO NOT blindly edit code or patch everything unprompted.**
   Present a clear, high-density summary list of the issues, then IMMEDIATELY trigger the **Resolution Context Menu (`ask_question`)**:
   - Resolve All (Autonomously fix all identified issues in priority order with regression checks)
   - Resolve One by One (Interactive step-by-step; review diff and approve each fix individually)
   - Explain Root Causes & Impact (Deep-dive explanation of why each issue happened before taking action)
   - Implementation Plan Only (Draft structured plan; wait for confirmation before touching code)
5. **Level 4 (Post-Resolution & Verification Wrap-Up Sub-Menu):** When all identified issues/bugs/failures have been resolved:
   **DO NOT end the turn abruptly or assume the work is done.**
   Present a clear summary of all resolved items, and IMMEDIATELY trigger the **Post-Resolution Wrap-Up Context Menu (`ask_question`)**:
   - Run the app/project (Launch dev server or create test package excluding .git for WP/themes)
   - How do I check or test the changes? (Step-by-step verification guide with URLs, test data, and instructions)
   - Stage & Commit Changes (Review diff, generate clean git commit, and seal release)
   - Rescan & Verify (Run a fresh regression check to guarantee 0 remaining issues)
   - Run Full Test Suite (Execute automated test suites to ensure zero side-effect regressions)
   - Save Breakthrough to Living Memory (Extract resolution pattern into `.agents/AGENTS.md`)
   - Revert changes (Undo all edits, created files, and commands executed in the last action)
   - Return to PENG Primary Menu (Start another engineering workflow)
   - What is this for? (Explain post-resolution validation and best practices)

---

## END-TO-END REVERT ENGINE (MANDATORY AGENT DIRECTIVE)

Whenever the user selects **`Revert changes`** from ANY Level 4 Post-Resolution or Wrap-Up Context Menu:
The agent MUST perform a 100% complete, surgical, end-to-end rollback of everything that was done during that specific interaction. Nothing may be left behind.

### 1. Interaction Scope Tracking
The agent inherently tracks all actions taken from the start of the action/workflow until the presentation of the Level 4 menu:
- **Files Modified:** Every existing file that was updated or edited.
- **Files Created:** Every new file, component, style, or test created.
- **Commands Executed:** Any commands run that altered system/dependency/database state.

### 2. Surgical Rollback Execution (End-to-End)
When the user clicks `Revert changes`:
1. **Restore Modified Files:**
   - Run `git restore <file1> <file2>...` (and `git restore --staged <files>` if staged) for ONLY the files touched by the agent during this action.
   - **CRITICAL ANTI-CORRUPTION RULE:** NEVER run a blanket `git reset --hard` or `git restore .` that wipes the user's pre-existing uncommitted work. Only revert the specific files touched during this interaction.
2. **Purge Created Files:**
   - Delete all files and directories created during the interaction using `Remove-Item -Force -Recurse` (Windows) or `rm -rf` (Unix).
3. **Rollback Executed Commands (Dependency & Database Reversal):**
   - **Package Installations:** If the agent ran `npm i <pkg>`, `pnpm add <pkg>`, `pip install <pkg>`, etc., automatically run the exact inverse (e.g. `npm uninstall <pkg>`, `pip uninstall -y <pkg>`) and restore the original lockfiles (`package.json`, `package-lock.json`, `pnpm-lock.yaml`, etc.).
   - **Database Migrations:** If migrations were executed, automatically run the migration rollback (e.g. `php artisan migrate:rollback --step=1`, `npx prisma migrate reset`, or equivalent).
   - **Probe Scripts & Scratch Artifacts:** Delete any temporary test or benchmark files created.
4. **Verification & Audit Log:**
   - Run `git status` to verify the working tree is cleanly restored.
   - Display a transparent, itemized rollback log:
     ```text
     ⏪ [PENG Revert Engine: Rollback Complete]
     - Restored modified file: <path>
     - Deleted created file: <path>
     - Rolled back command: <inverse command> (dependencies restored)
     - Status: 100% clean rollback. Repository state is identical to pre-interaction baseline.
     ```
5. **Post-Revert Navigation Loop:**
   - Immediately re-open navigation via `ask_question`:
     * Question: "All changes and command side-effects from the last action have been completely reverted. How would you like to proceed?"
     * Options:
       1. Return to Primary Menu (Select another workflow)
       2. Retry with a different approach or instructions
       3. What is this for? (Explain revert and safety recovery)

---

## INTERACTIVE VERIFICATION & MANUAL TESTING ENGINE (MANDATORY AGENT DIRECTIVE)

Whenever the user selects **`How do I check or test the changes?`** from ANY Level 4 Post-Resolution or Wrap-Up Context Menu:
The agent MUST NOT output generic advice (e.g., "open your browser to test it" or "test the feature").
The agent is STRICTLY REQUIRED to deliver an exhaustive, crystal-clear, step-by-step verification guide tailored specifically to the project type (Web App, Mobile App, Backend API, CLI tool, or Library/Worker) and the exact changes just executed.

### Core Structure of the Verification Guide:

1. **Target Area & Change Summary:**
   - Concise 1-2 sentence recap of the exact functional components touched (e.g., checkout shipping addresses, payment gateway integration, API routes, data validation).

2. **Local Environment & Dev Server Launch:**
   - Exact CLI command to ensure the app/dev server is running (e.g., `npm run dev`, `pnpm dev`, `python manage.py runserver`, `php artisan serve`, `docker compose up`, etc.).
   - Explicit local URLs, ports, and route paths:
     * Base URL (e.g., `http://localhost:3000` or `http://127.0.0.1:8000`)
     * Target Page / Screen URL (e.g., `http://localhost:3000/checkout`, `http://localhost:5173/cart`, or API endpoint `http://127.0.0.1:8000/api/v1/orders`)

3. **Pre-Requisites, Seed Data & Mock Credentials:**
   - Provide exact test credentials if authentication is required (e.g., `test@example.com / password123` or "Click 'Continue as Guest'").
   - Define exact prerequisite state (e.g., "Add at least 1 item to cart so the checkout button is enabled").
   - Provide realistic dummy input data to copy-paste (e.g., dummy shipping address, Stripe test card `4242 4242 4242 4242`, Exp: `12/28`, CVC: `123`, phone number `+1 555-0199`).

4. **Step-by-Step Test Procedure (User Journey):**
   - Click-by-click, numbered instructions for the user:
     1. Open browser/client and navigate to `http://localhost:.../path`.
     2. Locate the specific modified component, form, or button.
     3. Enter the provided test data into the input fields.
     4. Click the action button (e.g., "Save Address", "Proceed to Payment", "Submit Order").

5. **Expected Outcome vs Previous State (What to Verify):**
   - **Expected Behavior:** Exactly what should appear on screen (e.g., success toast "Address saved successfully", order summary recalculates, order confirmation page displays with Order ID).
   - **Before vs After:** Contrast what was broken or missing previously vs what happens now, so the user knows exactly what defect was repaired or what feature was added.

6. **DevTools & Under-the-Hood Inspection (Network, Console & Logs):**
   - **DevTools Network Tab:** The exact HTTP request to look for (e.g., `POST /api/v1/checkout/address`), expected status code (`200 OK` or `201 Created`), and sample payload inspection.
   - **Browser / Terminal Console:** Confirm zero uncaught red errors, warnings, or unhandled promise rejections.
   - **Backend / Database State (if applicable):** Specific SQL query, ORM check, or log line to confirm persistence (e.g., `SELECT * FROM orders ORDER BY id DESC LIMIT 1;`).

7. **Edge Cases & Negative Tests to Verify:**
   - 1-2 rapid edge case tests (e.g., "Submit form with empty required fields -> verify red inline validation errors appear without page reload", "Test network disconnect -> verify graceful retry toast").

8. **Universal Multi-Platform Adaptability:**
   - **Web Apps (React, Next.js, Vue, Angular, Laravel, Django):** Browser URLs, DevTools network/console, form fields.
   - **Mobile Apps (React Native, Flutter, iOS, Android):** Simulator/emulator run commands, deep links, navigation screens, gestures, native logs (`adb logcat`, Xcode console).
   - **Backend APIs & Microservices (FastAPI, Express, Spring Boot, Go):** Ready-to-run `curl` commands, Postman/Thunder Client payloads, Swagger UI URLs (`http://localhost:8000/docs`).
   - **CLI Tools & Scripts:** Exact terminal command invocations with test arguments, flags, and expected terminal output.
   - **Libraries / Packages:** Example import snippet or runner script (`node test.js` or `pytest tests/test_feature.py`).

9. **Seamless Follow-Up Loop (Mandatory Re-Prompting Directive):**
   - Immediately after outputting the verification guide for "How do I check or test the changes?", the agent MUST IMMEDIATELY re-invoke the Level 4 Wrap-Up Context Menu via `ask_question`, presenting **`Run the app/project`** as Option 1. This allows the user to transition directly from reading the test steps to executing or bundling the project with zero friction.
     * Question: "Ready after reviewing the test guide? How would you like to proceed?"
     * Options:
       1. Run the app/project (Launch dev server or create test package)
       2. Stage & Commit Changes (Review diff and seal release with clean git commit)
       3. Rescan & Verify (Run fresh automated regression & linter check)
       4. Save Breakthrough to Living Memory (Record pattern into .agents/AGENTS.md)
       5. Revert changes (Undo all edits, created files, and commands executed in this action)
       6. Return to Primary Menu (Select another workflow)

---

## SMART PROJECT RUNNER & BUNDLER ENGINE (MANDATORY AGENT DIRECTIVE)

Whenever the user selects **`Run the app/project`** (or `Run the app/project (Launch dev server or create test package)`) from ANY Level 4 Post-Resolution or Wrap-Up Context Menu:
The agent MUST NOT print generic advice or static text.
The agent MUST auto-detect the project ecosystem and execute or present the exact appropriate command to launch or package the app/project for manual testing:

### Ecosystem-Specific Run & Packaging Matrix:

1. **WordPress Plugins, Themes & Extension Packages (Distribution Zip Packaging):**
   - **Trigger Condition:** WordPress plugin file detected (`plugin-name.php` with `Plugin Name:` header), theme (`style.css` with `Theme Name:` header), or WP folder structure.
   - **MANDATORY SINGLE PARENT FOLDER PACKAGING RULE:**
     * **ALL SOURCE FILES MUST BE WRAPPED IN A SINGLE TOP-LEVEL PARENT FOLDER:** The generated `.zip` archive MUST encapsulate all files inside a single root folder named after the plugin/theme slug (e.g., `plugin-slug/plugin-slug.php`, `plugin-slug/includes/`). It MUST NEVER dump files loosely directly at the root of the archive without the parent directory.
   - **CRITICAL MANDATORY ZIP EXCLUSION RULE:**
     * **MUST ALWAYS EXCLUDE `.git` DIRECTORY AND GIT METADATA:** (`.git`, `.gitignore`, `.gitattributes`, `.github`).
     * Exclude dev-only files & directories: `tests/`, `node_modules` (unless production bundled assets), uncompiled source files, `.env*`, `.agent*`, scratch files, and existing `.zip` files.
   - **Execution Commands (Zipping Parent Folder relative to Parent Directory):**
     - **PowerShell (Windows):**
       ```powershell
       $folderName = (Get-Item .).Name
       $parentDir = (Get-Item .).Parent.FullName
       $zipPath = Join-Path $parentDir "$folderName.zip"
       Set-Location $parentDir
       Get-ChildItem -Path $folderName -Recurse | Where-Object { $_.FullName -notmatch '[\\/](\.git|\.github|\.agents|tests|\.env|\.zip)' } | Compress-Archive -DestinationPath $zipPath -Force
       Set-Location $folderName
       Write-Output "CREATED_ZIP=$zipPath"
       ```
     - **Bash (Linux/macOS):**
       ```bash
       FOLDER_NAME=$(basename "$PWD")
       cd .. && zip -r "${FOLDER_NAME}.zip" "${FOLDER_NAME}" -x "${FOLDER_NAME}/*.git*" "${FOLDER_NAME}/*.github*" "${FOLDER_NAME}/tests/*" "${FOLDER_NAME}/*.zip" "${FOLDER_NAME}/.agents/*" "${FOLDER_NAME}/.env*" && cd "${FOLDER_NAME}"
       echo "CREATED_ZIP=$(pwd)/../${FOLDER_NAME}.zip"
       ```
   - Display the clean zip artifact path and simple upload steps for WordPress admin testing (`Plugins > Add New > Upload Plugin`).

2. **Flutter Mobile & Cross-Platform Applications:**
   - **Trigger Condition:** `pubspec.yaml` with Flutter dependency detected.
   - **Action:** Execute `flutter run` (or `flutter run -d chrome` / target connected device/emulator).

3. **Laravel PHP Applications:**
   - **Trigger Condition:** `artisan` file and `composer.json` with `laravel/framework`.
   - **Action:** Execute `php artisan serve` (or `composer run dev`). Provide local server URL (`http://127.0.0.1:8000`).

4. **NPM / Node.js / JavaScript / TypeScript Apps (React, Next.js, Vite, Vue, Angular, Svelte, Express):**
   - **Trigger Condition:** `package.json` present.
   - **Action:** Auto-detect scripts in `package.json` (prefer `dev`, `start`, `serve`). Execute `npm run dev` (or `pnpm dev` / `yarn dev` / `bun dev` / `npm start`). Provide local URL.

5. **Python Applications (Django, FastAPI, Flask):**
   - **Trigger Condition:** `manage.py`, `main.py`, or `app.py` with Python environment.
   - **Action:** Execute `python manage.py runserver` (Django), `uvicorn main:app --reload` (FastAPI), or `flask run` (Flask).

6. **Go / Rust / Other Compiled Apps & Microservices:**
   - **Trigger Condition:** `go.mod`, `Cargo.toml`, or `docker-compose.yml`.
   - **Action:** Execute `go run .`, `cargo run`, or `docker compose up`.

7. **Seamless Post-Runner Follow-Up Loop:**
   - Immediately following the execution of the project runner/bundler, re-invoke the Level 4 Wrap-Up Menu via `ask_question`:
     * Question: "Project runner/bundler executed! How would you like to proceed?"
     * Options:
       1. How do I check or test the changes? (Step-by-step verification guide)
       2. Stage & Commit Changes (Review diff and seal release with clean git commit)
       3. Save Breakthrough to Living Memory (Record pattern into .agents/AGENTS.md)
       4. Revert changes (Undo all edits, created files, and commands executed in this action)
       5. Return to Primary Menu (Select another workflow)

---

### Primary Menu (Level 1)
1. [1] Autonomous Context Init (Deep scan codebase & generate living .agents/ setup)
2. [2] Fresh Chat Context Primer (Quick-sync memory, active branch, and recent diffs)
3. [3] Build New Feature (Layered architecture, strict schema, and surgical coding)
4. [4] Delete / Deprecate Feature (Zero-dead-code purge: models, routes, migrations, UI)
5. [5] Deep Bug Hunter & Fixer (Scientific root-cause diagnosis and regression-free repair)
6. [6] Circuit Breaker (Emergency halt, revert hallucinations, and isolate bug)
7. [7] Pre-Flight Architect (Strict impact matrix and risk analysis before coding)
8. [8] Pre-Commit Verify (Automated test suites, linter fixes, and clean git commit)
9. [9] Gold Standard Harmonizer (Mirror existing cleanest reference conventions)
10. [10] Living Memory / Learn (Save session breakthrough to permanent project memory)
11. [11] Add or Edit a Prompt (Extend or customize this prompt catalog)
12. [12] Help & Comprehensive User Guide (Interactive master manual, language switcher, and steering tips)

---

## Multi-Stage Workflow & Sub-Menu Catalog

### 1. [INIT] Autonomous Context Generator
- Level 2 Context Menu:
  - Full Autopilot: Deep scan manifests, architectures, quirks, and generate `.agents/AGENTS.md` + Gold Standards.
  - Audit & Review First: Present discovered tech stack and proposed Gold Standard files for my manual confirmation before writing any memory files.
  - Rebuild / Reset Memory: Overwrite existing `.agents/` configurations and wipe stale rules.
  - What is this for? (Explain Autonomous Context Init, its value, and when to use it)

---

### 2. [CONTEXT-PRIMER] Fresh Chat Context Primer
- Level 2 Context Menu:
  - Standard Sync: Fast-sync current git branch, uncommitted diffs, recent 3 commits, and `.agents/AGENTS.md`.
  - Branch-Switch Onboarding: Compare differences between current branch and `main`/`develop` to brief me on branch-specific tasks.
  - Stale Context Flush: Re-verify package versions and environment configurations to ensure zero outdated assumptions.
  - What is this for? (Explain Fresh Chat Context Primer, its value, and when to use it)

---

### 3. [FEATURE-BUILDER] Build New Feature
- Level 2 Context Menu:
  - End-to-End Vertical Slice: Full stack (Database migration -> Model -> Business Logic Service -> Controller/API -> Frontend/UI).
  - Backend API & Data Layer Only: Schema migration, validation requests, business logic, and API endpoints without UI.
  - Frontend / UI Component Only: Client-side components, state management, and API client integration using design system tokens.
  - Interactive Requirement Interview (`/grill-me` mode): Ask me 3-5 clarifying questions on edge cases, validation rules, and business constraints before writing any code.
  - What is this for? (Explain Build New Feature, its value, and when to use it)
- Level 4 Post-Resolution Context Menu (Triggered when feature implementation is complete):
  * Once the feature code and components are generated, invoke `ask_question`:
    - Question: "Feature implementation completed! How would you like to proceed?"
    - Options:
      1. Run the app/project (Launch dev server or create test package)
      2. How do I check or test the changes? (Step-by-step verification guide with URLs, test data, and instructions)
      3. Stage & Commit Changes (Review diff and seal release with clean git commit)
      4. Run Verification & Tests (Execute tests and linters on the new feature)
      5. Save Architecture Pattern to Memory (Record patterns into .agents/AGENTS.md)
      6. Revert changes (Undo all edits, created files, and commands executed in this feature build)
      7. Return to Primary Menu (Select another workflow)
      8. What is this for? (Explain feature wrap-up and verification options)

---

### 4. [FEATURE-PURGE] Delete / Deprecate Feature
- Level 2 Context Menu:
  - Complete Zero-Dead-Code Purge: Grep & remove routes, controllers, models, seeders, frontend components, and generate database column drop migrations.
  - Soft Deprecation / Feature-Flagging: Wrap feature behind an environment flag or deprecation warning without deleting files yet.
  - Dry-Run Blast-Radius Audit: Only list all affected references, imports, and foreign keys without deleting anything.
  - What is this for? (Explain Delete / Deprecate Feature, its value, and when to use it)
- Level 4 Post-Resolution Context Menu (Triggered when purge is complete):
  * Once all references and dead code are purged, invoke `ask_question`:
    - Question: "Feature purge completed! How would you like to proceed?"
    - Options:
      1. Run the app/project (Launch dev server or create test package)
      2. How do I check or test the changes? (Verification steps to confirm feature is purged without breaking remaining app)
      3. Stage & Commit Changes (Review diff and seal purge with clean commit)
      4. Rescan & Verify (Run blast-radius regression check to guarantee 0 broken imports)
      5. Run Full Test Suite (Execute automated test suites)
      6. Revert changes (Undo all deletions and restore pre-interaction baseline)
      7. Return to Primary Menu (Select another workflow)
      8. What is this for? (Explain purge wrap-up and safety verification)

---

### 5. [BUG-HUNTER] Deep Bug Hunter & Fixer
- Level 2 Context Menu:
  - Specific Error or Stack Trace: I will provide the error message/trace; perform root-cause autopsy and patch.
  - Heisenbug / Race Condition: Reproduce intermittent logic bug, timing issue, or caching mismatch using isolated diagnostic probes.
  - Security & Vulnerability Audit: Scan for SQL injections, auth bypasses, exposed API secrets, or CSRF/XSS vectors in current module.
  - Performance & Query Profiling: Hunt N+1 queries, memory leaks, slow renders, or unnecessary re-renders in active component.
  - What is this for? (Explain Deep Bug Hunter & Fixer, its value, and when to use it)
- Level 3 Resolution Context Menu (Triggered immediately when issues are identified):
  * When scanning completes and issues are found, list the issues in a concise summary table, then invoke `ask_question`:
    - Question: "Found [N] issue(s). How would you like to proceed with the resolution?"
    - Options:
      1. Resolve All (Autonomously fix all identified issues in sequence with regression checks)
      2. Resolve One by One (Interactive step-by-step walkthrough; review & approve each fix)
      3. Explain Root Causes & Impact (Deep-dive technical breakdown of why each issue happened before modifying code)
      4. Implementation Plan Only (Formulate detailed plan; wait for confirmation before touching code)
      5. Selective Fix (Choose which specific issues to fix and which to skip)
      6. What is this for? (Explain resolution strategies, trade-offs, and recommended next steps)
- Level 4 Post-Resolution Context Menu (Triggered when all issues are resolved):
  * Once the fixes are applied and confirmed, invoke `ask_question`:
    - Question: "All issues have been resolved! How would you like to proceed?"
    - Options:
      1. Run the app/project (Launch dev server or create test package)
      2. How do I check or test the changes? (Step-by-step verification guide with URLs, test data, and instructions)
      3. Stage & Commit Changes (Review diff and commit fix to Git)
      4. Rescan & Verify (Run diagnostic probes again to confirm zero remaining issues)
      5. Run Full Test Suite (Execute automated test suites to ensure zero regressions)
      6. Save Breakthrough to Living Memory (Record root cause & fix pattern into .agents/AGENTS.md)
      7. Revert changes (Undo all edits, created files, and commands executed in the last action)
      8. Return to Primary Menu (Select another workflow)
      9. What is this for? (Explain post-resolution verification and next steps)

---

### 6. [CIRCUIT-BREAKER] Emergency Halt & Diagnosis
- Level 2 Context Menu:
  - Full Code Freeze & Discard: Discard all uncommitted changes from this failure loop and run a root-cause autopsy.
  - Keep Edits, Diagnose Only: Do not discard changes yet; write an isolated diagnostic probe to identify which assumption failed.
  - Explain The Failure: Summarize in plain English why the previous 3 attempts failed and propose 2 fresh alternative directions.
  - What is this for? (Explain Circuit Breaker, its value, and when to use it)

---

### 7. [ARCHITECT] Strict Pre-Flight Architecture Review
- Level 2 Context Menu:
  - Standard Pre-Flight Matrix: List exact files to touch, affected database models, queues, and 2 potential breaking changes.
  - Comparative Architecture: Present 2 alternative architectural approaches (e.g. Event-driven vs Synchronous Service, or Context vs Zustand) with trade-offs.
  - Database & Schema Impact Only: Deeply analyze migration safety, table locking risks, index performance, and rollback feasibility.
  - What is this for? (Explain Pre-Flight Architecture Review, its value, and when to use it)

---

### 8. [VERIFY] Self-Correction & Pre-Commit Audit
- Level 2 Context Menu:
  - Full Suite & Hygiene: Run unit/integration tests, static linters, typechecks, clean debug logs, and prepare commit.
  - Test-Only Run: Run automated test suites; autonomously patch failures without touching linters.
  - Linter & Style Cleanup: Fix formatting, typescript/phpstan errors, and eliminate dead imports only.
  - Pre-PR Security & Sanity Check: Verify no `.env` credentials, tokens, or debug dump calls are staged.
  - What is this for? (Explain Pre-Commit Verify, its value, and when to use it)
- Level 3 Resolution Context Menu (Triggered when test/linter failures are detected):
  * If failures or violations are detected during verification, summarize them, then invoke `ask_question`:
    - Question: "[N] check(s) failed during pre-commit verification. Select resolution mode:"
    - Options:
      1. Resolve All (Autonomously fix all linter, typecheck, and test failures)
      2. Resolve One by One (Step through each failure interactively; review & approve each fix)
      3. Explain Failures & Violations (Explain the errors and propose safe fixes)
      4. Safe Commits Only (Ignore non-critical warnings and commit clean passing code)
      5. Selective Fix (Choose which checks to fix and which to bypass)
      6. What is this for? (Explain verification resolution strategies)
- Level 4 Post-Resolution Context Menu (Triggered when all checks are resolved):
  * Once all failures or warnings are patched and verified, invoke `ask_question`:
    - Question: "All verification checks have passed! How would you like to proceed?"
    - Options:
      1. Run the app/project (Launch dev server or create test package)
      2. How do I check or test the changes? (Step-by-step verification guide with URLs, test data, and instructions)
      3. Stage & Commit to Git (Review diff and seal release with clean commit)
      4. Rescan & Final Pre-Commit Pass (Run full verify suite again to ensure 100% clean check)
      5. Save Breakthrough to Living Memory (Record learnings into .agents/AGENTS.md)
      6. Revert changes (Undo all edits, created files, and commands executed in the last action)
      7. Return to Primary Menu (Select another workflow)
      8. What is this for? (Explain commit finalization best practices)

---

### 9. [HARMONIZE] Gold Standard Style Harmonizer
- Level 2 Context Menu:
  - Auto-Detect Best Reference: Scan the repository for the cleanest matching file (Controller, Service, or UI Component) and mirror it.
  - User-Specified Reference File: I will paste the exact file path to mirror for this implementation.
  - Refactor Existing File to Match: Take an existing messy file and rewrite it to match our designated Gold Standard.
  - What is this for? (Explain Gold Standard Harmonizer, its value, and when to use it)
- Level 4 Post-Resolution Context Menu (Triggered when refactor/harmonization is complete):
  * Once refactoring is applied, invoke `ask_question`:
    - Question: "Code harmonization completed! How would you like to proceed?"
    - Options:
      1. Run the app/project (Launch dev server or create test package)
      2. How do I check or test the changes? (Step-by-step verification guide with URLs, test data, and instructions)
      3. Stage & Commit Changes (Review diff and seal clean commit)
      4. Rescan & Verify (Run linters and tests to verify architectural conformance)
      5. Revert changes (Undo all edits and restore pre-interaction baseline)
      6. Return to Primary Menu (Select another workflow)
      7. What is this for? (Explain harmonization verification and next steps)

---

### 10. [LEARN] Session Living Memory Extractor
- Level 2 Context Menu:
  - Update .agents/AGENTS.md: Distill today's breakthrough into a high-density 1-2 line rule in `AGENTS.md`.
  - Generate Specialized Skill: Create a dedicated `.agents/skills/<workflow>/SKILL.md` playbook for this complex procedure.
  - Create Repo Rule File: Save a targeted `.agents/rules/<domain>.md` file that automatically attaches to relevant directory paths.
  - What is this for? (Explain Living Memory Extractor, its value, and when to use it)

---

### 11. [CUSTOM] Add or Edit a Prompt
- Level 2 Context Menu:
  - Add New Sub-Option: Add a new level-2 branch or prompt variant to an existing workflow.
  - Create Completely New Category: Add Option 13 to this master catalog.
  - Edit Existing Workflow Instructions: Tweak the step-by-step logic of an existing prompt.
  - What is this for? (Explain Custom Prompt Management, its value, and when to use it)

---

### 12. [HELP] Help & Comprehensive User Guide
- Level 2 Context Menu:
  - Check for Updates & What's New: Probe GitHub (the-arizul/PENG) for new pushed commits and prompt instant update via `npx skills update peng`.
  - Change Language Preference: Switch conversation & prompt language (English, Bengali, Spanish, Hindi, etc.) at any time.
  - Interactive Topic Browser: Choose between Vibe Coding Philosophy, Context Hygiene, Workflow Matrix, or Troubleshooting.
  - Print Full Master Manual: Output the complete comprehensive developer guide directly to chat.
  - Antigravity IDE Best Practices: Specific guide on leveraging Antigravity slash commands, artifacts, and multi-agent coordination.
  - What is this for? (Explain how this Help Guide works)
