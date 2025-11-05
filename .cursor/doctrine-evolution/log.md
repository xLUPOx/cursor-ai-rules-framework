---
description: Doctrine Evolution Log - Lessons learned and proposed integration
alwaysApply: false
---

# Doctrine Evolution Log

**Purpose:** Track lessons learned from sessions before integration into GLOBAL-RULES.mdc

**Process:**
1. Retro command (`/retro` slash command) generates lessons → saves here
2. Review and validate lessons
3. Integrate into GLOBAL-RULES.mdc via `/retro-integrate [lesson-id]` command (semi-automatic) or manual edit

**Location:** `.cursor/doctrine-evolution/log.md` (project-specific) or global doctrine-evolution log

---

## Template: New Lesson Entry

### [DATE]: [Title]

### Lesson Learned
**Issue:** [What went wrong or what pattern was identified]

**Root Cause:** [Why it happened]

### Proposed Integration
**Location:** GLOBAL-RULES.mdc [Section Reference, e.g., "B.7" or "A.3 · CONFIDENCE THRESHOLD PROTOCOL"]

**Change:** [Specific modification proposal - be detailed about what will be added/modified]

**Rationale:** [Why this change improves the doctrine]

**Impact:** [What this prevents/enables]

**Status:** [PENDING REVIEW | APPROVED | INTEGRATED | REJECTED]

---

## Lessons Log

### 2025-11-05: Command Redundancy Analysis

#### Lesson Learned
**Issue:** Commands (`request`, `refresh`, `retro`) duplicate content already in GLOBAL-RULES.mdc when `alwaysApply: true`.

**Root Cause:** Misunderstanding of rule activation mechanism. If GLOBAL-RULES.mdc is always active, workflow commands are redundant unless they add unique value.

#### Proposed Integration
**Location:** GLOBAL-RULES.mdc B.7 - Doctrine Evolution section

**Change:** Clarify that retro command is NOT redundant - it's necessary for:
- Extracting lessons from session
- Proposing doctrine updates
- Maintaining evolution log

**Rationale:** Retro command provides essential workflow for doctrine evolution that cannot be fully automated due to complexity of GLOBAL-RULES.mdc (575+ lines, 51 sections).

**Impact:** Prevents confusion about command utility. Enables proper doctrine evolution workflow.

**Status:** [INTEGRATED]

---

*Last Updated: 2025-11-05*

