---
description:
globs:
alwaysApply: false
---

# Create Detailed Task Plan

**Core Task:** Generate multi-commit task plan at `docs/features/<YYYY-MM-DD-task-name>.md` with comprehensive testing and logging.

## Setup

1. **Get timestamp:** Run `date +"%Y-%m-%d-%H-%M"` to create filename
2. **Check files:** Run `ls . docs` to verify project structure

## Information Gathering (MANDATORY)

**MUST read all relevant `docs/` files before planning:**
- `docs/PRD.md` (Product Requirements)
- `docs/tech_stack.md`
- `docs/openapi.yaml` (API specs)
- `docs/logging.md`
- `docs/testing_strategy.md`
- `README.md`

## Output Rules

- **ONLY output:** Complete Markdown content for the task plan file
- **NO conversation:** No preamble, commentary, or summaries
- **Missing info:** Use `<!-- TODO: [specify what's missing] -->` in file

## Required for Each Commit

### Testing (Priority Order)
1. **Unit tests** (preferred) - isolated, fast
2. **Integration tests** - component interactions, API contracts
3. **Log inspection** (fallback only if automated testing impossible)

### Logging (Always Required)
- Toggleable via environment variable/feature flag
- Structured output (JSON/key-value pairs)
- Use project's logging library
- Direct to standard log aggregation

### Verification Format
For each commit specify:
- **Test Command:** Exact command (e.g., `dotnet test`)
- **Expected Outcome:** Key assertions/behavior
- **Log Check:** How to trigger/observe logs and expected message

## File Structure

```markdown
# Task: [Brief Title]

## Commit 1: [type: description [docs/tasks/YYYY-MM-DD-task.md]]
**Description:**
[Specific details: file paths (/Controllers/UserController.cs), method names (HandleUserLoginAsync), CLI commands (dotnet ef migrations add), usings, NuGet packages, test files (tests/UserControllerTests.cs)]

**Verification:**
1. **Automated Test(s):**
   * **Command:** `dotnet test --filter UserControllerTests`
   * **Expected Outcome:** `[specific assertion: Assert.Equal(200, response.StatusCode)]`
2. **Logging Check:**
   * **Action:** `[trigger via API call with invalid credentials]`
   * **Expected Log:** `[{"Level":"Information","Message":"Reservation failed","UserId":"test@example.com"}]`
   * **Toggle Mechanism:** `[appsettings.json: "Logging:LogLevel:Default": "Information"]`

---

## Commit 2: [type: description [docs/tasks/YYYY-MM-DD-task.md]]
[Repeat structure for 2-10 commits total]
```

## Semantic Commit Types
Use: `feat:`, `fix:`, `test:`, `docs:`, `chore:`

## After Creation
1. Output ONLY the task plan file content
2. Provide brief executive summary of planned commits
3. Wait for user feedback
