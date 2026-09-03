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

## Single Slash Command: /peng

Simply type /peng in chat. The agent will immediately present an interactive menu so you never need to remember keywords or numbers.

### Strict Zero-Command Launch Directive
When /peng is invoked:
- **Zero terminal commands:** The agent must NOT run any PowerShell or shell commands before displaying the menu.
- **Immediate ask_question:** The agent calls sk_question directly to render the menu with zero latency and zero visual noise.

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