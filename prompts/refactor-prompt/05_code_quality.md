# CODE QUALITY MODULE

# ACTIVATION TRIGGER
Load when: Code smells detected in Phase 1 OR general quality assessment requested OR technical debt evaluation needed OR refactoring planning required OR code review preparation

# CODE QUALITY SCAN AREAS
- **Code Complexity**: Analyze cyclomatic complexity, cognitive complexity, nesting depth, function length
- **Code Smells**: Detect long methods, large classes, duplicate code blocks, complex conditionals, dead code
- **Design Patterns**: Identify anti-patterns, SOLID violations, inappropriate coupling, missing abstractions
- **Naming Conventions**: Check variable/function/class naming consistency, descriptiveness, PEP 8 compliance
- **Code Organization**: Review module structure, import organization, file organization, separation of concerns
- **Error Handling**: Analyze try/catch patterns, exception propagation, error logging, graceful degradation
- **Testing Patterns**: Identify untestable code, missing test hooks, test coverage gaps, test quality
- **Documentation Quality**: Assess inline comments, docstrings, type hints, code clarity

# CODE QUALITY PRIORITY MATRIX
- **CRITICAL**: Functions with cyclomatic complexity >15, classes >500 lines, security-impacting code quality issues, error handling that silently fails, infinite loops or recursion risks
- **HIGH**: Duplicate code blocks >20 lines, functions >50 lines, deeply nested code (>4 levels), missing error handling in critical paths, hardcoded configuration values, global state mutations
- **MEDIUM**: Missing type hints in public APIs, inconsistent naming conventions, moderate complexity (CC 8-15), minor DRY violations, missing docstrings, unused imports/variables
- **LOW**: Style guide violations, minor naming improvements, optional refactoring opportunities, cosmetic import ordering, comment improvements, whitespace issues

# QUALITY PATTERNS TO DETECT
## Anti-Patterns & Code Smells
- **God Objects**: Classes doing too much, violating single responsibility
- **Spaghetti Code**: Tangled control flow, goto-like patterns, unclear execution paths
- **Copy-Paste Programming**: Duplicate code blocks indicating missing abstractions
- **Magic Numbers/Strings**: Hardcoded values without named constants
- **Long Parameter Lists**: Functions with >5 parameters suggesting missing abstractions
- **Feature Envy**: Classes excessively using methods/properties of other classes
- **Inappropriate Intimacy**: Classes knowing too much about each other's internals

## Pythonic Patterns
- **List Comprehensions**: Identify loops that could be comprehensions
- **Context Managers**: Find file/resource handling without with statements
- **Generators**: Detect memory-heavy list operations that could use generators
- **Decorators**: Identify repeated pre/post processing that could use decorators
- **Type Hints**: Check for missing or incorrect type annotations
- **F-strings**: Find old-style string formatting that could be modernized

# OUTPUT ADDITIONS
Add code quality-specific metrics to the report:
- **Maintainability Index**: [Score 0-100 based on complexity, lines of code, and comments]
- **Technical Debt Score**: [Hours estimated to address all quality issues]
- **Complexity Distribution**: [Number of functions by complexity ranges]
- **Code Duplication**: [Percentage of duplicated code, number of duplicate blocks]
- **Test Coverage Estimate**: [Estimated coverage based on code structure]
- **Refactoring Priority List**: [Top 10 files needing attention with reasons]
- **Code Quality Grade**: [A-F with detailed justification]

# QUALITY IMPROVEMENT ROADMAP
Generate prioritized refactoring plan:
## Quick Wins (< 2 hours)
- Simple rename refactorings for clarity
- Extract magic numbers to constants
- Remove dead code and unused imports
- Add missing type hints to public APIs

## Short-term Improvements (2-8 hours)
- Extract duplicate code to shared functions
- Break down complex functions
- Improve error handling patterns
- Add comprehensive docstrings

## Major Refactoring (> 8 hours)
- Restructure large classes following SOLID principles
- Implement proper abstraction layers
- Redesign module organization
- Establish consistent patterns across codebase

# MODULE COMPLETION PROTOCOL
When code quality analysis is complete, output:

## Code Quality Module Complete
- **Analysis Status**: Complete/Partial/Needs Additional Context
- **Key Findings**: [Major code smells, complexity hotspots, refactoring opportunities]
- **Integration Notes**: [How quality issues impact security, performance, and maintainability]

## Recommended Next Steps
Based on Code Quality findings, consider loading:
- **High Priority**: Testing Module (if low testability detected), Security Module (if quality impacts security)
- **Medium Priority**: Documentation Module (for undocumented complex code), Performance Module (if inefficient patterns found)
- **Dependencies**: Quality improvements benefit all aspects of codebase health