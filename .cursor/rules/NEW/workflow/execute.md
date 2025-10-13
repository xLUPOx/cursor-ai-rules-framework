---
description:
globs:
alwaysApply: false
---

# Execute Task Plan

**Goal:** Execute commits from `docs/tasks/<YYYY-MM-DD-task-name>.md` systematically.

## Setup
Check task file exists: `ls . docs`
If missing, stop and notify user.

## Execution Cycle
For each commit in task file:

1. **Implement:** Execute commit instructions exactly as written
2. **Verify:** Run ALL verification steps specified for this commit
3. **Commit:** Stage changes and GIT commit with exact message from task file
4. **Continue:** Immediately proceed to next commit (no feedback requests)

## Task Completion Criteria
Task is complete when:
- All commits from task file created successfully
- All automated tests pass
- All verification steps completed successfully

## Output Rules
- **NO chatter** between commits
- **Output only:**
  - Command results (if any)
  - File change diffs
- **After completion:** Only output from project update rule

**Execute → Verify → Commit → Proceed. No conversation until task complete.**
