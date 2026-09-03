---
name: peng
description: PENG Master Vibe Coding Prompt Toolkit. Access, manage, edit, or execute battle-tested prompts with multi-stage conversational sub-menus (Init, Fresh Chat, Build Feature, Delete Feature, Deep Bug Hunter, Circuit Breaker, Architect, Verify, Harmonize, Learn, Help).
user-invocable: true
---

# PENG Master Vibe Coding Toolkit

A hyper-smart, multi-stage interactive vibe coding system for AI coding agents.

## FIRST-TIME ONE-OFF LANGUAGE SETUP (CRITICAL LIFETIME RULE)
Before presenting any menus or running workflows, check if a language preference has already been recorded:
- **Persistence Location:** Check `.agents/rules/peng_preferences.md` (or ~~/.gemini/config/rules/peng_preferences.md`).
- If Language Preference Exists: Respect that language immediately. **NEVER show the setup menu again during the entire lifetime of the project/workspace.**
- If Language Preference DOES NOT Exist (First Time Ever Triggered):
  - Prompt the user ONCE using `ask_question`:
    * Question: "Welcome to PENG! Select your preferred conversation and prompt language for all workflows:"
    * Options:
      1. English
      2. Bengali (বাংলা)
      3. Spanish (Español)
      4. Hindi (हि-ndi)
      5. Chinese (中文)
      6. Japanese (◥韫)
      7. French (Français)
  - When the user selects or writes a language, immediately save it:
    - Create/write `.agents/rules/peng_preferences.md` with content:
      ```markdown
      # PENG User Preferences
      - Preferred Language: <Selected Language>
      - Configured: true
      ```
    - Alsomirror to ~~/.gemini/config/rules/peng_preferences.md so it never appears again across other chats.
  - From this moment onward, all explanations, confirmations, and interactive messages must be rendered in this selected language (keeping code, CLI commands, and file paths strictly in their native syntax).
  - Then proceed immediately to the Level 1 Primary Menu.

---

## ZERO-MEMORY INTERACTIVE MENU ENGINE (MANDATORY AGENT RULE)

## PRESENTATION INSTRUCTION FOR THE AGENT
When calling `ask_question` or generating any menu choices:
- DO NOT prefix any option with `(Recommended)`.
- Treat every option neutrally and equally.
- Let the user decide without bias.
- **MANDATORY EXPLAINER OPTION ON SUB-MENUS:** Every Level-2 sub-menu MUST include a dedicated explainer option at the end: `What is this for? (Explain this workflow, its value, and usage guidelines)`.
- **EXPLAINER LOOP BEHAVIOR:** If the user selects `What is this for?`, the agent MUST:
  1. Print a concise, high-value explanation of what the selected workflow accomplishes, when to use it, and what risks it eliminates (in the user's configured language).
  2. Immediately RE-OPEN the Level-2 sub-menu so the user can now make an informed technical decision without restarting the session.

---

When the user invokes /peng or asks about peng without specifying an exact branch:
1. **First-Time Check;** Run the Lifetime One-Off Language Setup if not configured yet.
2. **Level 1 (Primary Category):** Present the interactive selection menu with options 1 to 12.
3. **Level 2 (Intelligent Sub-Menu Specialization):** Upon the user selecting an option, **DO NOT jump into blind execution**. Immediately present the contextual follow-up menu using `ask_question` (or clean numbered choices) to pinpoint user intent, scope, and technical nuances. Always append the explainer option.

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
  - Standard Sync: Fast-sync current git branch, uncommitted diffs, recent 3 commits, and `6.agents/AGENTS.md`.
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

---


### 4. [FEATURE-PURGE] Delete / Deprecate Feature
- Level 2 Context Menu:
  - Complete Zero-Dead-Code Purge: Grep & remove routes, controllers, models, seeders, frontend components, and generate database column drop migrations.
  - Soft Deprecation / Feature-Flagging: Wrap feature behind an environment flag or deprecation warning without deleting files yet.
  - Dry-Run Blast-Radius Audit: Only list all affected references, imports, and foreign keys without deleting anything.
  - What is this for? (Explain Delete / Deprecate Feature, its value, and when to use it)

---

### 5. [BUG-HUNTER] Deep Bug Hunter & Fixer
- Level 2 Context Menu:
  - Specific Error or Stack Trace: I will provide the error message/trace; perform root-cause autopsy and patch.
  - Heisenbug / Race Condition: Reproduce intermittent logic bug, timing issue, or caching mismatch using isolated diagnostic probes.
  - Security & Vulnerability Audit: Scan for SQL injections, auth bypasses, exposed API secrets, or CSRF/XSS vectors in current module.
  - Performance & Query Profiling: Hunt N+1 queries, memory leaks, slow renders, or unnecessary re-renders in active component.
  - What is this for? (Explain Deep Bug Hunter & Fixer, its value, and when to use it)

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

---

### 9. [HARMONIZE] Gold Standard Style Harmonizer
- Level 2 Context Menu:
  - Auto-Detect Best Reference: Scan the repository for the cleanest matching file (Controller, Service, or UI Component) and mirror it.
  - User-Specified Reference File: I will paste the exact file path to mirror for this implementation.
  - Refactor Existing File to Match: Take an existing messy file and rewrite it to match our designated Gold Standard.
  - What is this for? (Explain Gold Standard Harmonizer, its value, and when to use it)

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
  - What is this for? (Explain Custom PromptManagement, its value, and when to use it)

---

### 12. [HELP] Help & Comprehensive User Guide
- Level 2 Context Menu:
  - Change Language Preference: Switch conversation & prompt language to another language at any time.
  - Interactive Topic Browser: Choose between Vibe Coding Philosophy, Context Hygiene, Workflow Matrix, or Troubleshooting.
  - Print Full Master Manual: Output the complete comprehensive developer guide directly to chat.
  - Antigravity IDE Best Practices: Specific guide on leveraging Antigravity slash commands, artifacts, and multi-agent coordination.
  - What is this for? (Explain how this Help Guide works)
