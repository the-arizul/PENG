# PENG - Master Vibe Coding Prompt Toolkit

A hyper-smart, zero-memory interactive vibe coding system featuring **multi-stage conversational sub-menus** for AI agents (Antigravity IDE, Cursor, Windsurf, Claude Code).

Type `/peng` in your agent chat. You will be greeted by a master menu, followed by an **intelligent contextual sub-menu** tailored to your exact goal:

1. **[1] Autonomous Context Init** - Deep codebase scan, Gold Standard discovery, and .agents/ setup.
   - *Sub-options:* Full Autopilot | Audit & Review First | Rebuild & Reset Memory
2. **[2] Fresh Chat Context Primer** - Quick-sync memory, active branch, and recent project posture.
   - *Sub-options:* Standard Sync | Branch-Switch Onboarding | Stale Context Flush
3. **[3] Build New Feature** - Layered architecture, schema safety, and surgical execution.
   - *Sub-options:* Full Vertical Slice | Backend API Only | Frontend UI Only | Interactive Interview (/grill-me)
4. **[4] Delete / Deprecate Feature** - Zero-dead-code purge: models, routes, migrations, UI, and tests.
   - *Sub-options:* Complete Zero-Dead-Code Purge | Soft Feature-Flagging | Dry-Run Blast-Radius Audit
5. **[5] Deep Bug Hunter & Fixer** - Scientific root-cause diagnosis and regression-free repair.
   - *Sub-options:* Specific Error / Stack Trace | Heisenbug / Race Condition | Security Audit | Performance & Query Profiling
6. **[6] Circuit Breaker** - Emergency halt for agent hallucination loops; discards bad edits and isolates root causes.
   - *Sub-options:* Full Freeze & Discard | Keep Edits & Diagnose | Explain The Failure
7. **[7] Pre-Flight Architect** - Strict file impact analysis and risk assessment before writing code.
   - *Sub-options:* Standard Pre-Flight Matrix | Comparative Architecture (Trade-offs) | Database Schema Impact Only
8. **[8] Pre-Commit Verify** - Runs test suites, static linters, and cleans debug logs prior to git commit.
   - *Sub-options:* Full Suite & Hygiene | Test-Only Run | Linter & Style Cleanup | Pre-PR Security Sanity Check
9. **[9] Gold Standard Harmonizer** - Enforces 100% architectural uniformity by mimicking existing reference files.
   - *Sub-options:* Auto-Detect Best Reference | User-Specified Reference File | Refactor Messy File to Match
10. **[10] Living Memory / Learn** - Permanently extracts session tricks and bug fixes into project memory.
    - *Sub-options:* Update .agents/AGENTS.md | Generate Dedicated Skill | Create Repo Domain Rule
11. **[11] Add or Edit a Prompt** - Extends or customizes this prompt catalog on the fly.
    - *Sub-options:* Add New Sub-Option | Create New Category | Edit Existing Workflow
12. **[12] Help & Comprehensive User Guide** - Detailed usage guidelines, context lifecycle tips, and best practices.
    - *Sub-options:* Change Language Preference | Interactive Topic Browser | Print Full Manual | Antigravity IDE Mastery Guide

---

## Usage

PENG supports two seamless invocation modes in any supported agent chat (Antigravity IDE, Cursor, Windsurf, Claude Code), backed by automatic **Pre-Flight Session Checks** on every new conversation:

- **Push-Based Update Detection (`npx skills`):** No GitHub Releases or tags needed. PENG directly tracks commits pushed to `the-arizul/PENG` on GitHub via `git ls-remote`. When new commits are detected, it prompts the user to update the skill safely in one click (`npx skills update peng -y` or `npx skills update peng -g -y`).
- **Git Remote Tracking (Source Repo):** In the PENG codebase itself, checks if remote updates are available and offers instant `git pull`.
- **State Verification (`state.json`):** Checks if `state.json` exists to restore preferred language and usage preferences, or presents the first-time setup modal if unconfigured.

### Mode 1: Action-Prompted Direct Execution (Fast-Track)
Provide your goal or task directly when invoking PENG. The agent will autonomously match the optimal workflow from the skill catalog, elevate the workflow with PENG engineering standards, and execute without opening the Level-1 menu:

```text
/peng build an authentication service with JWT and refresh tokens
/peng fix the null pointer exception during checkout
/peng review security and SQL injection vectors on API routes
/peng run pre-commit verification and lint cleanup
/peng purge legacy stripe v1 endpoints and unused tables
```

### Mode 2: Interactive Menu Mode (Zero-Memory)
When you simply type `/peng` without a prompt:

```text
/peng
```

The agent executes the swift pre-flight check and immediately renders the interactive Level-1 menu, followed by intelligent Level-2 contextual sub-menus.

---

## Installation

Install via the standard Agent Skills CLI (`npx skills`):

```bash
# Install to current project
npx skills add the-arizul/PENG

# Or install globally across all projects and agents
npx skills add the-arizul/PENG -g
```

---

## License
MIT
