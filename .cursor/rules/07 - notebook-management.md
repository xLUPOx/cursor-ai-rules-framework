# Notebook Management Protocol

## **Core Principles**

- **Notebook Complexity Management:** For Jupyter notebooks with duplicates, recreate clean sections instead of attempting in-place modifications. Notebook structure is complex and content matching is error-prone.
- **Content Matching Precision:** When using edit tools, verify exact content matches before attempting modifications. Failed matches indicate structural complexity requiring alternative approaches.
- **Duplicate Detection Strategy:** Use search tools (grep, pattern matching) to identify all duplicate patterns before attempting cleanup operations. This prevents missing duplicates and ensures comprehensive cleanup.
- **User Intent Parsing:** Simple requests like "fai ordine" (make order) mean direct cleanup and organization, not comprehensive analysis. Lead with action, not explanation.

## **Jupyter Notebook Architecture Protocol**

### JSON Structure & Tool Limitations

- **JSON-Based Structure:** Jupyter notebooks are JSON files with complex nested structure containing cells, metadata, and execution state
- **Cell Metadata Complexity:** Each cell contains execution_count, outputs, metadata, and source arrays that complicate string matching
- **Tool Matching Failures:** edit_notebook tool fails because it matches against display content, not the underlying JSON structure
- **String Matching Complexity:** JSON contains escaped characters, whitespace normalization, and cell-specific formatting that breaks exact matches
- **Fallback Strategy Hierarchy:**
  1. Reduce context window (3 lines before/after)
  2. Target unique cell identifiers (imports, function signatures)
  3. Cell recreation with `is_new_cell: true`
  4. Manual JSON editing (last resort)

### Cell Type Handling

- **Code Cells:** Handle Python code with proper indentation preservation
- **Markdown Cells:** Preserve formatting and link structure
- **Raw Cells:** Maintain exact content without modification
- **Whitespace Preservation:** Maintain original indentation and spacing patterns
- **Failed Match Diagnostic:** When edit_notebook fails, analyze JSON structure vs display content mismatch

## **Context Window & Size Management Protocol**

### Notebook Size Calculation Formula

- **JSON Overhead:** ~2-3x display content size due to metadata and structure
- **Cell Metadata:** ~50-100 characters per cell for execution state and formatting
- **Output Data:** Variable size (can be 10x+ code size for dataframes/plots)
- **Context Window Impact:** File size × 1.5 for token estimation in Cursor IDE
- **Cell Count vs Line Count:** Distinguish between display lines and actual cell count

### Practical Size Tiers

- **Simple Notebooks (≤200 display lines / ≤15KB file):** Safe for all operations
- **Medium Notebooks (200-500 lines / 15-50KB):** Requires sectioned editing
- **Large Notebooks (500-1000 lines / 50-150KB):** Context window risk, mandatory division
- **Critical Notebooks (>1000 lines / >150KB):** Guaranteed failures, immediate division required

### Evidence-Based Thresholds

- Based on actual Cursor IDE behavior and context window limitations
- File size is more reliable indicator than line count due to output data variability
- Context window failures occur predictably at specific file size thresholds

## **Cell Editing Strategy Protocol**

### Primary Approach

- **Extensive Context:** Use 5+ lines before/after for edit_notebook operations
- **Unique Identifiers:** Target distinctive cell content (imports, function signatures, comments)
- **Cell Type Awareness:** Handle code, markdown, and raw cells appropriately

### Fallback Hierarchy

1. **Reduce Context Window:** Use 3 lines before/after for simpler matches
2. **Target Unique Identifiers:** Focus on imports, function signatures, distinctive comments
3. **Cell Recreation:** Use `is_new_cell: true` with complete cell content
4. **Manual JSON Editing:** Last resort for complex structural changes

### Diagnostic Protocol

- **Failed Match Analysis:** Identify JSON structure vs display content differences
- **Whitespace Issues:** Check for indentation and spacing mismatches
- **Character Encoding:** Verify Unicode and special character handling
- **Cell Boundary Detection:** Ensure proper cell identification and targeting

## **Notebook Organization & Division Protocol**

### Single Responsibility Principle

- **Setup/Configuration Notebooks:** Imports, environment variables, utility functions
- **Core Logic Notebooks:** Main functionality, business logic, algorithms
- **Testing Notebooks:** Unit tests, integration tests, validation scripts
- **Analysis Notebooks:** Data exploration, reporting, visualization

### Domain-Based Division Patterns

- **Functional Separation:** Each notebook has one clear, single responsibility
- **Dependency Management:** Clear import paths and shared utility modules
- **Cross-Notebook Coordination:** Systematic approach to shared components
- **Content Transfer Verification:** Use search tools to verify complete content transfer

### Division Strategy

- **Scope Assessment:** Use systematic analysis (grep, pattern matching) to determine content scope
- **Logical Grouping:** Divide by functionality rather than arbitrary size limits
- **Dependency Tracking:** Identify and manage cross-notebook dependencies
- **Import Path Coordination:** Ensure proper module loading and path configuration

## **Jupyter Kernel Lifecycle Protocol**

### Kernel vs Notebook Distinction

- **Kernel State:** Separate from notebook file, persists across sessions
- **Variable Persistence:** Variables remain in memory across cell edits
- **Execution State:** Execution count and output history maintained by kernel
- **Memory Management:** Long-running kernels require periodic cleanup

### State Management Strategies

- **Preserve Kernel State:** When possible, maintain variable state across edits
- **Kernel Restart:** When memory issues or state corruption occurs
- **Clear Output:** Remove output data while preserving kernel state
- **Kernel Interrupt:** Stop execution without losing kernel state

### Memory Management

- **Long-Running Kernels:** Monitor memory usage and restart when necessary
- **Variable Cleanup:** Clear large variables when no longer needed
- **Output Management:** Remove large output data to reduce memory footprint
- **State Verification:** Use `id()` checks to verify kernel state consistency

## **Content Verification & Quality Protocol**

### Pre-Edit Verification

- **Content Analysis:** Use grep and pattern matching to understand scope
- **Duplicate Detection:** Identify all duplicate patterns before cleanup
- **Structure Assessment:** Analyze notebook organization and dependencies
- **Impact Analysis:** Check all dependent files for potential issues

### Post-Edit Verification

- **Reread Verification:** Read modified files immediately after changes
- **Execution Testing:** Test cell execution to verify functionality
- **Content Integrity:** Verify complete content transfer and no data loss
- **Cross-Reference Validation:** Ensure all references and imports work correctly

### Quality Assurance

- **Duplicate Elimination:** Remove redundant content and consolidate functionality
- **Content Consolidation:** One focused report per notebook
- **Systematic Cleanup:** Use search tools to identify and fix all similar patterns
- **Verification Protocol:** Never assume content structure without verification

## **Cross-References**

- **Testing Patterns:** Reference `@08 - notebook-testing.md` for database testing, test organization, cross-platform compatibility, and validation patterns
- **Analytics Workflows:** Reference `@09 - notebook-analytics.md` for agent integration, debugging, data analysis, and error handling patterns

*Updated: 2024-12-19*