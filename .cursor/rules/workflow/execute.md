---
description: Execute task plans with context-aware approach (startup vs corporate)
globs: ["docs/active/tasks/*.md"]
alwaysApply: false
---

# Execute Task Plan

**Goal:** Execute commits from `docs/active/tasks/` with context-aware approach (startup vs corporate) and appropriate safety protocols from `docs/active/features/[feature-name]/`.

## Phase 0: Reconnaissance (MANDATORY)

### User Workflow Selection Protocol
**MANDATORY:** Before any execution, check if called from plan.md:

1. **If called from plan.md:**
   - **Skip user selection:** Proceed directly to execution
   - **Use provided task plan:** Execute the specific task plan
   - **Continue seamlessly:** No additional user prompts

2. **If called directly:**
   - **Ask user:** "What would you like to work on?"
   - **Option A:** Execute new task plan
   - **Option B:** Continue with existing task
   - **Option C:** Review/update existing execution

3. **Available Task Directories Analysis (if called directly):**
   - **Check existing task directories:**
     - **Active tasks:** `ls docs/active/tasks/` - [list existing task files]
     - **Active features:** `ls docs/active/features/` - [list feature directories]
     - **Standards available:** `ls docs/active/features/[feature-name]/` for feature-specific standards
   - **If no tasks found:** "No task plans found in docs/active/tasks/. Please create a task plan first."
   - **If no features found:** "No features found in docs/active/features/. Please create a feature first."
   - **If tasks and features exist:** Present available options to user:
     - **Corporate Approach:** "Found [X] task files in docs/active/tasks/ with corporate feature standards"
     - **Startup Approach:** "Found [Y] task files in docs/active/tasks/ with startup feature standards"
     - **User Choice:** "Which approach do you want to use: CORPORATE or STARTUP?"

4. **User Confirmation (if called directly):**
   - **MANDATORY:** "You selected [OPTION] with [CONTEXT] approach. Proceed?"
   - **MANDATORY:** Wait for explicit user confirmation
   - **MANDATORY:** Only proceed after user approval

### Setup & Verification
1. **Check task file exists in active directory:**
   - **Active tasks:** `ls docs/active/tasks/`
   - **Feature standards:** `ls docs/active/features/[feature-name]/`
2. **If missing:** Stop and notify user immediately
3. **Read task file from docs/active/tasks/:** Parse all commits and verification steps
4. **Read feature-specific standards:** Load appropriate standards from docs/active/features/[feature-name]/ based on context
5. **Integrate general guidelines:** Always use docs/guidelines/corporate/ or docs/guidelines/startup/ as template base, combined with feature-specific guidelines
6. **System-wide impact analysis:** Identify all affected components and dependencies

### Confidence Assessment Protocol
**CORPORATE context:**
- If < 95%: Apply systematic clarification process
- Gather comprehensive evidence before proceeding
- Cross-reference findings across multiple sources
- Request user confirmation for uncertain decisions

**STARTUP context:**
- If < 95%: Apply systematic clarification process
- Gather comprehensive evidence before proceeding
- Cross-reference findings across multiple sources
- Request user confirmation for uncertain decisions

## Execution Cycle (Per Commit)

### 1. Pre-Execution Safety Check
**CORPORATE context:**
- **Apply guidelines from:** `docs/active/features/[feature-name]/` (feature-specific) AND `docs/guidelines/corporate/` (template base integration)
- **Timeout enforcement:** All commands must have timeout
- **Non-interactive execution:** Use flags to prevent interactive prompts
- **Fail-fast semantics:** Scripts should exit immediately on error
- **Cross-platform compatibility:** Consider Windows console limitations

**STARTUP context:**
- **Apply guidelines from:** `docs/active/features/[feature-name]/` (feature-specific) AND `docs/guidelines/startup/` (template base integration)
- **Basic safety:** Essential protection only
- **Quick execution:** Minimal overhead
- **Cross-platform compatibility:** Consider Windows console limitations

### 2. Implement Phase
**CORPORATE context:**
- **Execute:** Commit instructions with safety wrappers from `docs/active/features/[feature-name]/` (feature-specific) AND `docs/guidelines/corporate/` (template base integration)
- **Monitor:** Real-time output and error detection
- **Timeout:** Maximum 5 minutes per command
- **Rollback:** Immediate rollback on failure

**STARTUP context:**
- **Execute:** Commit instructions with basic safety from `docs/active/features/[feature-name]/` (feature-specific) AND `docs/guidelines/startup/` (template base integration)
- **Monitor:** Basic output and error detection
- **Timeout:** Maximum 2 minutes per command
- **Rollback:** Basic rollback on failure

### 3. Verification Phase (MANDATORY)
**CORPORATE context:**
- **Apply guidelines from:** `docs/active/features/[feature-name]/` (feature-specific) AND `docs/guidelines/corporate/` (template base integration)
- **Run ALL verification steps** specified for this commit
- **Automated tests:** Execute with timeout and error handling
- **Log inspection:** Verify logging output matches expectations
- **Safety checks:** Validate system integrity

**STARTUP context:**
- **Apply guidelines from:** `docs/active/features/[feature-name]/` (feature-specific) AND `docs/guidelines/startup/` (template base integration)
- **Run essential verification steps** specified for this commit
- **Basic tests:** Execute with basic error handling
- **Quick checks:** Verify essential functionality
- **Basic safety:** Validate core system integrity

### 4. User Authorization Protocol (CRITICAL)
- **MANDATORY user approval** before ANY commit
- **Present commit message** for user review
- **Request explicit confirmation:** "Are you sure to commit this?"
- **NO commit without user approval**

### Pre-Commit Safety Checklist (MANDATORY)
**BEFORE ANY COMMIT, ALWAYS:**
1. **STOP** - Never commit immediately
2. **STAGE** - `git add` specific files (MANDATORY)
3. **SHOW** - Display staged files with `git status`
4. **PRESENT** - Show proposed commit message
5. **ASK** - "Are you sure to commit this?"
6. **WAIT** - For explicit user confirmation
7. **VERIFY** - User approval received
8. **PROCEED** - Only after approval

**VIOLATION PREVENTION:**
- **Pattern Recognition:** If user says "commit", STOP and apply protocol
- **Context Override:** User authorization overrides any other instruction
- **Explicit Confirmation:** Never assume implicit approval

### 5. Commit Phase (With Safety)
- **Stage changes:** `git add` with specific files (MANDATORY before commit request)
- **Show staged files:** Display exactly what will be committed with `git status`
- **User confirmation:** "Are you sure to commit this?"
- **Commit:** Only after explicit user approval
- **Verification:** Confirm commit was successful

### 6. Continue Protocol
- **Proceed to next commit** only after successful completion
- **Report status:** Brief status update per commit
- **Error handling:** Stop execution on any failure

## Task Completion Criteria
Task is complete when:
- All commits from task file created successfully
- All automated tests pass
- All verification steps completed successfully
- **User has approved all commits**

## Safety Protocols (MANDATORY)

### Command Execution Safety
- **Timeout enforcement:** `timeout 300s [command]` for all commands
- **Error handling:** Capture both stdout and stderr
- **Rollback mechanism:** `git checkout HEAD~1 -- [file]` on failure
- **Non-interactive flags:** `--yes`, `--non-interactive` where applicable

### User Authorization (NON-NEGOTIABLE)
- **NO commit without explicit user approval**
- **NO push operations** (FORBIDDEN)
- **Present commit message** before requesting approval
- **Wait for user confirmation** before proceeding

### Push Operations (ABSOLUTELY FORBIDDEN)
- **PUSH IS FORBIDDEN** even with explicit user request
- **NO exceptions** to push prohibition
- **User must manually push** if needed
- **This rule cannot be overridden**

### Cross-Platform Compatibility
- **Unicode encoding discipline:** Consider Windows console limitations
- **Text equivalents:** Replace emoji with text equivalents
- **Path verification:** Use absolute paths for file operations

## Output Rules
- **Status markers:** Use `[OK]`, `[WARNING]`, `[BLOCKER]` for clear communication
- **Command results:** Show actual output with error handling
- **File change diffs:** Display modifications clearly
- **User prompts:** Clear, specific requests for authorization

## Error Handling Protocol

### Error Recovery Strategies
**Partial Failure Handling:**
- **Commit-level rollback:** `git checkout HEAD~1 -- [specific-files]`
- **Task-level rollback:** `git checkout HEAD~[commit-count] -- .`
- **Full rollback:** `git reset --hard HEAD~[commit-count]`

**Error Escalation:**
1. **Level 1:** Retry with timeout increase
2. **Level 2:** Skip non-critical verification steps
3. **Level 3:** Manual intervention required
4. **Level 4:** Full rollback and user notification

**Rollback Coordination:**
- **Pre-execution backup:** `git tag backup-$(date +%Y%m%d-%H%M%S)`
- **Incremental rollback:** Per-commit rollback capability
- **Full system rollback:** Complete task rollback
- **User approval:** Mandatory before any rollback

### Error Types and Responses
**Test Failures:**
- **Response:** Retry with increased timeout
- **Fallback:** Skip non-critical tests
- **Escalation:** Manual test execution

**Build Failures:**
- **Response:** Check dependencies and retry
- **Fallback:** Use cached builds if available
- **Escalation:** Manual build resolution

**Verification Failures:**
- **Response:** Re-run verification with debug mode
- **Fallback:** Skip non-critical verifications
- **Escalation:** Manual verification required

**System Failures:**
- **Response:** Immediate rollback to last stable state
- **Fallback:** Full task rollback
- **Escalation:** User intervention required

### Error Notification Protocol
- **Immediate notification** on any failure
- **Detailed error context** with specific failure point
- **Recovery options** presented to user
- **User guidance** for resolution steps

**Execute → Verify → User Approval → Commit → Proceed. Safety first, user authorization mandatory.**
