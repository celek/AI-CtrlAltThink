# DOCUMENTATION ANALYSIS MODULE

# ACTIVATION TRIGGER
Load when: Documentation gaps identified in Phase 1 OR README missing/incomplete OR API documentation needed OR docstring coverage <50% OR explicit documentation audit requested OR onboarding improvement needed

# DOCUMENTATION SCAN AREAS
- **README Quality**: Completeness, setup instructions, usage examples, prerequisites, contribution guidelines
- **API Documentation**: Function/class docstrings, parameter descriptions, return value documentation, type hints
- **Code Comments**: Inline comment quality, complex logic explanation, TODO/FIXME tracking, decision rationale
- **Configuration Documentation**: Environment variables, settings files, deployment configuration, secrets management
- **Architecture Documentation**: System design docs, component relationships, data flow diagrams, decision records
- **User Documentation**: End-user guides, tutorials, FAQ sections, troubleshooting guides
- **Developer Documentation**: Development setup, testing procedures, debugging guides, code style guides
- **Change Documentation**: CHANGELOG maintenance, version history, migration guides, breaking changes

# DOCUMENTATION PRIORITY MATRIX
- **CRITICAL**: Missing README, no setup instructions, undocumented breaking changes, missing API documentation for public interfaces, no license file, missing security documentation
- **HIGH**: Incomplete installation guide, missing docstrings for public functions, undocumented configuration options, no contribution guidelines, missing architecture overview, no testing documentation
- **MEDIUM**: Inconsistent docstring format, missing inline comments for complex logic, outdated examples, incomplete type hints, missing troubleshooting section, no code style guide
- **LOW**: Minor grammar/spelling issues, optional enhancement suggestions, missing comments for simple code, cosmetic formatting improvements, nice-to-have diagrams

# DOCUMENTATION STANDARDS
## Docstring Formats
- **Google Style**: Check for consistent Google-style docstrings
- **NumPy Style**: Verify NumPy documentation format compliance
- **Sphinx Style**: Validate reStructuredText format
- **Type Hints**: Ensure alignment between docstrings and type annotations
- **Examples**: Verify code examples are current, runnable, and meaningful

## README Components
- **Project Title & Description**: Clear, concise project overview
- **Installation**: Step-by-step setup instructions
- **Usage**: Basic usage examples with expected outputs
- **API Reference**: Link to detailed API documentation
- **Contributing**: Guidelines for contributors
- **License**: License information and copyright
- **Contact**: Maintainer information and support channels

## Code Comment Quality
- **Complex Logic**: Every non-obvious algorithm explained
- **Business Rules**: Domain logic clearly documented
- **Workarounds**: Temporary fixes explained with TODOs
- **Design Decisions**: Rationale for architectural choices
- **External Dependencies**: Why specific libraries chosen

# OUTPUT ADDITIONS
Add documentation-specific metrics to the report:
- **Documentation Coverage**: [Percentage of functions/classes with docstrings]
- **README Completeness Score**: [0-100 based on essential sections]
- **Docstring Quality**: [A-F grade based on completeness and accuracy]
- **Comment Density**: [Ratio of comment lines to code lines]
- **Documentation Freshness**: [Last update vs last code change]
- **Missing Documentation**: [List of undocumented public APIs]
- **Documentation Debt**: [Estimated hours to achieve full documentation]

# DOCUMENTATION IMPROVEMENT PLAN
Generate prioritized documentation tasks:
## Immediate Documentation (< 4 hours)
- Create/update README with basic setup instructions
- Document all public API functions
- Add docstrings to critical business logic
- Document environment variables and configuration

## Short-term Documentation (1-2 days)
- Write comprehensive usage examples
- Create architecture overview document
- Add inline comments for complex algorithms
- Develop troubleshooting guide
- Document testing procedures

## Long-term Documentation (> 2 days)
- Create interactive API documentation (Sphinx/MkDocs)
- Develop video tutorials or screencasts
- Write comprehensive developer guide
- Create decision architecture records (ADRs)
- Build automated documentation generation

# DOCUMENTATION GENERATION HELPERS
Provide templates and tools:
- **Docstring Templates**: Generate skeleton docstrings for undocumented functions
- **README Template**: Provide markdown template with all essential sections
- **Documentation Tools**: Recommend Sphinx, MkDocs, or similar based on project
- **Badge Suggestions**: Propose relevant shields.io badges for README
- **Example Code**: Generate usage examples based on function signatures

# MODULE COMPLETION PROTOCOL
When documentation analysis is complete, output:

## Documentation Analysis Module Complete
- **Analysis Status**: Complete/Partial/Needs Additional Context
- **Key Findings**: [Documentation coverage gaps, quality issues, missing critical docs]
- **Integration Notes**: [How documentation relates to code quality and maintainability]

## Recommended Next Steps
Based on Documentation Analysis findings, consider loading:
- **High Priority**: Code Quality Module (to understand what needs documenting), Testing Module (to document test procedures)
- **Medium Priority**: API Module (for API documentation), Security Module (for security documentation)
- **Dependencies**: Good documentation depends on stable, well-structured code