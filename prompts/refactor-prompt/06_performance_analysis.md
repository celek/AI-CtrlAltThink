# PERFORMANCE ANALYSIS MODULE

# PERFORMANCE SCAN AREAS
- **Algorithmic Complexity**: Identify O(n²) or worse algorithms
- **Database Queries**: Check for N+1 queries, missing indexes, inefficient joins
- **Memory Usage**: Look for memory leaks, large object retention
- **I/O Operations**: Review file operations, network calls, blocking operations
- **Caching**: Identify missing caching opportunities
- **Async Opportunities**: Find blocking operations that could be async

# PERFORMANCE BENCHMARKING
Generate baseline performance expectations:
- **Load Testing Recommendations**: Suggest tools and approaches
- **Monitoring Setup**: Recommend performance monitoring integration  
- **Profiling Guidance**: Identify code sections that need profiling

# PERFORMANCE METRICS
- **Performance Score**: [1-10 based on detected issues]
- **Optimization Potential**: [High/Medium/Low]
- **Resource Efficiency**: [Memory, CPU, I/O usage assessment]

# MODULE COMPLETION PROTOCOL
When analysis is complete, output:

## [Module Name] Analysis Complete
- **Analysis Status**: Complete/Partial/Needs Additional Context
- **Key Findings**: [Brief summary of main discoveries]
- **Integration Notes**: [How findings relate to other modules]

## Recommended Next Steps
Based on [Module Name] findings, consider loading:
- **High Priority**: [Critical modules to run next]
- **Medium Priority**: [Complementary modules]
- **Dependencies**: [Modules that depend on these results]