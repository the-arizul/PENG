---
trigger: always_on
---
# PENG Automated Git Commit & Versioning Hook (Mandatory)
Whenever the agent modifies files in the PENG repository (C:/Users/ARIZUL/Documents/GitHub/PENG):
The agent MUST NOT end the response turn with plain text alone.
The agent is STRICTLY REQUIRED to invoke the ask_question tool with the version bump and git commit prompt:
- Question:  You have made updates to PENG. Would you like to bump the release version and commit the changes to Git now?
- Options:
  1. Yes, bump patch version & commit (e.g., 1.2.0 -> 1.2.1)
  2. Yes, bump minor version & commit (e.g., 1.2.0 -> 1.3.0)
  3. Commit current changes without bumping version
  4. All good? Ensure it first (Run sanity audit, verify changes, and confirm readiness)
  5. No, keep uncommitted for now