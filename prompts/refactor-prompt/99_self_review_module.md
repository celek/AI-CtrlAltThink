# SELF-REVIEW MODULE

# ACTIVATION TRIGGER
Load when: Always recommended as final phase after all analysis modules complete OR when conflicting recommendations detected OR high number of findings need prioritization OR validation of automated analysis required

# SELF-REVIEW SCAN AREAS
- **Finding Validation**: Cross-check all findings for false positives, duplicates, and conflicts
- **Completeness Check**: Ensure all critical code areas were analyzed appropriately
- **Recommendation Refinement**: Consolidate related findings and clarify implementation steps
- **Priority Verification**: Validate that priority assignments align with actual business impact
- **Consistency Check**: Ensure recommendations don't contradict each other or break functionality
- **Coverage Assessment**: Identify any gaps in the analysis or missed problem areas
- **Integration Review**: Verify that fixes work together cohesively
- **Risk Assessment**: Evaluate potential negative impacts of proposed changes

# SELF-REVIEW PRIORITY MATRIX
- **CRITICAL REVIEW ITEMS**: Conflicting security recommendations, changes that could break production, database migrations, authentication/authorization changes, recommendations affecting data integrity
- **HIGH REVIEW ITEMS**: Performance optimizations with trade-offs, large refactoring suggestions, dependency updates with breaking changes, architectural modifications
- **MEDIUM REVIEW ITEMS**: Code quality improvements affecting multiple files, testing strategy changes, documentation overhauls, development workflow modifications
- **LOW REVIEW ITEMS**: Style guide updates, minor optimizations, cosmetic improvements, optional enhancements

# REVIEW PROTOCOL PHASES
## Phase 1: Finding Validation
- **False Positive Detection**: Identify findings that don't apply to this codebase
- **Context Verification**: Ensure findings have complete context
- **Pattern Matching**: Verify that detected patterns are actually problematic
- **Framework Compatibility**: Confirm recommendations align with framework best practices
- **Business Logic Check**: Ensure suggestions don't break business requirements

## Phase 2: Consolidation & Deduplication
- **Merge Similar Findings**: Combine related issues into comprehensive fixes
- **Remove Duplicates**: Eliminate redundant recommendations across modules
- **Group by Component**: Organize findings by affected system components
- **Dependency Ordering**: Sequence fixes based on dependencies
- **Effort Batching**: Group fixes by implementation effort

## Phase 3: Risk & Impact Analysis
- **Breaking Change Assessment**: Identify changes that could disrupt service
- **Rollback Complexity**: Evaluate how easily changes can be reverted
- **Testing Requirements**: Determine testing needed for each change
- **Performance Impact**: Assess potential performance implications
- **Security Implications**: Review security impact of all recommendations

## Phase 4: Quality Assurance
- **File Path Validation**: Verify all referenced files and line numbers exist
- **Code Sample Accuracy**: Ensure code snippets accurately represent issues
- **Fix Plan Feasibility**: Confirm implementation steps are practical
- **Estimate Refinement**: Adjust effort estimates based on full context
- **Documentation Completeness**: Ensure all findings have clear explanations

# OUTPUT ADDITIONS
Generate refined analysis report with:
- **Validated Finding Count**: [Original count → Validated count after review]
- **False Positive Rate**: [Percentage of findings removed as false positives]
- **Consolidation Summary**: [How many findings were merged]
- **Risk Assessment Matrix**: [High/Medium/Low risk for each recommendation]
- **Implementation Roadmap**: [Sequenced plan for applying fixes]
- **Confidence Adjustments**: [List of confidence level changes made]
- **Coverage Gaps**: [Areas that need additional analysis]

# FINAL RECOMMENDATIONS
## Immediate Actions (Do Today)
- Critical security fixes with high confidence
- Breaking functionality repairs
- Data integrity issues
- Performance bottlenecks affecting users

## Short-term Improvements (This Week)
- High-priority code quality issues
- Important dependency updates
- Key documentation gaps
- Testing infrastructure setup

## Long-term Enhancements (This Month)
- Architectural improvements
- Comprehensive refactoring
- Performance optimizations
- Documentation overhaul

## Future Considerations (Backlog)
- Nice-to-have enhancements
- Experimental optimizations
- Long-term migration plans
- Optional tool adoptions

# SELF-REVIEW VALIDATION CHECKLIST
Ensure before finalizing:
- [ ] All critical issues have been identified
- [ ] No recommendations conflict with each other
- [ ] Priority levels align with business impact
- [ ] All fixes include verification steps
- [ ] Effort estimates are realistic
- [ ] Rollback procedures are documented
- [ ] Dependencies between fixes are mapped
- [ ] Team capacity considered in roadmap

# MODULE COMPLETION PROTOCOL
When self-review is complete, output:

## Self-Review Module Complete
- **Analysis Status**: Final review complete with [X] findings validated
- **Key Findings**: [Summary of critical validated issues, removed false positives, consolidated recommendations]
- **Integration Notes**: [Final implementation sequence and dependency map]

## Final Report Summary
- **Total Validated Findings**: [Count by priority]
- **Estimated Total Effort**: [Hours/days to address all issues]
- **Risk Assessment**: [Overall risk level of implementing recommendations]
- **Recommended Starting Point**: [First 3 actions to take]
- **Success Metrics**: [How to measure improvement after fixes]