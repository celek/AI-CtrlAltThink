# CONFIDENCE SCORING MODULE

# ACTIVATION TRIGGER
Load when: Always recommended after initial analysis modules OR uncertainty in findings OR complex codebase with limited context OR automated analysis results need validation OR risk assessment required

# CONFIDENCE SCAN AREAS
- **Finding Validation**: Review each finding for supporting evidence and potential false positives
- **Context Completeness**: Assess whether full context was available for accurate analysis
- **Pattern Certainty**: Evaluate how definitively code patterns match known issues
- **Tool Limitations**: Consider limitations of static analysis without runtime information
- **Framework Knowledge**: Gauge confidence in framework-specific recommendations
- **Dependency Analysis**: Assess accuracy of third-party package vulnerability detection
- **Code Coverage**: Evaluate what percentage of codebase was actually analyzed
- **Edge Cases**: Identify findings that may only apply in specific scenarios

# CONFIDENCE PRIORITY MATRIX
- **CRITICAL CONFIDENCE FACTORS**: Findings that could break production if wrong, security recommendations that might introduce vulnerabilities, architectural changes with wide impact, data migration or schema changes
- **HIGH CONFIDENCE FACTORS**: Performance optimizations that could degrade performance, refactoring recommendations affecting core business logic, dependency updates with breaking changes, framework migration suggestions
- **MEDIUM CONFIDENCE FACTORS**: Code quality improvements, documentation suggestions, minor optimization recommendations, style guide enforcement
- **LOW CONFIDENCE FACTORS**: Cosmetic changes, optional enhancements, future-proofing suggestions, nice-to-have features

# CONFIDENCE CALCULATION METHODOLOGY
## Evidence-Based Scoring
For each finding, calculate confidence based on:
- **Direct Evidence (90-100%)**: Clear code patterns, definitive syntax errors, obvious security vulnerabilities
- **Strong Indicators (70-89%)**: Multiple supporting patterns, consistent anti-patterns, well-documented issues
- **Moderate Indicators (50-69%)**: Some supporting evidence, common patterns, industry best practices
- **Weak Indicators (30-49%)**: Limited context, assumptions required, edge cases possible
- **Speculative (<30%)**: Insufficient information, requires runtime analysis, highly context-dependent

## Confidence Factors Assessment
- **Static Analysis Certainty**: How definitive the code pattern detection is
- **Context Availability**: Whether imports, dependencies, and related files were analyzed
- **Framework Specificity**: Confidence in framework-specific patterns and conventions
- **Test Coverage**: Whether the area has existing tests that validate behavior
- **Code Complexity**: Higher complexity reduces confidence in analysis
- **External Dependencies**: Uncertainty from third-party library behavior
- **Runtime Behavior**: Limitations of static analysis without execution context

# OUTPUT ADDITIONS
Add confidence-specific enhancements to each finding:
- **Confidence Score**: [Percentage with justification]
- **Evidence Quality**: [Strong/Moderate/Weak with specific examples]
- **Uncertainty Factors**: [List of assumptions and limitations]
- **Verification Priority**: [Immediate/Soon/Eventually based on risk]
- **False Positive Risk**: [High/Medium/Low with explanation]
- **Validation Method**: [How to verify the finding is accurate]
- **Alternative Interpretations**: [Other possible explanations]

# CONFIDENCE-BASED RECOMMENDATIONS
Adjust recommendations based on confidence levels:
## High Confidence (>80%)
- Proceed with implementation
- Include in immediate action items
- Automate fixes where possible
- Mark as priority fixes

## Medium Confidence (50-80%)
- Recommend manual review first
- Suggest testing in development
- Provide validation steps
- Include in code review discussions

## Low Confidence (<50%)
- Flag for expert review
- Suggest additional investigation
- Provide multiple solution options
- Defer to team decision

# RISK MITIGATION STRATEGIES
Based on confidence scoring, suggest:
- **Testing Requirements**: Additional tests needed before implementing changes
- **Rollback Plans**: How to revert if issues arise
- **Staged Rollout**: Gradual implementation for uncertain changes
- **Monitoring Points**: What to watch after changes
- **Documentation Needs**: Areas requiring better documentation for confidence

# MODULE COMPLETION PROTOCOL
When confidence scoring is complete, output:

## Confidence Scoring Module Complete
- **Analysis Status**: Complete with confidence distribution
- **Key Findings**: [High-confidence issues requiring action, low-confidence areas needing review]
- **Integration Notes**: [How confidence scoring affects priority and implementation approach]

## Recommended Next Steps
Based on Confidence Scoring results:
- **High Priority**: Manual review of low-confidence critical findings, validation of high-impact recommendations
- **Medium Priority**: Testing plan for medium-confidence changes, expert review requests
- **Dependencies**: Confidence scores should influence all implementation decisions