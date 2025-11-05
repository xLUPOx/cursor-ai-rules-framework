---
description: Doctrine Integration Protocol - Semi-automatic GLOBAL-RULES.mdc updates
alwaysApply: false
---

# Doctrine Integration Protocol

**CRITICAL:** Auto-modification of GLOBAL-RULES.mdc (575+ lines, 51 sections) is **RISKY**. This protocol provides **semi-automatic** integration with safety checks.

**Usage:** Use slash command `/retro-integrate [lesson-id]` in chat after reviewing `.cursor/doctrine-evolution/log.md` to integrate lessons into GLOBAL-RULES.mdc.

---

## **Phase 0: Pre-Integration Validation**

### **Mandatory Checks:**
1. **Read Evolution Log:** Review `.cursor/doctrine-evolution/log.md` (project-specific) or global doctrine-evolution log for pending lessons
2. **Validate Lesson Quality:** Ensure lesson meets criteria:
   - ✅ Universal & Reusable
   - ✅ Abstracted (not session-specific)
   - ✅ High-Impact
   - ✅ Non-conflicting with existing rules
3. **Locate Integration Point:** Identify exact section in GLOBAL-RULES.mdc using structural analysis:
   - Use section numbering (A.B.C format)
   - Match existing style patterns
   - Verify no duplicate content exists

---

## **Phase 1: Structural Analysis**

### **GLOBAL-RULES.mdc Structure:**
- **4 Main Sections:** PHASE 0, OPERATIONAL FOUNDATION, COMMUNICATION PROTOCOL, AUTHORIZATION & SAFETY, SYSTEM GOVERNANCE
- **51 Sub-sections:** Hierarchical organization (A.B.C format)
- **Style Requirements:**
  - Formal tone ("CRITICAL:", "MANDATORY:", "FORBIDDEN:")
  - Bullet points with bold labels
  - Cross-references using section notation
  - No dates/timestamps in doctrine content

### **Integration Constraints:**
- **Preserve Structure:** Maintain hierarchical numbering
- **Match Style:** Use exact formatting patterns from existing sections
- **Maintain Coherence:** Ensure new content doesn't contradict existing rules
- **Cross-Reference:** Update related sections if needed

---

## **Phase 2: Draft Integration**

### **Process:**
1. **Create Backup:** Copy GLOBAL-RULES.mdc to `.backup/` before modification
2. **Generate Diff:** Show exact changes before applying
3. **Preserve Context:** Include 5+ lines before/after insertion point
4. **Match Formatting:** Use identical formatting as surrounding content
5. **Validate Structure:** Verify section numbering remains correct

### **Integration Types:**

**Type A: Add New Protocol**
- Find appropriate section (e.g., "B.6 · ADVANCED PROTOCOLS INTEGRATION")
- Add after existing protocols
- Use identical formatting

**Type B: Enhance Existing Protocol**
- Locate exact protocol
- Enhance with new insight (don't duplicate)
- Maintain original structure

**Type C: Fix Inconsistency**
- Identify conflicting rules
- Resolve conflict (user approval required)
- Update all affected sections

---

## **Phase 3: Validation & Safety Checks**

### **TWO-STEP VALIDATION PROCESS**

**CRITICAL:** Validation happens in TWO phases:
1. **AI Automatic Pre-Check** - AI validates against checklist autonomously
2. **Collaborative Review** - AI guides user through checklist together

---

### **STEP 1: AI AUTOMATIC PRE-CHECK**

**Before showing proposal to user, AI MUST:**

1. **Read GLOBAL-RULES.mdc completely** - Understand full context
2. **Read evolution log entry** - Understand proposed change
3. **Validate against ALL checklist items (A1-F3)** - Check each question internally
4. **Generate Validation Report** - Show which items pass/fail
5. **Modify proposal** - Fix obvious issues before user review
6. **Highlight concerns** - Flag items that need user attention

**AI Pre-Check Output Format:**
```
AI PRE-CHECK RESULTS:
✅ A1: Universal Applicability - PASS
✅ A2: Abstraction Level - PASS
⚠️ A3: Impact Assessment - NEEDS USER REVIEW (low impact risk)
✅ B1: Conflict Detection - PASS
✅ B2: Completeness - PASS
...
✅ F3: Final Sanity Check - PASS

SUMMARY: 51/54 items pass. 3 items need user review.
```

---

### **STEP 2: COLLABORATIVE REVIEW WITH USER**

**After AI pre-check, AI guides user through checklist:**

#### **A. Content Quality & Universal Applicability**

**AI Action:** Present each question, show AI's assessment, ask for user confirmation.

**A1. Universal Applicability:**
- **AI:** "✅ AI Check: This lesson appears universal. Question: Is this lesson truly universal and reusable across different projects, or is it specific to this session?"
- **User:** Confirms or flags concern
- **AI:** If user flags concern, AI modifies proposal and re-checks

**A2. Abstraction Level:**
- **AI:** "✅ AI Check: Abstraction level appropriate. Question: Is the lesson abstracted enough? (e.g., 'Always verify environment variables' not 'Check JWT_SECRET_KEY in .env')"
- **User:** Confirms or requests modification
- **AI:** Adjusts if needed

**A3. Impact Assessment:**
- **AI:** "⚠️ AI Check: Impact may be medium. Question: Does this prevent a critical failure or enforce crucial safety?"
- **User:** Evaluates and decides
- **AI:** Proceeds based on user decision

**[Continue for ALL 54 questions with same pattern]**

---

### **COLLABORATIVE WORKFLOW SEQUENCE**

**Before Approval, Execute Sequentially:**

1. **AI Performs Automatic Pre-Check:**
   - Reads GLOBAL-RULES.mdc and evolution log
   - Validates against ALL 54 checklist items internally
   - Generates pre-check report showing pass/fail/warning for each item
   - Modifies proposal to fix obvious issues
   - Highlights items requiring user attention

2. **AI Presents Proposal with Pre-Check Results:**
   ```
   PROPOSED CHANGE:
   Location: GLOBAL-RULES.mdc B.7
   Type: Enhancement
   Diff: [show exact diff]
   Rationale: [why this improves doctrine]
   
   AI PRE-CHECK SUMMARY:
   ✅ 51 items passed automatically
   ⚠️ 3 items need your review: [list]
   🔍 Ready for collaborative review
   ```

3. **AI Guides User Through Collaborative Review:**
   - **For each checklist item:**
     - AI shows: "✅ AI Check: [assessment]"
     - AI asks: "Question: [the question]"
     - User responds: Confirms, flags concern, or requests modification
     - AI adjusts: If user flags concern, AI modifies and re-checks
   - **AI tracks progress:** Shows which items are complete
   - **AI highlights concerns:** Focuses extra attention on items user flagged

4. **AI Addresses User Concerns:**
   - Modifies proposal based on user feedback during review
   - Re-validates modified proposal against checklist
   - Shows updated diff with changes highlighted
   - Asks for confirmation on modifications

5. **User Approves After Collaborative Review:**
   - Only after ALL 54 checklist items reviewed together
   - User has seen AI's assessment AND provided own input
   - Explicit approval: "approve" or "integrate"
   - Can request additional modifications before approval

6. **Post-Integration Verification:**
   - Re-read modified section
   - Verify formatting correctness
   - Check for unintended side effects
   - Confirm evolution log updated

---

### **MANDATORY USER VALIDATION CHECKLIST**

**CRITICAL:** During collaborative review, AI and user verify ALL questions below together.

#### **A. Content Quality & Universal Applicability**

**A1. Universal Applicability:**
- [ ] **Question:** Is this lesson truly universal and reusable across different projects, or is it specific to this session?
- [ ] **Question:** Would this rule apply to Python, JavaScript, Pine Script, and other languages equally?
- [ ] **Question:** Is this principle timeless, or will it become obsolete with technology changes?

**A2. Abstraction Level:**
- [ ] **Question:** Is the lesson abstracted enough? (e.g., "Always verify environment variables" not "Check JWT_SECRET_KEY in .env")
- [ ] **Question:** Are there any session-specific details that should be removed?
- [ ] **Question:** Is the language tool-agnostic and framework-agnostic?

**A3. Impact Assessment:**
- [ ] **Question:** Does this prevent a critical failure or enforce crucial safety?
- [ ] **Question:** Will this significantly improve efficiency or quality?
- [ ] **Question:** Is this high-impact enough to justify adding to GLOBAL-RULES.mdc?

#### **B. Logical Coherence & Consistency**

**B1. Conflict Detection:**
- [ ] **Question:** Does this new rule contradict any existing rule in GLOBAL-RULES.mdc?
- [ ] **Question:** Are there similar rules elsewhere that should be merged instead of duplicated?
- [ ] **Question:** Does this create logical inconsistencies with related protocols?

**B2. Completeness:**
- [ ] **Question:** If this rule requires exceptions or special cases, are they all covered?
- [ ] **Question:** Are there edge cases where this rule might fail or be inappropriate?
- [ ] **Question:** Does this rule need to reference or be referenced by other sections?

**B3. System-Wide Impact:**
- [ ] **Question:** Will this change affect how other protocols work?
- [ ] **Question:** Should other sections be updated to maintain consistency?
- [ ] **Question:** Are there cross-references that need updating?

#### **C. Structural Integrity & Organization**

**C1. Location Accuracy:**
- [ ] **Question:** Is this the BEST location for this rule, or would another section be more appropriate?
- [ ] **Question:** Does the section hierarchy (A.B.C format) make sense?
- [ ] **Question:** Should this be a new section, subsection, or enhancement to existing?

**C2. Structural Consistency:**
- [ ] **Question:** Does the numbering follow the existing pattern correctly?
- [ ] **Question:** Are the heading levels (##, ###, ####) consistent with surrounding content?
- [ ] **Question:** Does this maintain the document's structural flow?

**C3. Formatting & Style Match:**
- [ ] **Question:** Does the formatting match EXACTLY the surrounding sections? (bullet style, bold usage, spacing)
- [ ] **Question:** Is the tone consistent? (formal, military-style, "CRITICAL:", "MANDATORY:", "FORBIDDEN:")
- [ ] **Question:** Are there any formatting inconsistencies (spaces, indentation, markdown syntax)?

#### **D. Language & Expression Quality**

**D1. Clarity & Precision:**
- [ ] **Question:** Is the language clear and unambiguous?
- [ ] **Question:** Could this be misinterpreted or have multiple interpretations?
- [ ] **Question:** Are technical terms used correctly and consistently?

**D2. Conciseness:**
- [ ] **Question:** Is this concise enough? (matches RADICAL COMMUNICATION CONCISENESS protocol)
- [ ] **Question:** Are there unnecessary words that can be removed?
- [ ] **Question:** Does this respect the "Maximum Signal, Minimum Noise" principle?

**D3. Tone Consistency:**
- [ ] **Question:** Does the tone match the authoritative, formal style of GLOBAL-RULES.mdc?
- [ ] **Question:** Are the imperatives ("MUST", "SHALL", "FORBIDDEN") used correctly?
- [ ] **Question:** Is the language directive and prescriptive, not descriptive?

#### **E. Integration Mechanics**

**E1. Diff Quality:**
- [ ] **Question:** Does the diff show sufficient context (5+ lines before/after)?
- [ ] **Question:** Is the diff clear and easy to understand?
- [ ] **Question:** Are there any unintended changes in the diff?

**E2. Backup & Safety:**
- [ ] **Question:** Has a backup been created before modification?
- [ ] **Question:** Can this change be easily reverted if needed?
- [ ] **Question:** Is this a single, atomic change, or should it be split?

**E3. Cross-Reference Integrity:**
- [ ] **Question:** Are all section references (like "see B.4") still valid after this change?
- [ ] **Question:** Should this rule reference other sections?
- [ ] **Question:** Do other sections need to reference this new rule?

#### **F. Meta-Validation (Final Checks)**

**F1. Evolution Log Accuracy:**
- [ ] **Question:** Does the evolution log entry accurately describe what will be integrated?
- [ ] **Question:** Is the rationale clear and convincing?
- [ ] **Question:** Will future readers understand why this change was made?

**F2. Documentation Completeness:**
- [ ] **Question:** If this rule needs examples, are they included?
- [ ] **Question:** Are edge cases or exceptions documented?
- [ ] **Question:** Is the integration complete, or are there follow-up changes needed?

**F3. Final Sanity Check:**
- [ ] **Question:** After reading the entire modified section, does it make sense as a whole?
- [ ] **Question:** Would a new reader understand this rule without context?
- [ ] **Question:** Is this the RIGHT change, or should it be approached differently?

---

### **VALIDATION WORKFLOW**

**Before Approval, Execute Sequentially:**

1. **AI Proposes Integration:**
   - Shows exact diff with context
   - Explains location and rationale
   - Highlights potential concerns

2. **User Reviews Checklist:**
   - Goes through ALL questions (A1-F3)
   - Flags any concerns or "NO" answers
   - Requests clarification or modification if needed

3. **AI Addresses Concerns:**
   - Modifies proposal based on feedback
   - Re-validates against checklist
   - Shows updated diff

4. **User Approves:**
   - Only after ALL checklist items verified
   - Explicit approval: "approve" or "integrate"
   - Can request modifications before approval

5. **Post-Integration Verification:**
   - Re-read modified section
   - Verify formatting correctness
   - Check for unintended side effects
   - Confirm evolution log updated

### **Safety Mechanisms:**
- **Diff Preview:** Always show diff before applying
- **User Approval:** Require explicit approval for modifications
- **Rollback Capability:** Keep backup for easy reversion
- **Incremental Updates:** One lesson at a time, not batch updates
- **Checklist Enforcement:** Integration blocked until checklist complete

---

## **Phase 4: Integration Execution**

### **Execution Protocol:**
1. **Present Proposal:**
   ```
   PROPOSED CHANGE:
   Location: GLOBAL-RULES.mdc B.7
   Type: Enhancement
   Diff: [show exact diff]
   Rationale: [why this improves doctrine]
   ```

2. **Await Approval:** User must explicitly approve with "approve" or "integrate"

3. **Execute Integration:**
   - Apply diff to GLOBAL-RULES.mdc
   - Update evolution log status to "INTEGRATED"
   - Commit change with descriptive message

4. **Post-Integration Verification:**
   - Re-read modified section
   - Verify formatting correctness
   - Check for unintended side effects

---

## **Phase 5: Evolution Log Update**

### **Update Log Entry:**
- Change status from "PENDING REVIEW" to "INTEGRATED"
- Add integration timestamp
- Reference commit hash if applicable
- Note any deviations from original proposal

---

## **Limitations & Risks**

### **What AI CAN Do:**
- ✅ Propose modifications with exact diff
- ✅ Match formatting and style
- ✅ Locate appropriate integration points
- ✅ Detect obvious conflicts

### **What AI CANNOT Guarantee:**
- ❌ 100% logical coherence across all 575 lines
- ❌ No unintended side effects
- ❌ Perfect style matching (human review recommended)
- ❌ Complete understanding of all rule interactions

### **Mitigation Strategy:**
- **Semi-Automatic:** AI proposes, human approves
- **Incremental:** One lesson at a time
- **Reversible:** Always keep backups
- **Validated:** Post-integration verification mandatory

---

## **Alternative: Fully Manual Integration**

If auto-integration is too risky:
1. AI generates lesson in evolution log
2. AI proposes exact diff
3. **Human manually applies** diff to GLOBAL-RULES.mdc
4. AI verifies integration correctness

---

*Protocol: Doctrine Integration*
*Command: Doctrine Integration Protocol*
*Activate with: /retro-integrate [lesson-id]*
