# Documentation Architecture

## Overview
This documentation system provides context-aware development workflows for both corporate and startup environments.

## Structure

### Standards (`docs/standards/`)
- **Purpose**: General standards and best practices
- **Corporate**: Comprehensive standards for enterprise development
- **Startup**: Simplified standards for rapid development

### Templates (`docs/templates/`)
- **Purpose**: Reusable templates for features and tasks
- **Corporate**: Detailed templates with comprehensive requirements
- **Startup**: Quick templates for rapid iteration

### Active Work (`docs/active/`)
- **Purpose**: Current development work
- **Features**: Feature-specific standards and requirements
- **Tasks**: Task plans and execution workflows

## How to Use

### Creating a New Feature
1. Copy template from `docs/templates/features/[context]/`
2. Create feature directory in `docs/active/features/[feature-name]/`
3. Copy and customize standards from `docs/standards/[context]/` to `docs/active/features/[feature-name]/`
4. Update during development

### Feature-Specific Standards
Each feature should have its own standards that:
- Extend general standards from `docs/standards/`
- Override general standards where needed
- Include feature-specific requirements
- Document architectural decisions

## Workflow Integration
- **plan.md**: Creates task plans from templates and executes commits
- **execute.md**: Executes existing task plans from `docs/active/tasks/`
- Both rules apply feature-specific standards from `docs/active/features/[feature-name]/`
- Fallback to general standards from `docs/standards/` if feature-specific not available

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

### Standards Structure
```
docs/standards/
├── corporate/           # Enterprise standards
│   ├── logging.md       # Comprehensive logging strategy
│   ├── testing_strategy.md # Full testing protocols
│   ├── tech_stack.md    # Complete technology stack
│   ├── PRD.md          # Product requirements
│   └── openapi.yaml    # API specifications
└── startup/            # Startup standards
    ├── startup-logging.md    # Quick logging setup
    ├── startup-testing.md    # Essential testing
    └── startup-tech.md      # Minimal tech stack
```

### Templates Structure
```
docs/templates/
├── features/           # Feature templates
│   ├── corporate/     # Detailed feature templates
│   └── startup/       # Quick feature templates
└── tasks/             # Task templates
    ├── corporate/     # Comprehensive task templates
    └── startup/       # Simplified task templates
```

### Active Work Structure
```
docs/active/
├── features/          # Active feature development
│   └── [feature-name]/ # Feature-specific standards
│       ├── feature-logging.md
│       ├── feature-testing.md
│       ├── feature-api.yaml
│       └── feature-tech.md
└── tasks/             # Active task execution
    └── [task-files].md # Task plans and execution
```

## Best Practices

### Documentation Maintenance
1. **Keep standards updated** with project evolution
2. **Feature-specific standards** should extend, not duplicate
3. **Archive completed work** to maintain active directory clarity
4. **Regular review** of standards and templates

### Development Workflow
1. **Start with templates** for new features/tasks
2. **Apply context-appropriate standards** (corporate vs startup)
3. **Create feature-specific standards** as needed
4. **Use workflow rules** for automated execution

### Quality Assurance
- **Standards compliance**: Ensure all work follows established standards
- **Context awareness**: Apply appropriate level of detail
- **Documentation consistency**: Maintain uniform structure and format
- **Version control**: Track changes and maintain history

---

**Documentation Owner**: [Team Lead]
**Last Updated**: [Date]
**Review Cycle**: [Frequency]
