---
description: Execute task plans with context-aware approach (startup vs corporate)
globs: []
alwaysApply: false
---

# Execute Task Plan

**Goal:** Execute commits from `docs/active/tasks/` with validation against:
- `docs/guidelines/project_coding_style_analysis.json` (coding style rules)
- and secondary guidelines from `docs/guidelines/

## 🚫 ANTI-OVERKILL PRINCIPLE (CRITICAL)

**GOLDEN RULE:** Match effort to task complexity. Never apply enterprise-level solutions to simple tasks.

**FORBIDDEN OVERKILL:**
- Repository pattern for simple data access
- Dependency injection for basic functions
- Factory patterns for simple object creation
- Comprehensive logging for basic operations
- Extensive test suites for simple functions
- Enterprise patterns for single-file changes

**SIMPLE TASK APPROACH:**
- Direct function calls
- Basic error handling (try/catch)
- Simple logging (print or basic logger)
- Unit tests only (5-8 methods max)
- No unnecessary abstractions

## Phase 0: Reconnaissance (MANDATORY)

### Dual Validation Protocol (MANDATORY - FIRST STEP)
**CRITICAL:** Before ANY execution, ALWAYS read and validate against BOTH sources:

**Source 1: Coding Style Analysis (JSON)**
1. **Read:** `docs/guidelines/project_coding_style_analysis.json`
2. **Extract enforcement rules:**
   - `naming_conventions` → Enforce naming rules (snake_case, PascalCase, etc.)
   - `error_handling.approach` → Match error handling style
   - `testing_strategy.testing_framework` → Use correct test framework
   - `architectural_patterns` → Follow existing patterns
   - `code_organization` → Apply structure patterns
   - `overall_philosophy` → Guide implementation approach

**Source 2: Feature guidelines (Feature-Specific)**
1. **Read:** Secondary guidelines from `docs/guidelines/
2. **Read:** Feature info from `docs/active/features/[feature-name]/`
3. **Extract requirements:**
   - Implementation guidelines
   - Verification steps
   - Testing requirements
   - Logging requirements

**Validation Strategy:**
- **BOTH sources must be satisfied** before commit
- If violation detected in EITHER source → **PROPOSE SOLUTION** to user
- If conflict between sources → **CONSULT USER** for clarification

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
     - **Standards available:** `ls docs/active/features/[feature-name]/` for feature-specific guidelines
   - **If no tasks found:** "No task plans found in docs/active/tasks/. Please create a task plan first."
   - **If no features found:** "No features found in docs/active/features/. Please create a feature first."
   - **If tasks and features exist:** Present available options to user:
     - **Corporate Approach:** "Found [X] task files in docs/active/tasks/ with corporate feature standards"
     - **Startup Approach:** "Found [Y] task files in docs/active/tasks/ with startup feature standards"
     - **User Choice:** "Which approach do you want to use: CORPORATE or STARTUP?"

4. **User Confirmation (if called directly):**
   - **MANDATORY:** "You selected [TASK]. Proceed with execution?"
   - **MANDATORY:** Wait for explicit user confirmation
   - **MANDATORY:** Only proceed after user approval

### Setup & Verification
1. **Check task file exists:** `ls docs/active/tasks/`
2. **If missing:** Stop and notify user immediately
3. **Read task file:** Parse all commits and verification steps
4. **Read coding style:** Load `docs/guidelines/project_coding_style_analysis.json`
5. **Read guidelines:** Load from `docs/guidelines/`
6. **Read feature specifics:** Load from `docs/active/features/[feature-name]/`
7. **System-wide impact analysis:** Identify all affected components and dependencies

### Confidence Assessment Protocol
- If < 95%: Apply systematic clarification process
- Gather comprehensive evidence before proceeding
- Cross-reference findings across multiple sources
- Request user confirmation for uncertain decisions

## Execution Cycle (Per Commit)

### 1. Pre-Execution Safety Check
- **Apply guidelines from:** 
  - `docs/guidelines/project_coding_style_analysis.json` (coding style)
  - `docs/guidelines/` (general guidelines)
  - `docs/active/features/[feature-name]/`  (feaure specific guidelines)
- **Timeout enforcement:** All commands must have timeout
- **Non-interactive execution:** Use flags to prevent interactive prompts
- **Fail-fast semantics:** Scripts should exit immediately on error
- **Cross-platform compatibility:** Consider Windows console limitations

### 2. Implement Phase

**Adaptive Intensity Protocol (MANDATORY - FIRST STEP)**
**CRITICAL:** Match validation intensity to task complexity to prevent over-engineering and overkill.

**ANTI-OVERKILL PRINCIPLE:** Never apply enterprise-level complexity to simple tasks. Match effort to actual requirements.

**Task Complexity Assessment:**
1. **SIMPLE TASK** (toolkit base, enum extension, single file changes):
   - **Validation:** Basic naming conventions + essential error handling
   - **Testing:** Unit tests only (5-8 test methods)
   - **Logging:** Essential logging only (errors + key operations)
   - **Patterns:** Basic patterns only (no enterprise patterns required)
   - **Examples:** AnalyticsToolkit base, AgentType enum, single file fixes
   - **ANTI-OVERKILL:** NO Repository pattern, NO Dependency Injection, NO Factory pattern, NO comprehensive logging

2. **MEDIUM TASK** (multi-file changes, feature additions):
   - **Validation:** Standard validation + error handling
   - **Testing:** Unit + integration tests
   - **Logging:** Structured logging for key operations
   - **Patterns:** Standard architectural patterns
   - **Examples:** Multi-file refactoring, feature additions
   - **ANTI-OVERKILL:** Standard patterns only, NO enterprise-level complexity

3. **COMPLEX TASK** (system-wide changes, new subsystems):
   - **Validation:** Full dual validation protocol
   - **Testing:** Comprehensive testing suite (unit + integration + performance + security)
   - **Logging:** Full structured logging with loguru
   - **Patterns:** All architectural patterns (Repository, Dependency injection, Factory, etc.)
   - **Examples:** New subsystem, architecture changes, system-wide refactoring
   - **ANTI-OVERKILL:** Full enterprise patterns ONLY when truly needed for system-wide changes

**Pre-Implementation Dual Validation (MANDATORY):**

**Validation Source 1: Coding Style (JSON) - ADAPTIVE INTENSITY**
- **SIMPLE TASK:** Basic naming conventions only
  - Functions: snake_case
  - Classes: PascalCase
  - Variables: snake_case
  - Constants: UPPER_SNAKE_CASE
- **MEDIUM TASK:** Standard validation
  - All naming conventions
  - Basic error handling
  - Standard testing framework
- **COMPLEX TASK:** Full validation
  - All naming conventions
  - Full error handling approach
  - Complete testing framework
  - All architectural patterns

**Validation Source 2: Guidelines - ADAPTIVE INTENSITY**
- **SIMPLE TASK:** Essential guidelines only
- **MEDIUM TASK:** Standard guidelines
- **COMPLEX TASK:** Full guidelines compliance

**Implementation:**
- **Execute:** Commit instructions following ADAPTIVE INTENSITY protocol
- **Apply project philosophy:** Match intensity to task complexity
- **Enforce naming:** Apply exact naming conventions from JSON
- **Monitor:** Real-time output and error detection
- **Timeout:** Maximum 5 minutes per command
- **Rollback:** Immediate rollback on failure
- **ANTI-OVERKILL CHECK:** Before implementing, verify complexity matches task requirements

**Violation Handling:**
- If violation of JSON rules detected → **PROPOSE SOLUTION** to user
- If violation of template rules detected → **PROPOSE SOLUTION** to user
- If both satisfied → Proceed with commit

### 3. Verification Phase (MANDATORY) - ADAPTIVE INTENSITY
- **Apply guidelines from:**
  - `docs/guidelines/project_coding_style_analysis.json` (testing framework)
  - `docs/guidelines/` (general verification)
  - `docs/active/features/[feature-name]/` (specific feature verification)
- **Run verification steps** specified in task commit
- **Automated tests:** Execute with ADAPTIVE INTENSITY testing:
  - **SIMPLE TASK:** Unit tests only (5-8 test methods)
  - **MEDIUM TASK:** Unit + integration tests
  - **COMPLEX TASK:** Full testing suite (unit + integration + performance + security)
- **Log inspection:** Verify logging matches ADAPTIVE INTENSITY:
  - **SIMPLE TASK:** Essential logging only (errors + key operations)
  - **MEDIUM TASK:** Structured logging for key operations
  - **COMPLEX TASK:** Full structured logging with loguru
- **Safety checks:** Validate system integrity

### 4. Dual Compliance Validation Protocol (CRITICAL) - ADAPTIVE INTENSITY
**MANDATORY validation before ANY commit against BOTH sources with ADAPTIVE INTENSITY:**

**JSON Validation (project_coding_style_analysis.json) - ADAPTIVE INTENSITY:**
1. **Naming Convention Check (ALL TASKS):**
   - Functions match `naming_conventions.functions` (snake_case)
   - Classes match `naming_conventions.classes` (PascalCase)
   - Variables match `naming_conventions.variables` (snake_case)
   - Constants match `naming_conventions.constants` (UPPER_SNAKE_CASE)

2. **Error Handling Check - ADAPTIVE INTENSITY:**
   - **SIMPLE TASK:** Basic error handling only
   - **MEDIUM TASK:** Standard error handling approach
   - **COMPLEX TASK:** Full error handling approach with all patterns

3. **Testing Check - ADAPTIVE INTENSITY:**
   - **SIMPLE TASK:** Unit tests only (5-8 test methods)
   - **MEDIUM TASK:** Unit + integration tests
   - **COMPLEX TASK:** Full testing suite (unit + integration + performance + security)

4. **Architectural Patterns Check - ADAPTIVE INTENSITY:**
   - **SIMPLE TASK:** Basic patterns only (no enterprise patterns required)
   - **MEDIUM TASK:** Standard architectural patterns
   - **COMPLEX TASK:** All architectural patterns (Repository, Dependency injection, Factory, etc.)

**Guidelines Validation (docs/guidelines/ + `docs/active/features/[feature-name]/`) - ADAPTIVE INTENSITY:**
5. **Implementation Guidelines Check:**
   - **SIMPLE TASK:** Essential guidelines only
   - **MEDIUM TASK:** Standard guidelines
   - **COMPLEX TASK:** Full guidelines compliance

6. **Verification Steps Check:**
   - **SIMPLE TASK:** Essential verification steps only
   - **MEDIUM TASK:** Standard verification steps
   - **COMPLEX TASK:** All template-specified verification steps completed

**Violation Response:**
- If JSON violation → **PROPOSE SOLUTION** with corrected code
- If template violation → **PROPOSE SOLUTION** with template-compliant code
- If both pass → Proceed to User Authorization

### 5. User Authorization Protocol (CRITICAL)
- **MANDATORY user approval** before ANY commit
- **Present commit message with branch specification** for user review
- **Request explicit confirmation:** "Are you sure to commit this to [branch-name]?"
- **NO commit without user approval**

### Pre-Commit Safety Checklist (MANDATORY)
**BEFORE ANY COMMIT, ALWAYS:**
1. **STOP** - Never commit immediately
2. **STAGE** - `git add` specific files (MANDATORY)
3. **SHOW** - Display staged files with `git status`
4. **PRESENT** - Show proposed commit message with branch name
5. **ASK** - "Are you sure to commit this to [branch-name]?"
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
- **User confirmation:** "Are you sure to commit this to [branch-name]?"
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

### Dual Compliance Prevention Protocol
**MANDATORY:** Before any implementation, validate against BOTH sources:

**Source 1: Coding Style Analysis (JSON)**
1. **Read:** `docs/guidelines/project_coding_style_analysis.json`
2. **Apply philosophy:** Follow `overall_philosophy.primary_adjectives`
3. **Verify structure:** Must match `code_organization` patterns
4. **Enforce naming:** Must follow `naming_conventions` exactly
5. **Match error handling:** Must use `error_handling.approach` and patterns
6. **Use correct testing:** Must use `testing_strategy.testing_framework`
7. **Follow patterns:** Must adhere to `architectural_patterns`

**Source 2: Guidelines**
8. **Read specific features guidelines:** From `docs/active/features/[feature-name]/`
9. **Read feature guidelines:** From `docs/active/features/[feature-name]/`
10. **Apply template guidelines:** Follow implementation requirements

**Violation Handling:**
- If JSON violation → **STOP** → **PROPOSE SOLUTION** to user
- If template violation → **STOP** → **PROPOSE SOLUTION** to user
- If both satisfied → Proceed with implementation

### Complexity Metrics Validation
**From guidelines and JSON - NOT hardcoded:**
1. **Check JSON:** Validate against `overall_philosophy.complexity_level`
2. **Check guidelines:** Validate against guidelines-specified metrics
3. **Reject violations:** If exceeds either JSON or template constraints

### Validation Failure Protocol
**When EITHER JSON or template validation fails:**
1. **STOP execution** - Do not proceed with commit
2. **Identify violation source:**
   - JSON violation: Show which rule from `project_coding_style_analysis.json` was violated
   - Template violation: Show which template requirement was not met
3. **PROPOSE SOLUTION** - Provide corrected code that satisfies BOTH sources
4. **Present to user** - Show original vs. proposed solution
5. **Wait for approval** - User must approve or modify solution
6. **Re-validate** - Run dual validation again after fix
7. **Continue only** - After BOTH validations pass

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

## Over-Engineering Prevention Protocol (CRITICAL)

### Anti-Pattern Detection
**MANDATORY:** Before any implementation, assess task complexity and apply appropriate intensity:

**SIMPLE TASK INDICATORS:**
- Single file changes (enum extension, basic toolkit)
- 1-3 methods maximum
- Basic functionality only
- No enterprise patterns required

**MEDIUM TASK INDICATORS:**
- Multi-file changes
- 4-8 methods
- Feature additions
- Standard patterns required

**COMPLEX TASK INDICATORS:**
- System-wide changes
- New subsystems
- 10+ methods
- Full enterprise patterns required

### Over-Engineering Prevention Rules
1. **SIMPLE TASK:** NO enterprise patterns, NO comprehensive logging, NO extensive testing
2. **MEDIUM TASK:** Standard patterns, moderate logging, standard testing
3. **COMPLEX TASK:** Full enterprise patterns, comprehensive logging, extensive testing

### Anti-Overkill Enforcement
**CRITICAL:** Prevent overkill in all phases:

**FORBIDDEN FOR SIMPLE TASKS:**
- Repository pattern
- Dependency injection containers
- Factory patterns
- Comprehensive logging frameworks
- Extensive test suites
- Enterprise architectural patterns
- Complex error handling systems
- Performance monitoring
- Security scanning
- Integration testing

**ALLOWED FOR SIMPLE TASKS:**
- Basic error handling (try/catch)
- Simple logging (print statements or basic logger)
- Unit tests (5-8 methods max)
- Direct function calls
- Simple data structures
- Basic naming conventions

### Violation Detection
**STOP execution if:**
- Simple task with enterprise patterns applied
- Simple task with comprehensive logging
- Simple task with extensive testing suite
- Task complexity assessment incorrect
- Over-engineering detected in any phase

**CORRECTIVE ACTION:**
- Re-assess task complexity
- Apply appropriate intensity level
- Reduce implementation to match complexity
- Remove unnecessary enterprise patterns
- Simplify logging and testing
- Proceed with corrected approach

### Overkill Prevention Checklist
**Before ANY implementation, verify:**
- [ ] Task complexity correctly assessed
- [ ] No enterprise patterns for simple tasks
- [ ] No comprehensive logging for simple tasks
- [ ] No extensive testing for simple tasks
- [ ] Implementation matches actual requirements
- [ ] No unnecessary abstractions
- [ ] No over-architected solutions
