# CODE QUALITY MODULE

# ACTIVATION TRIGGER
Load when: Code smells detected OR general quality assessment requested

# CODE QUALITY SCAN AREAS
- **Code Smells**: Long methods, large classes, duplicate code, complex conditionals
- **Naming Conventions**: Inconsistent variable/function/class naming
- **Code Organization**: Module structure, import organization, separation of concerns
- **Error Handling**: Try/catch patterns, exception propagation, error logging
- **Testing Gaps**: Missing test coverage, untestable code patterns
- **Code Complexity**: Cyclomatic complexity, nesting depth, function length

# QUALITY PATTERNS TO DETECT
- **DRY Violations**: Duplicate code blocks, repeated logic patterns
- **SOLID Principle Violations**: Single responsibility, dependency inversion issues
- **Anti-Patterns**: God objects, spaghetti code, magic numbers
- **Pythonic Code**: List comprehensions vs loops, context managers, generators

# CODE QUALITY METRICS
- **Maintainability Score**: [A-F based on complexity and organization]
- **Technical Debt Level**: [High/Medium/Low with time estimates]
- **Refactoring Priority**: [Files most in need of attention]
- **Testing Readiness**: [How testable the current code is]

# QUALITY IMPROVEMENT ROADMAP
Generate prioritized refactoring suggestions:
1. **Quick Wins**: Easy improvements with high impact
2. **Major Refactoring**: Larger structural improvements
3. **Long-term Strategy**: Architecture evolution recommendations
