{A concise but complete description of the persistent bug or issue. Include observed behavior, expected behavior, and any relevant error messages.}

---

## **Mission Briefing: Root Cause Analysis & Remediation Protocol**

Previous, simpler attempts to resolve this issue have failed. Standard procedures are now suspended. You will initiate a **deep diagnostic protocol.**

Your approach must be systematic, evidence-based, and relentlessly focused on identifying and fixing the **absolute root cause.** Patching symptoms is a critical failure.

---

## **Phase 0: Reconnaissance & State Baseline (Read-Only)**

-   **Directive:** Adhering to the **Operational Doctrine**, perform a non-destructive scan of the repository, runtime environment, configurations, and recent logs. Your objective is to establish a high-fidelity, evidence-based baseline of the system's current state as it relates to the anomaly.
-   **Output:** Produce a concise digest (≤ 200 lines) of your findings.
-   **Constraint:** **No mutations are permitted during this phase.**
-   **MANDATORY Dataset Size Assessment Protocol:** 
    - **Step 1:** Calculate exact input dataset size (file count + total file sizes)
    - **Step 2:** Estimate output file size based on input complexity and processing type
    - **Step 3:** Determine if batch processing is needed based on:
      - Input files >100 items OR
      - Total input size >10MB OR  
      - Estimated output >5MB OR
      - Complex processing operations (regex, parsing, analysis)
    - **Step 4:** If batch processing needed, calculate optimal batch sizes based on token limits
    - **Step 5:** Request explicit user confirmation for batch processing before proceeding
    - **Step 6:** Never truncate results when user demands maximum precision
    - **Step 7:** Report batch completion and request continuation ("continua", "vai")
-   **User Requirement Priority Protocol:** When user demands "massima precisione" and "file per file riga per riga", suspend conciseness and prioritize thoroughness. User corrections require complete approach restart from corrected perspective. "più a fondo possibile" means systematic analysis, not approximations. Treat user feedback as absolute requirements, not suggestions. When user requests deeper analysis, conduct comprehensive examination rather than surface-level review.
-   **Code-First Analysis Protocol:** Prioritize actual implementation analysis over documentation assumptions. Base all technical conclusions on actual code examination rather than theoretical analysis. Verify all claims against actual source code implementation.
-   **Error Pattern Systematic Recognition:** Systematically identify duplicate constants and function definitions across similar file types. Prevent recursive function calls that cause infinite loops. Ensure proper namespace usage (e.g., `ta.` prefix for Pine Script functions). Replace unsupported functions with compatible alternatives. Apply systematic fixes to all occurrences of identified error patterns. Verify fixes across all similar files to prevent pattern repetition.
-   **Progress Communication Excellence:** Communicate clear batch progress with exact file counts and completion status. Always request explicit permission ("continua", "vai") before proceeding to next batch. Maintain precise TODO tracking with correct completion percentages. Use clear status markers (✅ completed, ⚠️ corrected, 🚧 in progress) for progress communication. Report exact results (perfect files + corrected files) for each batch.
-   **MCP Server Integration Excellence:** Query ALL available MCP servers for comprehensive knowledge synthesis before implementation. Apply MCP server knowledge to specific domains (Pine Script, trading, clean code). Cross-reference findings across multiple MCP servers for accuracy. Combine insights from different MCP servers for comprehensive solutions. Use MCP-provided templates and best practices as starting points. Leverage MCP servers for Pine Script syntax validation and best practices. Use MCP servers for institutional trading patterns and methodology. Apply MCP server knowledge for code organization and maintainability.
-   **Chat Summary Management:** Maintain complete TODO tracking in chat summaries to avoid information loss. Ensure summary accurately reflects current progress state and completion status. Include critical progress information without losing essential details. Treat user corrections about summary accuracy as critical feedback requiring immediate correction.
-   **CRITICAL VERIFICATION MANDATE:** **NEVER assume file existence without explicit verification. Check each individual file before documenting its presence.**
-   **MCP Server Diagnostic Integration:** Leverage MCP servers to gather technology-specific diagnostic patterns, common issue resolutions, and best practices that can inform your analysis of the anomaly. Use MCP server knowledge to identify potential root causes and diagnostic approaches.
-   **MCP Server Exhaustive Search Protocol:** Query ALL available MCP servers for comprehensive diagnostic coverage. Different servers offer different perspectives (syntax validation, implementation patterns, domain expertise). Combine insights from multiple servers for comprehensive root cause analysis.
-   **MCP Server User Correction Protocol:** When users correct MCP server consultation approach, treat as absolute requirement for immediate verification. Conduct exhaustive verification of all available MCP servers even when initial searches return limited results. User corrections about MCP server usage require complete approach restart from corrected perspective.
-   **Web Search Integration Protocol:** When MCP servers don't provide specific technical solutions, use web search as a fallback to find language/framework-specific built-in functions, advanced features, and diagnostic patterns. This ensures comprehensive knowledge gathering before root cause analysis.
-   **Pine Script Diagnostic Protocol:** Reference `@10 - pinescript-management.md` and `@11 - pinescript-advanced.md` for diagnostic patterns
-   **Notebook Diagnostic Protocol:** Reference `@07 - notebook-management.md`, `@08 - notebook-testing.md`, and `@09 - notebook-analytics.md` for specialized debugging patterns

---

## **Phase 1: Isolate the Anomaly**

-   **Directive:** Your first and most critical goal is to create a **minimal, reproducible test case** that reliably and predictably triggers the bug.
-   **Actions:**
    1.  **Define Correctness:** Clearly state the expected, non-buggy behavior.
    2.  **Create a Failing Test:** If possible, write a new, specific automated test that fails precisely because of this bug. This test will become your signal for success.
    3.  **Pinpoint the Trigger:** Identify the exact conditions, inputs, or sequence of events that causes the failure.
-   **Constraint:** You will not attempt any fixes until you can reliably reproduce the failure on command.

---

## **Phase 2: Root Cause Analysis (RCA)**

-   **Directive:** With a reproducible failure, you will now methodically investigate the failing pathway to find the definitive root cause.
-   **MANDATORY Date Verification Protocol:** Before writing ANY date in documentation, comments, or code, ALWAYS execute a date verification command to establish current date context. This prevents documentation inconsistencies and maintains accuracy across all artifacts.
-   **Document Timestamp Verification Protocol:** When verifying document accuracy claims, ALWAYS check the document's generation/creation timestamp against the current date. Documents older than 6 months require fresh verification before accepting accuracy claims.
-   **Documentation Update Protocol:** When modifying documentation files, ALWAYS update the generation date to maintain traceability of changes. This includes adding an "*Updated: YYYY-MM-DD*" line to track when files were last modified.
-   **Search/Replace Validation Protocol:** Before executing search_replace operations, ALWAYS verify that old_string and new_string are different to prevent identical replacement errors.
-   **Code Verification Protocol:** Always verify current source code before updating documentation to ensure 100% accuracy and faithfulness to the actual implementation.
-   **File Content Verification Protocol:** Always verify actual file contents, line counts, and implementation details using appropriate tools (e.g., line counting commands) before updating documentation. Never trust existing documentation as the source of truth.
-   **Deep Analysis Requirement Protocol:** When users request "deeper" analysis or indicate that initial analysis was insufficient, conduct comprehensive examination of actual implementation files rather than relying on surface-level documentation.
-   **MCP Server RCA Integration:** Use MCP servers to access technology-specific troubleshooting guides, common issue patterns, and diagnostic best practices that can inform your root cause analysis and hypothesis formation. Leverage all available MCP servers for comprehensive diagnostic coverage.
-   **Built-in Function Research Protocol:** Always research language/framework built-in functions before implementing custom solutions. Many issues can be resolved using existing framework capabilities rather than custom logic.
-   **Chart Visibility Detection Protocol:** For Pine Script chart visibility issues, use `chart.left_visible_bar_time` and `chart.right_visible_bar_time` for dynamic range detection instead of fixed bar count approaches.
-   **Pine Script Root Cause Analysis:** For Pine Script issues (.pine files), reference `@10 - pinescript-management.md` for comprehensive diagnostic protocols
-   **Visual Consistency Analysis:** When investigating visual issues, check for systematic inconsistencies across all visual elements. Partial changes to colors, patterns, or markers often create visual inconsistencies that affect user experience.
-   **Interface Organization Analysis:** When analyzing interface issues, verify logical hierarchy and grouping of elements. Poor organization can cause user confusion and workflow inefficiencies.
-   **Naming Convention Analysis:** When investigating naming issues, check for generic or unclear names that cause confusion. Specific, descriptive names improve clarity and usability.
-   **Error Management Analysis:** When investigating errors, check for function return type compliance, variable scope issues, and identifier declaration problems. Implement immediate error correction with systematic validation.
-   **Memory Management Analysis:** When investigating performance issues, check for memory leaks, array size problems, and unused code accumulation. Implement systematic cleanup and resource optimization.
-   **Communication Pattern Analysis:** When investigating communication issues, check for verbose explanations, unclear problem statements, and lack of structured data presentation. Implement radical conciseness and direct problem statement approaches.
-   **No Invention Protocol:** Never implement features, ranges, behaviors, or parameter values not explicitly requested by user. Avoid assumption-making and feature addition without explicit user direction.
-   **Parameter Context Verification Protocol:** When user mentions parameters, always clarify which specific parameter group/context they are referring to before making changes. Verify parameter location and context to prevent incorrect modifications.
-   **Pine Script v6 Function Namespace Analysis:** When investigating Pine Script function errors, check for missing `ta.` prefix in technical analysis functions. Validate function names against Pine Script v6 documentation and ensure proper namespace compliance.
-   **Multi-Modal Filter Analysis:** When investigating filtering issues, check for rigid single-mode implementations, lack of user flexibility, and poor parameter organization. Implement dropdown mode selection and dynamic calculation functions for better user experience.
-   **Pattern Category Recognition Protocol:** When multiple detection methods serve the same functional purpose (e.g., trend detection patterns), implement strict mutual exclusion within the same category. Patterns of the same macro category should not be detected simultaneously or sequentially without actual state change.
-   **Series Logic Implementation Protocol:** Pattern detection systems should prevent redundant marking within the same state until actual state change occurs. Apply series-like logic where no double marking occurs until the underlying condition changes.
-   **Exclusion Flag Architecture Protocol:** Complex exclusion logic requires explicit flags beyond simple conditional chains. Use dedicated exclusion flags to prevent pattern detection conflicts and ensure proper mutual exclusion.
-   **Evidence-Gathering Protocol:**
    1.  **Formulate a Testable Hypothesis:** State a clear, simple theory about the cause (e.g., "Hypothesis: The user authentication token is expiring prematurely.").
    2.  **Devise an Experiment:** Design a safe, non-destructive test or observation to gather evidence that will either prove or disprove your hypothesis.
    3.  **Execute and Conclude:** Run the experiment, present the evidence, and state your conclusion. If the hypothesis is wrong, formulate a new one based on the new evidence and repeat this loop.
-   **Anti-Patterns (Forbidden Actions):**
    -   **FORBIDDEN:** Applying a fix without a confirmed root cause supported by evidence.
    -   **FORBIDDEN:** Re-trying a previously failed fix without new data.
    -   **FORBIDDEN:** Patching a symptom (e.g., adding a `null` check) without understanding *why* the value is becoming `null`.
    -   **FORBIDDEN:** Documenting file existence without explicit verification of each individual file.
    -   **FORBIDDEN:** Applying patterns universally without checking each specific instance.
    -   **FORBIDDEN:** Assuming shared component instances without verification. Use `id()` checks to confirm instance identity.
    -   **FORBIDDEN:** Implementing fallback logic that only handles null parameters. Must handle empty strings, whitespace, and invalid data types.
    -   **FORBIDDEN:** Creating overly broad security patterns that block legitimate operations. Security validation must be precise and tested with legitimate use cases.
    -   **FORBIDDEN:** Providing generic agent instructions that don't guide professional behavior. High-level agents need specific expert protocols.
    -   **FORBIDDEN:** Trusting existing documentation without verifying against actual implementation files. Always use source code as the authoritative source.
    -   **FORBIDDEN:** Conducting superficial analysis when users request deeper investigation. Surface-level examination leads to incomplete corrections.
    -   **FORBIDDEN:** Assuming line counts, file sizes, or implementation details without direct verification using appropriate tools.

---

## **Phase 3: Remediation**

-   **Directive:** Design and implement a minimal, precise fix that durably hardens the system against the confirmed root cause.
-   **MANDATORY Date Verification Protocol:** Before writing ANY date in documentation, comments, or code, ALWAYS execute a date verification command to establish current date context. This prevents documentation inconsistencies and maintains accuracy across all artifacts.
-   **Documentation Update Protocol:** When modifying documentation files, ALWAYS update the generation date to maintain traceability of changes. This includes adding an "*Updated: YYYY-MM-DD*" line to track when files were last modified.
-   **Search/Replace Validation Protocol:** Before executing search_replace operations, ALWAYS verify that old_string and new_string are different to prevent identical replacement errors.
-   **Code Verification Protocol:** Always verify current source code before updating documentation to ensure 100% accuracy and faithfulness to the actual implementation.
-   **MCP Server Remediation Integration:** Leverage MCP servers to access proven fix patterns, best practices for similar issues, and implementation guidelines that can inform your remediation approach and ensure the fix follows industry standards. Utilize all available MCP servers for comprehensive remediation guidance.
-   **Framework-Specific Solution Priority:** Prioritize framework-specific built-in functions over custom implementations. Research language/framework capabilities before implementing custom solutions to avoid reinventing existing functionality.
-   **User Feedback Integration Protocol:** Treat user corrections as absolute requirements and restart analysis from corrected perspective. User feedback often provides critical insights into the actual problem requirements.
-   **Pine Script Remediation Protocol:** For Pine Script fixes (.pine files), reference `@10 - pinescript-management.md` for comprehensive remediation guidelines
-   **Code Cleanup Protocol:** Systematically identify and remove unused code after implementing proper solutions. Maintain clean codebase by removing obsolete inputs, variables, and functions. Ensure code cleanup doesn't break existing functionality. Regularly review and clean up unused code to prevent technical debt.
-   **Label Rendering Logic Protocol:** For visual indicators with multiple pattern types, ensure label rendering uses proper conditional exclusion (`else if`) to prevent dual display. Separate `if` statements can cause multiple labels to appear simultaneously.
-   **Pattern Detection Validation Protocol:** When implementing pattern detection systems, verify that exclusion logic prevents both same-bar and cross-bar pattern conflicts. Use explicit exclusion flags and trend change validation to ensure proper mutual exclusion.
-   **Core Protocols in Effect:**
    -   **Read-Write-Reread:** For every file you modify, you must read it immediately before and after the change.
    -   **Command Execution Canon:** All shell commands must use the mandated safety wrapper.
    -   **System-Wide Ownership:** If the root cause is in a shared component, you are **MANDATED** to analyze and, if necessary, fix all other consumers affected by the same flaw.
    -   **Notebook Work Protocol:** When working with Jupyter notebooks, reference and apply the **Notebook Management Protocol** from `@07 - notebook-management.md` for specialized editing, organization, and content management strategies.

## **Documentation Verification Protocol**

-   **Directive:** When analyzing documentation issues, verify document accuracy against current codebase state
-   **Document Timestamp Verification:** Check document generation/creation timestamp against current date - documents older than 6 months require fresh verification
-   **Documentation Update Protocol:** When modifying documentation files, ALWAYS update the generation date to maintain traceability of changes
-   **Pattern Consistency Check:** Verify documentation follows established patterns and maintains consistency with existing documentation
-   **Accuracy Validation:** Cross-reference documentation claims against actual system implementation
-   **File Content Verification:** Always verify actual file contents, line counts, and implementation details using appropriate tools before updating documentation
-   **Source of Truth Principle:** Actual implementation files are the authoritative source, not existing documentation
-   **Comprehensive Analysis Requirement:** When users request deeper analysis, examine all aspects of implementation including imports, advanced features, error handling, and sophisticated patterns

---

## **Phase 4: Verification & Regression Guard**

-   **Directive:** Prove that your fix has resolved the issue without creating new ones.
-   **Verification Steps:**
    1.  **Confirm the Fix:** Re-run the specific failing test case from Phase 1. It **MUST** now pass.
    2.  **Run Full Quality Gates:** Execute the entire suite of relevant tests (unit, integration, etc.) and linters to ensure no regressions have been introduced elsewhere.
    3.  **Autonomous Correction:** If your fix introduces any new failures, you will autonomously diagnose and resolve them.

---

## **Phase 5: Mandatory Zero-Trust Self-Audit**

-   **Directive:** Your remediation is complete, but your work is **NOT DONE.** You will now conduct a skeptical, zero-trust audit of your own fix.
-   **Audit Protocol:**
    1.  **Re-verify Final State:** With fresh commands, confirm that all modified files are correct and that all relevant services are in a healthy state.
    2.  **Hunt for Regressions:** Explicitly test the primary workflow of the component you fixed to ensure its overall functionality remains intact.

---

## **Phase 6: Final Report & Verdict**

-   **Directive:** Conclude your mission with a structured "After-Action Report."
-   **Report Structure:**
    -   **Root Cause:** A definitive statement of the underlying issue, supported by the key piece of evidence from your RCA.
    -   **Remediation:** A list of all changes applied to fix the issue.
    -   **Verification Evidence:** Proof that the original bug is fixed (e.g., the passing test output) and that no new regressions were introduced (e.g., the output of the full test suite).
    -   **Final Verdict:** Conclude with one of the two following statements, exactly as written:
        -   `"Self-Audit Complete. Root cause has been addressed, and system state is verified. No regressions identified. Mission accomplished."`
        -   `"Self-Audit Complete. CRITICAL ISSUE FOUND during audit. Halting work. [Describe issue and recommend immediate diagnostic steps]."`
-   **Constraint:** Maintain an inline TODO ledger using ✅ / ⚠️ / 🚧 markers throughout the process.