# Task Plan Template

**Task ID:** `TASK-YYYY-MM-DD-task-name`
**Feature Source:** `FEAT-YYYY-MM-DD-feature-name`
**Created:** `YYYY-MM-DD`
**Status:** `Draft | Ready | In Progress | Completed`
**Estimated Duration:** `X hours`

## Task Overview

**Description:**
[Brief description of what this task accomplishes]

**Feature Reference:**
[Link to source feature specification]

**Acceptance Criteria:**
- [ ] **AC-001:** [Specific acceptance criterion]
- [ ] **AC-002:** [Another acceptance criterion]

## Reconnaissance Requirements (MANDATORY)

### Pre-Execution Analysis
- [ ] **Repository inventory:** Analyze predominant languages, frameworks, build tools
- [ ] **Dependency topology:** Examine manifest files for dependencies
- [ ] **Quality gates:** Locate linters, type checkers, security scanners, test suites
- [ ] **System-wide impact analysis:** Identify all affected components and dependencies

### Information Gathering (MANDATORY)
**MUST read all relevant files before execution:**
- [ ] `docs/active/features/[feature-name]/` (Source feature specification - CORPORATE context)
- [ ] `docs/templates/corporate/template-corporate-PRD.md` (Product Requirements - CORPORATE context)
- [ ] `docs/templates/corporate/template-corporate-tech.md` (Tech stack - CORPORATE context)
- [ ] `docs/templates/corporate/template-corporate-openapi.yaml` (API specs - CORPORATE context)
- [ ] `docs/templates/corporate/template-corporate-logging.md` (Logging - CORPORATE context)
- [ ] `docs/templates/corporate/template-corporate-testing.md` (Testing - CORPORATE context)
- [ ] `README.md`
- [ ] `.gitignore`, `package.json`, `requirements.txt`, etc.

### Confidence Assessment Protocol
**Before execution, assess confidence level:**
- [ ] **Confidence ≥ 95%:** Proceed with execution
- [ ] **Confidence < 95%:** Apply systematic clarification process
- [ ] **Evidence gathering:** Comprehensive evidence before proceeding
- [ ] **Multi-source validation:** Cross-reference findings across multiple sources
- [ ] **User confirmation:** Request user confirmation for uncertain decisions

### Date Verification Protocol
- [ ] **Current date verified:** `date +"%A, %Y-%m-%d %H:%M:%S UTC"`
- [ ] **Timestamp accuracy:** All dates in task plan verified

## Implementation Commits

### Commit 1: `feat: setup basic structure [docs/tasks/YYYY-MM-DD-task.md]`
**Description:**
[Specific details: file paths (/src/components/NewComponent.tsx), method names (handleUserAction), CLI commands (npm install package-name), imports, dependencies, test files (tests/NewComponent.test.tsx)]

**Verification:**
1. **Automated Test(s):**
   * **Command:** `timeout 30s npm test -- --testPathPattern=NewComponent`
   * **Expected Outcome:** `[specific assertion: expect(component).toBeInTheDocument()]`
   * **Timeout:** 30 seconds maximum
2. **Logging Check:**
   * **Action:** `[trigger component mount and check console output]`
   * **Expected Log:** `[{"Level":"Info","Message":"Component mounted","Component":"NewComponent"}]`
   * **Toggle Mechanism:** `[environment variable: LOG_LEVEL=info]`
3. **Safety Check:**
   * **Rollback:** `[git checkout HEAD~1 -- src/components/NewComponent.tsx]`
   * **User Approval:** `[MANDATORY before commit]`
   * **Push Prohibition:** `[PUSH FORBIDDEN - user must push manually]`

---

### Commit 2: `feat: implement core functionality [docs/tasks/YYYY-MM-DD-task.md]`
**Description:**
[Specific details: file paths (/src/services/UserService.ts), method names (createUser, validateUser), API endpoints (POST /api/users), database operations, error handling, test files (tests/UserService.test.ts)]

**Verification:**
1. **Automated Test(s):**
   * **Command:** `timeout 60s npm test -- --testPathPattern=UserService`
   * **Expected Outcome:** `[specific assertion: expect(response.status).toBe(201)]`
   * **Timeout:** 60 seconds maximum
2. **Logging Check:**
   * **Action:** `[trigger API call with invalid data]`
   * **Expected Log:** `[{"Level":"Error","Message":"Validation failed","Field":"email","Value":"invalid-email"}]`
   * **Toggle Mechanism:** `[appsettings.json: "Logging:LogLevel:Default": "Error"]`
3. **Safety Check:**
   * **Rollback:** `[git checkout HEAD~1 -- src/services/UserService.ts]`
   * **User Approval:** `[MANDATORY before commit]`
   * **Push Prohibition:** `[PUSH FORBIDDEN - user must push manually]`

---

### Commit 3: `test: add comprehensive test coverage [docs/tasks/YYYY-MM-DD-task.md]`
**Description:**
[Specific details: test files (tests/integration/UserWorkflow.test.ts), test utilities (tests/utils/testHelpers.ts), mock data (tests/fixtures/userData.json), test configuration (jest.config.js updates)]

**Verification:**
1. **Automated Test(s):**
   * **Command:** `timeout 120s npm run test:integration`
   * **Expected Outcome:** `[specific assertion: expect(testResults.passed).toBeGreaterThan(0)]`
   * **Timeout:** 120 seconds maximum
2. **Logging Check:**
   * **Action:** `[run tests and check test execution logs]`
   * **Expected Log:** `[{"Level":"Info","Message":"Test suite completed","Passed":5,"Failed":0}]`
   * **Toggle Mechanism:** `[environment variable: TEST_LOG_LEVEL=info]`
3. **Safety Check:**
   * **Rollback:** `[git checkout HEAD~1 -- tests/]`
   * **User Approval:** `[MANDATORY before commit]`
   * **Push Prohibition:** `[PUSH FORBIDDEN - user must push manually]`

---

### Commit 4: `docs: update documentation [docs/tasks/YYYY-MM-DD-task.md]`
**Description:**
[Specific details: file paths (/docs/api/UserAPI.md), README updates, code comments, JSDoc annotations, changelog entries]

**Verification:**
1. **Automated Test(s):**
   * **Command:** `timeout 30s npm run docs:validate`
   * **Expected Outcome:** `[specific assertion: expect(docValidation.errors).toHaveLength(0)]`
   * **Timeout:** 30 seconds maximum
2. **Logging Check:**
   * **Action:** `[generate documentation and check build logs]`
   * **Expected Log:** `[{"Level":"Info","Message":"Documentation generated successfully","Pages":10}]`
   * **Toggle Mechanism:** `[environment variable: DOC_LOG_LEVEL=info]`
3. **Safety Check:**
   * **Rollback:** `[git checkout HEAD~1 -- docs/]`
   * **User Approval:** `[MANDATORY before commit]`
   * **Push Prohibition:** `[PUSH FORBIDDEN - user must push manually]`

---

### Commit 5: `chore: final cleanup and optimization [docs/tasks/YYYY-MM-DD-task.md]`
**Description:**
[Specific details: code cleanup, performance optimizations, dependency updates, final testing, deployment preparation]

**Verification:**
1. **Automated Test(s):**
   * **Command:** `timeout 180s npm run test:full`
   * **Expected Outcome:** `[specific assertion: expect(allTests.passed).toBe(true)]`
   * **Timeout:** 180 seconds maximum
2. **Logging Check:**
   * **Action:** `[run full test suite and check performance logs]`
   * **Expected Log:** `[{"Level":"Info","Message":"All tests passed","Duration":"45s","Coverage":"95%"}]`
   * **Toggle Mechanism:** `[environment variable: FULL_LOG_LEVEL=info]`
3. **Safety Check:**
   * **Rollback:** `[git checkout HEAD~1 -- .]`
   * **User Approval:** `[MANDATORY before commit]`
   * **Push Prohibition:** `[PUSH FORBIDDEN - user must push manually]`

## Pre-Execution Checklist

- [ ] **Feature specification reviewed and approved**
- [ ] **All dependencies identified and available**
- [ ] **Development environment configured**
- [ ] **Test data prepared**
- [ ] **Rollback plan confirmed**

## Post-Execution Checklist

- [ ] **All commits created successfully**
- [ ] **All automated tests passing**
- [ ] **All verification steps completed**
- [ ] **User has approved all commits**
- [ ] **Feature acceptance criteria met**
- [ ] **Documentation updated**
- [ ] **Ready for user manual push**

## Risk Mitigation

### Technical Risks
- **Risk:** Test failures during execution
  - **Mitigation:** Immediate rollback to previous stable state
- **Risk:** Dependency conflicts
  - **Mitigation:** Pre-execution dependency validation

### Process Risks
- **Risk:** User approval delays
  - **Mitigation:** Clear communication of approval requirements
- **Risk:** Push operations attempted
  - **Mitigation:** Explicit push prohibition enforcement

## Success Metrics

- **Completion Rate:** 100% of commits executed successfully
- **Test Coverage:** Maintain or improve existing coverage
- **Performance:** No degradation in system performance
- **Quality:** All acceptance criteria met

---

**Created By:** [Creator name]
**Reviewers:** [List of reviewers]
**Execution Owner:** [Developer responsible for execution]
**Feature Owner:** [Product owner or stakeholder]
