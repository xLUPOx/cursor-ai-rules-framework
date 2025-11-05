# Cursor AI Rules Framework

A comprehensive, evidence-first prompting framework designed to elevate AI agents from simple command executors to **Autonomous Principal Engineers**.

## 🎯 Philosophy

**Autonomy through discipline. Trust through verification.**

This framework enforces a rigorous workflow of reconnaissance, planning, safe execution, and self-improvement, ensuring every action is deliberate, verifiable, and aligned with senior engineering best practices.

## 📁 Framework Overview

### Core Components
- **GLOBAL-RULES.mdc** - Main operational doctrine and protocols
- **commands/** - Workflow commands for doctrine evolution (`retro`, `retro-integrate`) - Location: `.cursor/commands/`
- **doctrine-evolution/** - Doctrine evolution log and lessons tracking - Location: `.cursor/doctrine-evolution/`
- **workflow/** - Planning and execution rules for development tasks
- **docs/** - Context-aware documentation system (corporate vs startup)
- **estensions/** - Specialized rules for specific domains

### Documentation System
- **Guidelines** - Template base for creating feature-specific guidelines (corporate/startup contexts)
- **Templates** - Reusable starting points for features and tasks
- **Active Work** - Current development with feature-specific guidelines that extend and integrate with general guidelines
- **Workflow Integration** - Automated execution with safety protocols using integrated guidelines approach

## 🚀 Quick Start

### 1. Install the Core Doctrine

**For Global Use (Recommended):**
- Install `GLOBAL-RULES.mdc` as a global rule in your Cursor IDE
- This ensures all your projects benefit from this disciplined foundation

**For Project-Specific Use:**
- Place the content in a project-specific `.cursor/rules/` directory
- This will override global settings for specific projects

### 2. Use the Workflow Commands (Recommended)

**Activate workflows using command references in chat:**

| Command | Purpose | How to Use |
|---------|---------|------------|
| **`/retro`** | Self-Improvement Loop | Type `/retro` in chat at end of session |
| **`/retro-integrate`** | Integrate Lessons into Doctrine | Type `/retro-integrate [lesson-id]` in chat after reviewing `.cursor/doctrine-evolution/log.md` |

**Example Usage:**
```
/retro
```

**Note:** GLOBAL-RULES.mdc contains all operational protocols (Phase 0-5 workflows). No separate `request` or `refresh` commands needed when `alwaysApply: true`. Use `/retro` only for doctrine evolution at end of sessions.

### 2b. Legacy Playbooks (Alternative)

**Legacy templates available in `OLD/` directory - copy and paste into chat:**

| Playbook | Purpose | How to Use |
|----------|---------|------------|
| **`OLD/02 - request.md`** | Standard Operating Procedure | Copy full content, replace placeholder with your goal, paste in chat |
| **`OLD/03 - refresh.md`** | Root Cause Analysis | Use when bugs persist and simpler attempts failed |
| **`OLD/04 - retro.md`** | Self-Improvement Loop | Use at end of session to capture learnings and improve the framework |

**Note:** Command `/retro` enables doctrine evolution workflow. GLOBAL-RULES.mdc contains all operational protocols (no need for separate request/refresh commands when `alwaysApply: true`).

### 3. Apply Optional Directives

**These are user rules - install in Cursor settings or append to playbooks:**

| Directive | Type | Function | How to Use |
|-----------|------|----------|------------|
| **`05 - concise.md`** | User Rule | Radically concise communication | Install as global rule or append to playbooks |
| **`06 - no-absolute-right.md`** | User Rule | Professional communication guidelines | Install as global rule to avoid sycophantic language |

## 📁 Framework Components

### Core Files

- **`GLOBAL-RULES.mdc`** - Main framework documentation and operational doctrine
- **`commands/retro.md`** - Retrospective and doctrine evolution command (location: `.cursor/commands/retro.md`)
- **`commands/retro-integrate.md`** - Semi-automatic doctrine integration protocol (location: `.cursor/commands/retro-integrate.md`)
- **`workflow/plan.md`** - Planning phase protocols
- **`workflow/execute.md`** - Execution phase protocols

### Specialized Extensions

**These are user rules - install in Cursor settings for specific domains:**

| Extension File | Type | Function | When to Use |
|----------------|------|----------|-------------|
| **`07 - notebook-management.md`** | User Rule | Jupyter notebook protocols | When working with Jupyter notebooks |
| **`08 - notebook-testing.md`** | User Rule | Notebook testing patterns | For notebook testing workflows |
| **`09 - notebook-analytics.md`** | User Rule | Analytics workflows | For data analysis projects |
| **`10 - pinescript-management.md`** | User Rule | Pine Script development | When developing TradingView indicators |
| **`11 - pinescript-advanced.md`** | User Rule | Advanced Pine Script patterns | For complex Pine Script implementations |

### Legacy Files

**Historical versions available in `OLD/` directory:**
- **`00 - Cursor AI Prompting Rules.md`** - Original framework documentation
- **`01 - core.md`** - Legacy core operational doctrine
- **`02 - request.md`** - Legacy standard operating procedure template
- **`03 - refresh.md`** - Legacy root cause analysis template
- **`04 - retro.md`** - Legacy self-improvement loop template
- **`05 - concise.md`** - Legacy concise communication rules
- **`06 - no-absolute-right.md`** - Legacy professional communication guidelines
- **`commits.mdc`** - Commit message guidelines

## 🔧 How to Use

### Installation Types

**1. Core Doctrine (Required):**
- Install `GLOBAL-RULES.mdc` as a global rule in Cursor
- This provides the foundational operational principles and all protocols

**2. Workflow Extensions (Optional):**
- `workflow/plan.md` - Enhanced planning phase protocols with integrated standards approach
- `workflow/execute.md` - Enhanced execution phase protocols with integrated standards approach

**3. Specialized Extensions (Install in Cursor Settings):**
- `07-11` - Domain-specific rules (notebooks, Pine Script, etc.)
- Install based on your development needs

**4. Legacy Playbooks (Historical):**
- Available in `OLD/` directory for reference
- `02 - request.md` - Legacy standard development tasks
- `03 - refresh.md` - Legacy debugging persistent issues  
- `04 - retro.md` - Legacy session reflection and improvement

### Typical Session Workflow

1. **Install Core Framework:**
   - Install `GLOBAL-RULES.mdc` as a global rule in Cursor
   - Optionally install specialized extensions from `estensions/` directory
   - Framework automatically activates all protocols

2. **Observe Disciplined Execution:**
   - Agent announces operational phase (Reconnaissance, Planning, etc.)
   - Performs non-destructive research first
   - Executes plan with verifiable evidence
   - Runs tests autonomously
   - Concludes with mandatory self-audit

3. **Review Final Report:**
   - Agent provides summary with status markers
   - All evidence transparently available in chat log
   - Workspace left clean

4. **Continuous Improvement:**
   - Framework includes built-in self-improvement protocols via `/retro` command
   - **Doctrine Evolution Process:**
     1. Type `/retro` in chat at end of session → AI analyzes and extracts lessons
     2. Lessons saved to `.cursor/doctrine-evolution/log.md` with status `[PENDING REVIEW]`
     3. Review lessons in log.md
     4. Integrate via `/retro-integrate [lesson-id]` command (semi-automatic) or manual edit
     5. AI proposes exact diff → User approves → Integration applied
   - **Why Semi-Automatic?** GLOBAL-RULES.mdc is complex (575+ lines, 51 sections). Manual review prevents style inconsistencies, logical conflicts, and unintended side effects.

## 🎯 Status Markers

The framework uses clear status indicators:

- `✅` - Objective completed successfully
- `⚠️` - Recoverable issue encountered and fixed autonomously  
- `🚧` - Blocked; awaiting input or resource

## 🧠 Core Principles

1. **Research-First, Always** - Never act on assumption
2. **Extreme Ownership** - Own end-to-end system health
3. **Autonomous Problem-Solving** - Self-sufficient operation
4. **Unyielding Precision & Safety** - Respect operational environment
5. **Metacognitive Self-Improvement** - Continuous learning and evolution

## 🔗 MCP Server Integration

The framework includes protocols for leveraging Model Context Protocol (MCP) servers:

- **Automatic Detection** - MCP servers globally configured
- **Context-Aware Selection** - Based on technology stack and requirements
- **Knowledge Synthesis** - Combine insights from multiple sources
- **Template Application** - Use MCP-provided best practices

## 📋 Cursor Plan Mode Compatibility

**Plan Mode (Shift+Tab) is fully compatible:**
- Generated plans follow Phase 0-5 structure
- Enhanced communication with structured overviews
- All operational protocols remain unchanged
- MCP server integration preserved

## 🤝 Contributing

This framework is designed for community use and improvement. Contributions are welcome for:

- New specialized rule files
- Framework enhancements
- Documentation improvements
- Bug fixes and optimizations

## 🙏 Credits & Attribution

This framework is inspired by and adapted from the original work of [aashari](https://gist.github.com/aashari/07cc9c1b6c0debbeb4f4d94a3a81339e). We thank the author for sharing their valuable insights and structures, which provided a solid foundation for developing this enhanced framework.

**Key modifications and enhancements:**
- Expanded operational doctrine with additional protocols
- Added specialized rules for notebooks, Pine Script, and analytics
- Integrated MCP server support protocols
- Enhanced communication guidelines and conciseness directives
- Added comprehensive documentation and usage examples
- **Integrated guidelines approach** - Feature-specific guidelines extend and integrate with general guidelines for complete coverage

## 📄 License

This framework is provided as-is for educational and professional use. Please respect the operational principles and maintain the disciplined approach that makes this framework effective.

---

**Welcome to a more disciplined, reliable, and truly autonomous way of working with AI.**

*Updated: 2025-11-05*
