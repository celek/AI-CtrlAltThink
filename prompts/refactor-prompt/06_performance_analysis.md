# PERFORMANCE ANALYSIS MODULE

# ACTIVATION TRIGGER
Load when: Performance concerns identified in Phase 1 OR large codebase detected (>10k lines) OR database/API integration present OR explicit performance audit requested OR slow response times reported

# PERFORMANCE SCAN AREAS
- **Algorithmic Complexity**: Identify O(n²) or worse algorithms, nested loops, recursive patterns without memoization
- **Database Operations**: N+1 queries, missing indexes, inefficient joins, lack of query optimization, connection pooling
- **Memory Management**: Memory leaks, large object retention, inefficient data structures, circular references
- **I/O Operations**: Synchronous file operations, blocking network calls, inefficient file reading patterns
- **Caching Opportunities**: Missing caching layers, repeated expensive computations, static data regeneration
- **Concurrency Patterns**: Blocking operations in async code, thread safety issues, GIL bottlenecks
- **Resource Usage**: CPU-intensive operations, unnecessary object creation, string concatenation in loops
- **API Performance**: Response time analysis, payload sizes, pagination implementation, rate limiting

# PERFORMANCE PRIORITY MATRIX
- **CRITICAL**: Exponential algorithms in production paths, memory leaks causing crashes, database queries >5 seconds, infinite loops, synchronous blocking in async handlers, missing database indexes on foreign keys
- **HIGH**: O(n²) algorithms with large datasets, N+1 query patterns, missing caching for expensive operations, large memory allocations, inefficient file processing, API endpoints >2 seconds response time
- **MEDIUM**: Suboptimal algorithms (could be improved by one complexity class), minor memory inefficiencies, missing pagination, redundant API calls, inefficient string operations, missing connection pooling
- **LOW**: Micro-optimizations, premature optimization opportunities, minor caching improvements, code style affecting performance marginally, optional async conversions

# PERFORMANCE PATTERNS TO DETECT
## Database Performance
- **N+1 Queries**: Detect ORM lazy loading issues
- **Missing Indexes**: Identify unindexed foreign keys and frequently queried fields
- **Inefficient Joins**: Find queries that could use select_related/prefetch_related
- **Transaction Scope**: Detect overly broad or missing transaction boundaries
- **Connection Management**: Check for connection leaks or missing pooling

## Memory & CPU Patterns
- **Memory Leaks**: Circular references, unclosed resources, growing collections
- **Inefficient Data Structures**: Using lists where sets/dicts would be better
- **String Building**: String concatenation in loops vs join() or StringIO
- **Unnecessary Copying**: Deep copies where shallow would suffice
- **Repeated Calculations**: Same expensive computation multiple times

## I/O & Network Patterns
- **Synchronous I/O**: Blocking file/network operations in async contexts
- **Batch Processing**: Missing opportunities for bulk operations
- **Streaming**: Loading entire files into memory vs streaming
- **API Chattiness**: Multiple API calls that could be combined
- **Missing Compression**: Large payloads without compression

# OUTPUT ADDITIONS
Add performance-specific metrics to the report:
- **Performance Score**: [1-10 based on identified bottlenecks and optimization potential]
- **Complexity Analysis**: [List of functions with complexity >O(n log n)]
- **Database Health**: [Query performance assessment, index coverage percentage]
- **Memory Profile**: [Estimated memory usage patterns, leak risk assessment]
- **Optimization Potential**: [Estimated performance improvement percentage]
- **Critical Paths**: [Slowest code paths with timing estimates]
- **Scalability Assessment**: [How well code will handle 10x, 100x load]

# PERFORMANCE OPTIMIZATION ROADMAP
Generate actionable performance improvements:
## Immediate Optimizations (< 1 day)
- Add missing database indexes
- Implement basic caching for expensive queries
- Fix obvious N+1 query patterns
- Replace inefficient algorithms with standard library equivalents

## Short-term Improvements (1-3 days)
- Implement query optimization strategies
- Add Redis/Memcached caching layer
- Convert synchronous I/O to async where beneficial
- Optimize data structures and algorithms

## Long-term Enhancements (> 3 days)
- Implement database query result caching
- Add CDN for static assets
- Implement background job processing
- Consider microservices for CPU-intensive operations
- Database sharding or read replicas

# PERFORMANCE BENCHMARKING
Provide performance testing recommendations:
- **Load Testing Tools**: Suggest appropriate tools (locust, ab, wrk)
- **Profiling Approach**: Recommend profiling tools and methodology
- **Monitoring Setup**: Suggest APM tools and metrics to track
- **Performance Budgets**: Define acceptable response times and resource usage
- **Optimization Validation**: How to measure improvement impact

# MODULE COMPLETION PROTOCOL
When performance analysis is complete, output:

## Performance Analysis Module Complete
- **Analysis Status**: Complete/Partial/Needs Additional Context
- **Key Findings**: [Critical bottlenecks, optimization opportunities, scalability concerns]
- **Integration Notes**: [How performance issues relate to code quality and architecture]

## Recommended Next Steps
Based on Performance Analysis findings, consider loading:
- **High Priority**: Database Module (if query issues found), Caching Module (if caching gaps identified)
- **Medium Priority**: Code Quality Module (for algorithm improvements), Architecture Module (for structural optimizations)
- **Dependencies**: Performance fixes may require framework-specific optimizations