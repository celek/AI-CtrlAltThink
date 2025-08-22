# FRAMEWORK DETECTION MODULE

# ACTIVATION TRIGGER
Load when: Web framework indicators detected (Django manage.py, Flask app.py, FastAPI main.py) OR web application patterns identified OR API endpoints discovered OR explicitly requested for framework-specific analysis

# FRAMEWORK SCAN AREAS
- **Framework Identification**: Detect primary framework through file patterns, imports, and project structure
- **Framework Version**: Identify specific version for version-specific recommendations
- **Configuration Analysis**: Review framework configuration files for security and optimization
- **Routing Patterns**: Analyze URL routing, endpoint definitions, and API structure
- **Middleware Stack**: Examine middleware configuration and ordering
- **Template Systems**: Review template usage, inheritance, and security
- **Database Integration**: Check ORM usage, query patterns, and migration status
- **Authentication/Authorization**: Analyze auth implementation and session management

# FRAMEWORK-SPECIFIC DETECTION
## Django Detection & Analysis
- **Indicators**: manage.py, settings.py, INSTALLED_APPS, django imports
- **Check for**: DEBUG settings in production, SECRET_KEY exposure, ALLOWED_HOSTS configuration
- **Models**: Migration health, model relationships, database indexes, query optimization
- **Views**: Class-based vs function-based patterns, permission decorators, CSRF protection
- **Templates**: Template injection risks, context processors, static file handling
- **Admin Interface**: Admin site security, custom admin actions, permissions

## Flask Detection & Analysis
- **Indicators**: Flask imports, app.py/application.py, blueprints folder structure
- **Check for**: App factory pattern usage, configuration management, environment variables
- **Blueprints**: Blueprint organization, circular imports, proper registration
- **Extensions**: Flask-Login, Flask-SQLAlchemy, Flask-WTF security configurations
- **Request Handling**: Request context usage, before/after request hooks, error handlers
- **Session Management**: Session configuration, cookie security settings

## FastAPI Detection & Analysis
- **Indicators**: FastAPI imports, uvicorn, async def endpoints, Pydantic models
- **Check for**: Async/await patterns, dependency injection usage, response models
- **API Documentation**: OpenAPI schema generation, documentation completeness
- **Validation**: Pydantic model validation, request/response serialization
- **Performance**: Async implementation quality, blocking operations in async context
- **Security**: OAuth2 implementation, JWT handling, CORS configuration

# FRAMEWORK PRIORITY MATRIX
- **CRITICAL**: DEBUG enabled in production, exposed SECRET_KEY, missing CSRF protection, SQL injection vulnerabilities, authentication bypass risks, insecure session configuration
- **HIGH**: Missing security headers, improper CORS settings, unprotected admin interfaces, missing rate limiting, insecure file uploads, weak password policies
- **MEDIUM**: Suboptimal ORM queries, missing database indexes, improper error handling, outdated framework version, missing input validation, incomplete logging
- **LOW**: Code organization improvements, missing docstrings, template optimization, static file handling, development settings cleanup, cosmetic routing improvements

# OUTPUT ADDITIONS
Add framework-specific metrics to the report:
- **Framework Health Score**: [1-10 based on framework best practices]
- **Security Posture**: [Assessment of framework-specific security measures]
- **Performance Indicators**: [ORM query efficiency, caching usage, async implementation]
- **Configuration Quality**: [Production readiness, environment separation]
- **Framework Version Status**: [Current/Outdated/EOL with upgrade path]
- **Best Practices Adherence**: [Percentage following framework conventions]

# ADAPTIVE RECOMMENDATIONS
Generate framework-specific improvement plans:
- **Security Hardening**: Framework-specific security configurations and middleware
- **Performance Optimization**: Caching strategies, query optimization, async improvements
- **Structure Refactoring**: Align with framework best practices and patterns
- **Testing Approach**: Framework-specific testing tools and strategies
- **Deployment Considerations**: Production configuration checklist
- **Migration Path**: Steps to upgrade framework version if needed

# MODULE COMPLETION PROTOCOL
When framework analysis is complete, output:

## Framework Detection Module Complete
- **Analysis Status**: Complete/Partial/Needs Additional Context
- **Key Findings**: [Detected framework, version, major configuration issues, security concerns]
- **Integration Notes**: [Framework-specific security and performance considerations for other modules]

## Recommended Next Steps
Based on Framework Detection findings, consider loading:
- **High Priority**: Security Module (for framework-specific vulnerabilities), Performance Module (for framework optimization)
- **Medium Priority**: Code Quality Module (for framework patterns), Dependency Module (for framework packages)
- **Dependencies**: Framework context enhances all other module analyses