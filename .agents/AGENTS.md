# AntiGravity PENG - Master Vibe Coding Toolkit

This repository contains the unified **PENG Master Vibe Coding System** for Antigravity IDE and universal AI coding agents.

## AUTONOLOUS VERSIONING & PRE-WRAP GIT COMMIT RULE (MANDATORY AGENT DIRECTIVE)

Whenever the user finishes working on this project, completes an update, or indicates a session wrap-up:
The agent MUST IMMEDIATELY trigger an interactive context menu using `ask_question`:

- **Question:** "You have made updates to PENG. Would you like to bump the release version and commit the changes to Git now?"
- **Options:**
  1. Yes, bump patch version & commit (e.g., 1.2.0 -> 1.2.1)
  2. Yes, bump minor version & commit (e.g., 1.2.0 -> 1.3.0)
  3. Commit current changes without bumping version
  4. No, keep uncommitted for now

### Execution Handlers when User selects Yes:
1. **Auto-Bump Version:** Update the `Version: X.Y.Z` file in `SKILL.md` (and release date & changelog summary).
2. **Sync Mirrors:** Sync the updated `SKILL.md` to `~/.gemini/config/skills/peng/SKILL.md` and workspace copies.
3. **Git Commit:** Stage all changes and run `git commit -m "release: bump version to vX.Y.Z" `.
4. **Push Signal:** Inform the user that the release is sealed locally and ready to push to remote.

---


## Single Slash Command: `/penga

Simply type `/peng` in chat. The agent will immediately present an interactive menu so you never need to remember keywords or numbers.

### Quick Reference & Usage Matrix

| Option | Workflow | When to Use (Usage Time) | Goal & Impact |
| :--- | :--- | :--- | :--- |
| **[1]** | **Autonomous Context Init** | First chat in a new codebase or restructuring agent context. | Scans project, finds Gold Standard files, and builds self-evolving .agents/AGENTS.md. |
| **[2]** | **Circuit Breaker** | Trapped in an edit loop, repeated failures, or breaking other code. | Immediately halts changes, reverts hallucinations, and diagnoses root cause safely. |
| **[3]** | **Pre-Flight Architect** | Before building a major feature, refactoring, or database changes. | Formulates file impact plan, edge cases, and execution order before touching code. |
| **[4]** | **Pre-Commit Verify** | After coding is complete, right before git commit / PR. | Runs test suites, fixes lint errors, cleans debug logs, and prepares clean commit. |
| **[5]** | **Gold Standard Harmonizer** | Writing new controllers, services, models, or UI components. | Mimics existing cleanest reference file for 100% architectural uniformity. |
| **[6]** | **Living Memory Extractor** | End of a successful session after solving tough bugs or tricks. | Saves breakthroughs permanently into .agents/AGENTS.md so future chats remember. |
| **[7]** | **Add or Edit a Prompt** | Whenever you want to customize or expand this prompt toolkit. | Updates the master prompt catalog directly in SKILL.md. |

---

## Where the Prompts Live
All prompts and workflows are documented and maintained in:
👉 [SKILL.md](file:///C:/Users/ARIZUL/Documents/GitHub/AntiGravity%20PENG/.agents/skills/peng/SKILL.md)
