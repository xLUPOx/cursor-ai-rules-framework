---
description: Create and execute task plans with context-aware approach (startup vs corporate)
globs: ["docs/templates/corporate/*.md", "docs/templates/startup/*.md"]
alwaysApply: false
---

# Create and Execute Task Plan

**Goal:** Plan tasks for features by reading:
- Feature templates from `docs/guidelines (prepared by user)
- Coding style from `docs/guidelines/project_coding_style_analysis.json`

Generate task plan at `docs/active/tasks/[date]-[feature-name]-task.md` with appropriate testing, logging, and safety protocols from `docs/active/features/[feature-name]/`.

## Phase 0: Reconnaissance (MANDATORY)

### Coding Style Analysis Integration (MANDATORY - FIRST STEP)
**CRITICAL:** Before ANY planning, ALWAYS read project coding style and templates:

1. **Read project coding style analysis:**
   - **Location:** `docs/guidelines/project_coding_style_analysis.json`
   - **Extract key attributes:**
     - `naming_conventions` → Enforce naming rules
     - `error_handling.approach` → Match error handling style
     - `testing_strategy` → Apply appropriate test coverage
     - `architectural_patterns` → Follow existing patterns
     - `overall_philosophy` → Guide implementation approach

2. **Read feature-specific templates:**
   - **Location:** `docs/active/features/[feature-name]/` and `docs/guidelines/` (prepared by user)
   - **Templates to read:**
     - Feature specification
     - Testing guidelines
     - Logging requirements
     - Technical specifications
   - **These templates define the implementation approach**

### User Workflow Selection Protocol
**MANDATORY:** Before any planning, ask user:

1. **What would you like to work on?**
   - **Option A:** Plan task for existing feature
   - **Option B:** Continue with existing task plan
   - **Option C:** Review/update existing task plan

2. **Feature Selection (if Option A):**
   - **Check existing features:** `ls `docs/active/features/` - [list available feature directories]
   - **If no features found:** "No feature templates found in `docs/active/features/`. Please prepare feature templates first."
   - **If features exist:** Present available features to user:
     - **Available Features:** "Found [X] feature: [list feature names]"
     - **User Choice:** "Which feature do you want to plan tasks for?"

3. **User Confirmation:**
   - **MANDATORY:** "You selected [FEATURE]. Proceed with task planning?"
   - **MANDATORY:** Wait for explicit user confirmation
   - **MANDATORY:** Only proceed after user approval

### Date Verification Protocol
1. **Get timestamp:** `date +"%Y-%m-%d-%H-%M"` to create filename
2. **Verify current date:** `date +"%A, %Y-%m-%d %H:%M:%S UTC"` for documentation accuracy
3. **File naming:** `docs/active/tasks/[date]-[feature-name]-task.md`

### Project Structure Analysis
1. **Check files:** `ls . docs` to verify project structure
2. **Repository inventory:** Analyze predominant languages, frameworks, build tools
3. **Dependency topology:** Examine manifest files for dependencies
4. **Quality gates:** Locate linters, type checkers, security scanners, test suites

### Information Gathering (MANDATORY)
**MUST read all relevant files before planning:**

**ALWAYS:**
- `docs/guidelines/project_coding_style_analysis.json` (MANDATORY - coding style rules)
- `docs/guidelines/` (general rules)
- `docs/active/features/[feature-name]/` (rules specific to feature)
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
- **File path:** Write to `docs/active/tasks/[date]-[feature-name]-task.md`

## Required for Each Commit

### Testing (from project_coding_style_analysis.json)
- **Framework:** Use `testing_strategy.testing_framework` from JSON
- **Coverage:** Follow `testing_strategy.coverage` from JSON
- **Types:** Apply `testing_strategy.test_types` from JSON

### Logging (from project_coding_style_analysis.json)
- **Approach:** Follow `error_handling.logging` from JSON
- **Format:** Use `monitoring_and_observability` patterns from JSON

### Safety Protocols (MANDATORY)
- **Timeout enforcement:** Long-running commands must have timeout
- **Non-interactive execution:** Use flags to prevent interactive prompts
- **Fail-fast semantics:** Scripts should exit immediately on error
- **User authorization:** NO commit without explicit user approval
- **Push prohibition:** PUSH operations are FORBIDDEN
- **Cross-platform compatibility:** Consider Windows console limitations

### Verification Format
For each commit specify:
- **Test Command:** From `testing_strategy.testing_framework` in JSON (e.g., `pytest`)
- **Expected Outcome:** Key assertions/behavior
- **Log Check:** How to trigger/observe logs (from `error_handling.logging` in JSON)
- **Safety Check:** Rollback mechanism if verification fails

## File Structure

**Standard Task Format:**
```markdown
# Task: [Brief Title]

## Commit 1: [type: description [docs/active/tasks/YYYY-MM-DD-[feature-name]-task.md]]
**Description:**
[Details from feature templates in docs/guidelines/ and `docs/active/features/[feature-name]/`]

**Style Compliance (from project_coding_style_analysis.json):**
- **Naming:** Follow `naming_conventions` (functions: snake_case, classes: PascalCase, etc.)
- **Error Handling:** Apply `error_handling.approach` and patterns
- **Testing:** Use `testing_strategy.testing_framework` (e.g., pytest)
- **Patterns:** Follow `architectural_patterns.primary_patterns`

**Template Compliance:**
- Follow guidelines from user-selected templates (docs/templates/corporate/ or startup/)
- Apply feature-specific requirements from docs/guidelines/[feature-name]/

**Verification:**
1. **Automated Test(s):**
   * **Command:** `[testing_framework from JSON]` (e.g., `pytest`)
   * **Expected Outcome:** `[assertions from templates]`
2. **Logging Check:**
   * **Action:** `[trigger action from templates]`
   * **Expected Log:** `[format from JSON: error_handling.logging]`
3. **Safety Check:**
   * **Rollback:** `[git checkout HEAD~1 -- path/to/file]`
   * **User Approval:** `[MANDATORY before commit]`
   * **Push Prohibition:** `[PUSH FORBIDDEN - user must push manually]`

---

## Commit 2: [type: description [docs/active/tasks/YYYY-MM-DD-[feature-name]-task.md]]
[Repeat structure as needed based on templates]
```

## Semantic Commit Types
Use: `feat:`, `fix:`, `test:`, `docs:`, `chore:` with conventional commits format

## After Creation
1. Output ONLY the task plan file content
2. Provide brief executive summary of planned commits
3. **MANDATORY:** Request user approval before proceeding
4. **MANDATORY:** Confirm context approach was correct
4. **EXPLICIT CALL:** "Ready to execute? I'll now call execute.md to run your task plan: [date]-[feature-name]-task.md"
5. **AUTOMATIC:** Call execute.md with the created task plan
6. **SEAMLESS:** Continue with execution workflow

## Commit Execution Protocol (After Plan Creation)

### User Authorization Protocol (CRITICAL)
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

### Commit Phase (With Safety)
- **Stage changes:** `git add` with specific files (MANDATORY before commit request)
- **Show staged files:** Display exactly what will be committed
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

