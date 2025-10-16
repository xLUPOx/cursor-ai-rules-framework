# Documentation Architecture

## Overview
This documentation system provides a unified development workflow with dual validation:
- **Coding Style Rules** from `project_coding_style_analysis.json`
- **User-Selected Templates** from `docs/templates/`

## Structure

### Guidelines (`docs/guidelines/`)
- **Purpose**: Coding style rules and general guidelines
- **Coding Style**: `project_coding_style_analysis.json` (MANDATORY for all code)
- **General Guidelines**: General rules and best practices
- **Usage**: Single source of truth for coding standards

### Templates (`docs/templates/`)
- **Purpose**: Reusable implementation templates (user-selectable)
- **Corporate**: Detailed templates with comprehensive requirements
- **Startup**: Quick templates for rapid iteration
- **Selection**: User chooses which templates to apply

### Active Work (`docs/active/`)
- **Purpose**: Current development work
- **Features**: Feature-specific guidelines and requirements (`[feature-name]/`)
- **Tasks**: Generated task plans (`[date]-[feature-name]-task.md`)

## How to Use

### Preparing Feature Guidelines
1. **Create feature directory:** `mkdir docs/active/features/[feature-name]/`
2. **Select base templates:** Choose from `docs/templates/corporate/` or `docs/templates/startup/`
3. **Copy and customize:** Copy selected templates to feature directory
4. **Rename files:** Rename to feature-specific names (e.g., `template-corporate-feature.md` → `feature-requirements.md`)
5. **Add custom requirements:** Feature-specific details, constraints, decisions
6. **Ready for planning:** Feature guidelines are now ready

### Creating Task Plans
1. **Call plan.md:** "Create task plan for [feature-name]"
2. **Prerequisites:**
   - Feature guidelines must exist in `docs/active/features/[feature-name]/`
   - `docs/guidelines/project_coding_style_analysis.json` must be present
3. **Plan generation:** System reads:
   - Coding style from JSON
   - General guidelines from `docs/guidelines/`
   - Feature-specific guidelines from `docs/active/features/[feature-name]/`
4. **Output:** Task plan at `docs/active/tasks/[date]-[feature-name]-task.md`

### Executing Tasks
1. **Call execute.md:** "Execute task [task-name]"
2. **Dual validation:** System validates against:
   - **JSON rules:** Naming conventions, error handling, testing framework
   - **Guidelines rules:** General guidelines + feature-specific requirements
3. **Violation handling:** If validation fails, system proposes solution
4. **Commit:** Only after both validations pass and user approval

## Unified Workflow

### Single Process
No more corporate/startup/balanced contexts. Instead:
- **Coding style** defined by `project_coding_style_analysis.json`
- **General guidelines** from `docs/guidelines/`
- **Feature-specific requirements** from `docs/active/features/[feature-name]/`

### Dual Validation
Every commit validates against:
1. **JSON Validation:** Naming, error handling, testing, patterns
2. **Guidelines Validation:** General guidelines + feature-specific requirements

## File Organization

### Guidelines Structure
```
docs/guidelines/
├── project_coding_style_analysis.json  # MANDATORY coding style rules
└── [general guidelines files]          # General best practices
```

### Templates Structure (User-Selectable)
```
docs/templates/
├── corporate/         # Comprehensive templates
│   ├── template-corporate-feature.md
│   ├── template-corporate-task.md
│   ├── template-corporate-logging.md
│   ├── template-corporate-testing.md
│   ├── template-corporate-tech.md
│   ├── template-corporate-PRD.md
│   └── template-corporate-openapi.yaml
└── startup/          # Quick templates
    ├── template-startup-feature.md
    ├── template-startup-task.md
    ├── template-startup-logging.md
    ├── template-startup-testing.md
    └── template-startup-tech.md
```

### Active Work Structure
```
docs/active/
├── features/
│   └── [feature-name]/                # Feature-specific guidelines (user-prepared)
│       ├── feature-requirements.md
│       ├── feature-logging.md
│       ├── feature-testing.md
│       └── feature-tech.md
└── tasks/                             # Generated task plans
    └── [date]-[feature-name]-task.md
```

## Best Practices

### Documentation Maintenance
1. **Keep JSON updated:** `project_coding_style_analysis.json` is single source of truth
2. **Prepare feature guidelines:** Before planning, prepare in `docs/active/features/[feature-name]/`
3. **Update general guidelines:** Maintain best practices in `docs/guidelines/`
4. **Archive completed work:** Move finished tasks from `docs/active/tasks/`

### Development Workflow
1. **Prepare feature guidelines** in `docs/active/features/[feature-name]/`
2. **Select base templates** from `docs/templates/` (corporate or startup)
3. **Call plan.md** to generate task plan
4. **Call execute.md** to execute with dual validation

### Quality Assurance
- **Dual validation:** All code validates against JSON + guidelines
- **Violation handling:** System proposes solutions, not rejections
- **User approval:** Mandatory for all commits
- **Consistency:** JSON + guidelines ensure uniform coding style across project

---

**Documentation Owner**: System Architect
**Last Updated**: 2025-10-16
**Review Cycle**: Monthly
