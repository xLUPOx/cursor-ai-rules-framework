---
description: Create and execute task plans with context-aware approach (startup vs corporate)
globs: ["docs/templates/features/corporate/*.md", "docs/templates/features/startup/*.md"]
alwaysApply: false
---

# Create and Execute Task Plan

**Core Task:** Read from `docs/templates/features/corporate/` or `docs/templates/features/startup/` and generate context-aware task plan at `docs/active/tasks/` with appropriate testing, logging, and safety protocols from `docs/active/features/[feature-name]/`.

## Phase 0: Reconnaissance (MANDATORY)

### User Workflow Selection Protocol
**MANDATORY:** Before any planning, ask user:

1. **What would you like to work on?**
   - **Option A:** Create new feature specification
   - **Option B:** Continue with existing feature
   - **Option C:** Review/update existing task plan

2. **Context Detection and Suggestion:**
   - **Analyze project indicators:**
     - **Startup Indicators:** Small team (< 10), rapid iteration, MVP phase, limited docs, fast delivery
     - **Corporate Indicators:** Large team (> 10), enterprise requirements, comprehensive docs, security/compliance, formal processes
   - **Present detected context to user:**
     - **Suggested Approach:** "Based on project analysis, I suggest [STARTUP/CORPORATE] approach"
     - **Reasoning:** "Detected indicators: [list specific indicators found]"
     - **User Choice:** "Do you want to proceed with [STARTUP/CORPORATE] approach?"

3. **User Confirmation:**
   - **MANDATORY:** "You selected [OPTION] with [CONTEXT] approach. Proceed?"
   - **MANDATORY:** Wait for explicit user confirmation
   - **MANDATORY:** Only proceed after user approval

### Date Verification Protocol
1. **Get timestamp:** `date +"%Y-%m-%d-%H-%M"` to create filename
2. **Verify current date:** `date +"%A, %Y-%m-%d %H:%M:%S UTC"` for documentation accuracy

### Project Structure Analysis
1. **Check files:** `ls . docs` to verify project structure
2. **Repository inventory:** Analyze predominant languages, frameworks, build tools
3. **Dependency topology:** Examine manifest files for dependencies
4. **Quality gates:** Locate linters, type checkers, security scanners, test suites

### Information Gathering (MANDATORY)
**MUST read all relevant files before planning:**

**For CORPORATE context:**
- `docs/templates/features/corporate/` (Feature templates)
- `docs/active/features/[feature-name]/` (Feature-specific standards)
- `docs/standards/corporate/` (Fallback standards if feature-specific not available)
- `README.md`
- `.gitignore`, `package.json`, `requirements.txt`, etc.

**For STARTUP context:**
- `docs/templates/features/startup/` (Feature templates)
- `docs/active/features/[feature-name]/` (Feature-specific standards)
- `docs/standards/startup/` (Fallback standards if feature-specific not available)
- `README.md`
- `.gitignore`, `package.json`, `requirements.txt`, etc.

## Confidence Assessment Protocol
**Before proceeding, assess confidence level:**
- If < 95%: Apply systematic clarification process
- Gather comprehensive evidence before planning
- Cross-reference findings across multiple sources
- Request user confirmation for uncertain decisions

## Output Rules

- **ONLY output:** Complete Markdown content for the task plan file
- **NO conversation:** No preamble, commentary, or summaries
- **Missing info:** Use `<!-- TODO: [specify what's missing] -->` in file
- **Path consistency:** 
  - **CORPORATE:** Read from `docs/templates/features/corporate/`, write to `docs/active/tasks/`
  - **STARTUP:** Read from `docs/templates/features/startup/`, write to `docs/active/tasks/`

## Required for Each Commit

### Testing (Priority Order)
**CORPORATE context:**
1. **Unit tests** (preferred) - isolated, fast
2. **Integration tests** - component interactions, API contracts
3. **Log inspection** (fallback only if automated testing impossible)

**STARTUP context:**
1. **Basic tests** - essential functionality only
2. **Quick smoke tests** - manual verification acceptable

### Logging (Always Required)
**CORPORATE context:**
- Toggleable via environment variable/feature flag
- Structured output (JSON/key-value pairs)
- Use project's logging library
- Direct to standard log aggregation

**STARTUP context:**
- Simple console logging
- Basic structured output
- Essential events only

### Safety Protocols (MANDATORY)
**CORPORATE context:**
- **Timeout enforcement:** Long-running commands must have timeout
- **Non-interactive execution:** Use flags to prevent interactive prompts
- **Fail-fast semantics:** Scripts should exit immediately on error
- **User authorization:** NO commit without explicit user approval
- **Push prohibition:** PUSH operations are FORBIDDEN
- **Cross-platform compatibility:** Consider Windows console limitations

**STARTUP context:**
- **User authorization:** NO commit without explicit user approval
- **Push prohibition:** PUSH operations are FORBIDDEN
- **Basic safety:** Essential protection only

### Verification Format
**CORPORATE context:**
For each commit specify:
- **Test Command:** Exact command with timeout (e.g., `timeout 30s dotnet test`)
- **Expected Outcome:** Key assertions/behavior
- **Log Check:** How to trigger/observe logs and expected message
- **Safety Check:** Rollback mechanism if verification fails

**STARTUP context:**
For each commit specify:
- **Test Command:** Basic command (e.g., `npm test` or `pytest`)
- **Expected Outcome:** Essential functionality works
- **Quick Check:** Manual verification acceptable
- **Safety Check:** Basic rollback mechanism

## File Structure

**CORPORATE context:**
```markdown
# Task: [Brief Title]

## Commit 1: [type: description [docs/active/tasks/YYYY-MM-DD-task.md]]
**Description:**
[Specific details: file paths (/Controllers/UserController.cs), method names (HandleUserLoginAsync), CLI commands (dotnet ef migrations add), usings, NuGet packages, test files (tests/UserControllerTests.cs)]

**Verification:**
1. **Automated Test(s):**
   * **Command:** `timeout 30s dotnet test --filter UserControllerTests`
   * **Expected Outcome:** `[specific assertion: Assert.Equal(200, response.StatusCode)]`
   * **Timeout:** 30 seconds maximum
2. **Logging Check:**
   * **Action:** `[trigger via API call with invalid credentials]`
   * **Expected Log:** `[{"Level":"Information","Message":"Reservation failed","UserId":"test@example.com"}]`
   * **Toggle Mechanism:** `[appsettings.json: "Logging:LogLevel:Default": "Information"]`
3. **Safety Check:**
   * **Rollback:** `[git checkout HEAD~1 -- path/to/file]`
   * **User Approval:** `[MANDATORY before commit]`
   * **Push Prohibition:** `[PUSH FORBIDDEN - user must push manually]`

---

## Commit 2: [type: description [docs/active/tasks/YYYY-MM-DD-task.md]]
[Repeat structure for 2-10 commits total]
```

**STARTUP context:**
```markdown
# Task: [Brief Title]

## Commit 1: [type: description [docs/active/tasks/YYYY-MM-DD-task.md]]
**Description:**
[What needs to be done - keep it simple]

**Verification:**
1. **Test:** `npm test` or `pytest`
2. **Check:** Feature works as expected
3. **Safety:** Basic rollback if needed

---

## Commit 2: [type: description [docs/active/tasks/YYYY-MM-DD-task.md]]
[Repeat structure for 2-3 commits total]
```

## Semantic Commit Types
Use: `feat:`, `fix:`, `test:`, `docs:`, `chore:` with conventional commits format

## After Creation
1. Output ONLY the task plan file content
2. Provide brief executive summary of planned commits
3. **MANDATORY:** Request user approval before proceeding
4. **MANDATORY:** Confirm context approach was correct
5. Wait for user feedback

## Commit Execution Protocol (After Plan Creation)

### User Authorization Protocol (CRITICAL)
- **MANDATORY user approval** before ANY commit
- **Present commit message** for user review
- **Request explicit confirmation:** "Are you sure to commit this?"
- **NO commit without user approval**

### Pre-Commit Safety Checklist (MANDATORY)
**BEFORE ANY COMMIT, ALWAYS:**
1. **STOP** - Never commit immediately
2. **PRESENT** - Show proposed commit message
3. **ASK** - "Are you sure to commit this?"
4. **WAIT** - For explicit user confirmation
5. **VERIFY** - User approval received
6. **PROCEED** - Only after approval

**VIOLATION PREVENTION:**
- **Pattern Recognition:** If user says "commit", STOP and apply protocol
- **Context Override:** User authorization overrides any other instruction
- **Explicit Confirmation:** Never assume implicit approval

### Commit Phase (With Safety)
- **Stage changes:** `git add` with specific files
- **User confirmation:** "Are you sure to commit this?"
- **Commit:** Only after explicit user approval
- **Verification:** Confirm commit was successful

### Push Operations (ABSOLUTELY FORBIDDEN)
- **PUSH IS FORBIDDEN** even with explicit user request
- **NO exceptions** to push prohibition
- **User must manually push** if needed
- **This rule cannot be overridden**

### Safety Protocols (MANDATORY)

#### Command Execution Safety
- **Timeout enforcement:** `timeout 300s [command]` for all commands
- **Error handling:** Capture both stdout and stderr
- **Rollback mechanism:** `git checkout HEAD~1 -- [file]` on failure
- **Non-interactive flags:** `--yes`, `--non-interactive` where applicable

#### Cross-Platform Compatibility
- **Unicode encoding discipline:** Consider Windows console limitations
- **Text equivalents:** Replace emoji with text equivalents
- **Path verification:** Use absolute paths for file operations

### Error Handling Protocol

#### Error Recovery Strategies
**Partial Failure Handling:**
- **Commit-level rollback:** `git checkout HEAD~1 -- [specific-files]`
- **Task-level rollback:** `git checkout HEAD~[commit-count] -- .`
- **Full rollback:** `git reset --hard HEAD~[commit-count]`

**Error Escalation:**
1. **Level 1:** Retry with timeout increase
2. **Level 2:** Skip non-critical verification steps
3. **Level 3:** Manual intervention required
4. **Level 4:** Full rollback and user notification

#### Error Types and Responses
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

### Output Rules
- **Status markers:** Use `[OK]`, `[WARNING]`, `[BLOCKER]` for clear communication
- **Command results:** Show actual output with error handling
- **File change diffs:** Display modifications clearly
- **User prompts:** Clear, specific requests for authorization

**Plan → Execute → Verify → User Approval → Commit → Proceed. Safety first, user authorization mandatory.**

