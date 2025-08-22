# DEPENDENCY ANALYSIS MODULE

# ACTIVATION TRIGGER
Load when: Requirements files detected (requirements.txt, setup.py, pyproject.toml, Pipfile) OR dependency-related issues identified in Phase 1 discovery OR explicitly requested for package audit

# DEPENDENCY SCAN AREAS
- **Package Versions**: Analyze all dependency files for version specifications, pinning strategies, and update availability
- **Security Vulnerabilities**: Cross-reference all packages against CVE databases and security advisories
- **Unused Dependencies**: Identify packages listed in requirements but not imported anywhere in codebase
- **Missing Dependencies**: Detect imports in code that lack corresponding requirement entries
- **Version Conflicts**: Find incompatible version specifications across different requirement files
- **Transitive Dependencies**: Analyze dependency chains for conflicts and security issues
- **License Compliance**: Review package licenses for compatibility and legal requirements
- **Package Health**: Check for deprecated, abandoned, or unmaintained packages

# DEPENDENCY PRIORITY MATRIX
- **CRITICAL**: Known security vulnerabilities with available fixes, missing essential dependencies causing import failures, packages with critical CVEs
- **HIGH**: Severely outdated packages (>2 major versions behind), version conflicts preventing installation, deprecated packages still in use, unmaintained packages in core functionality
- **MEDIUM**: Unused dependencies consuming resources, minor version updates with bug fixes, packages with non-critical vulnerabilities, missing dev dependencies
- **LOW**: Optional dependency optimizations, documentation dependencies, cosmetic version pinning improvements, test-only dependency updates

# OUTPUT ADDITIONS
Add dependency-specific metrics to the report:
- **Dependency Health Score**: [1-10 based on overall dependency state]
- **Security Vulnerabilities**: [Count by severity: Critical/High/Medium/Low]
- **Update Summary**: [X packages need major updates, Y need minor updates]
- **Unused Package Count**: [Number of removable dependencies with estimated size savings]
- **Missing Dependencies**: [List of imports without requirements]
- **License Risk Assessment**: [High/Medium/Low based on license compatibility]
- **Technical Debt**: [Estimated hours to update all dependencies]

# DEPENDENCY-SPECIFIC RECOMMENDATIONS
Generate actionable dependency management improvements:
- **Immediate Actions**: Security patches and critical updates
- **Version Pinning Strategy**: Recommendations for version specification approach
- **Dependency Cleanup**: List of safe-to-remove packages
- **Update Sequence**: Order for updating packages to minimize conflicts
- **Alternative Packages**: Suggest replacements for deprecated/abandoned packages

# MODULE COMPLETION PROTOCOL
When dependency analysis is complete, output:

## Dependency Analysis Module Complete
- **Analysis Status**: Complete/Partial/Needs Additional Context
- **Key Findings**: [Summary of dependency health, critical issues, and improvement opportunities]
- **Integration Notes**: [How dependency issues relate to security, performance, and framework modules]

## Recommended Next Steps
Based on Dependency Analysis findings, consider loading:
- **High Priority**: Security Module (if vulnerabilities found), Framework Module (for framework-specific dependencies)
- **Medium Priority**: Performance Module (if heavy dependencies detected), Code Quality Module (for import organization)
- **Dependencies**: Results enhance Security and Framework module analyses