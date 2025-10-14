# Documentation Architecture

## Overview
This documentation system provides context-aware development workflows for both corporate and startup environments.

## Structure

### Guidelines (`docs/guidelines/`)
- **Purpose**: General guidelines and best practices (currently minimal)
- **Corporate**: Enterprise-grade guidelines (example.md placeholder)
- **Startup**: Startup-optimized guidelines (example.md placeholder)
- **Usage**: Reference guidelines for development (to be populated with actual content)

### Templates (`docs/templates/`)
- **Purpose**: Reusable templates for features and tasks
- **Corporate**: Detailed templates with comprehensive requirements
- **Startup**: Quick templates for rapid iteration

### Active Work (`docs/active/`)
- **Purpose**: Current development work
- **Features**: Feature-specific guidelines and requirements
- **Tasks**: Task plans and execution workflows

## How to Use

### Creating a New Feature
1. **Create feature directory:** `mkdir docs/active/features/[feature-name]/`
2. **Copy templates:** Copy relevant files from `docs/templates/[context]/` to feature directory
3. **Rename files:** Rename template files to feature-specific names (e.g., `template-corporate-feature.md` → `feature-requirements.md`)
4. **Customize:** Edit feature-specific files for your needs
5. **Ready for planning:** Call plan.md to create task plan

### Feature-Specific Guidelines
Each feature should have its own guidelines that:
- **Copy from templates:** Start with templates from `docs/templates/[context]/`
- **Customize for feature:** Adapt templates to specific feature requirements
- **Extend general guidelines:** Add feature-specific requirements and constraints
- **Document decisions:** Record architectural decisions and trade-offs

## Workflow Integration

### How Workflow Rules Work
- **plan.md**: Creates task plans for EXISTING features
  - **User calls:** "Crea task plan per [feature-name]"
  - **Prerequisite:** Feature must exist in `docs/active/features/[feature-name]/`
  - **System generates:** Task plan in `docs/active/tasks/[date]-[feature-name]-task.md`
  - **User must create feature first:** Feature directory must exist before calling plan.md

- **execute.md**: Executes task plans with context-aware approach
  - **If called from plan.md:** Seamless execution of generated task plan
  - **If called directly:** User selects from available task plans
  - **System applies:** Feature-specific guidelines from `docs/active/features/[feature-name]/` AND general templates from `docs/templates/`
  - **Integration approach:** Feature-specific guidelines extend and customize general templates for complete coverage

## Context-Aware Approach

### Corporate Context
- **Comprehensive standards**: Full testing, logging, security protocols
- **Detailed documentation**: Complete requirements and specifications
- **Enterprise-grade**: Security, compliance, and scalability focus

### Startup Context
- **Simplified standards**: Essential testing and logging only
- **Quick documentation**: Rapid iteration and MVP focus
- **Agile approach**: Fast delivery and minimal overhead

## File Organization

### Guidelines Structure
```
docs/guidelines/
├── corporate/           # Enterprise guidelines (example.md placeholder)
│   └── example.md
└── startup/            # Startup guidelines (example.md placeholder)
    └── example.md
```

### Templates Structure
```
docs/templates/
├── corporate/         # Corporate templates
│   ├── template-corporate-feature.md
│   ├── template-corporate-task.md
│   ├── template-corporate-logging.md
│   ├── template-corporate-testing.md
│   ├── template-corporate-tech.md
│   ├── template-corporate-PRD.md
│   └── template-corporate-openapi.yaml
└── startup/          # Startup templates
    ├── template-startup-feature.md
    ├── template-startup-task.md
    ├── template-startup-logging.md
    ├── template-startup-testing.md
    └── template-startup-tech.md
```

### Active Work Structure
```
docs/active/
├── features/          # Active feature development (currently empty)
│   └── [feature-name]/ # Feature-specific standards (to be created)
│       ├── feature-logging.md
│       ├── feature-testing.md
│       ├── feature-api.yaml
│       └── feature-tech.md
├── tasks/             # Active task execution
│   └── example.md     # Example task file
└── README.md          # Active development guide
```

## Best Practices

### Documentation Maintenance
1. **Keep guidelines updated** with project evolution
2. **Feature-specific guidelines** should extend, not duplicate
3. **Archive completed work** to maintain active directory clarity
4. **Regular review** of guidelines and templates

### Development Workflow
1. **Start with templates** for new features/tasks
2. **Apply context-appropriate guidelines** (corporate vs startup)
3. **Create feature-specific guidelines** as needed
4. **Use workflow rules** for automated execution

### Quality Assurance
- **Guidelines compliance**: Ensure all work follows established guidelines
- **Context awareness**: Apply appropriate level of detail
- **Documentation consistency**: Maintain uniform structure and format
- **Version control**: Track changes and maintain history

---

**Documentation Owner**: System Architect
**Last Updated**: 2025-10-14
**Review Cycle**: Monthly
