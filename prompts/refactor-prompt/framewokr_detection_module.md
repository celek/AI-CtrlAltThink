# FRAMEWORK DETECTION MODULE

# DETECTION LOGIC
1. **Django**: Check for manage.py, settings.py, INSTALLED_APPS
2. **Flask**: Look for Flask imports, app.py patterns, blueprints
3. **FastAPI**: Detect FastAPI imports, async patterns, Pydantic models
4. **Generic Python**: Fallback for non-web applications

# FRAMEWORK-SPECIFIC ANALYSIS
## Django Specific
- **Models**: Check for migrations, model best practices, security issues
- **Views**: Review class-based vs function-based patterns, security decorators
- **Settings**: Validate DEBUG settings, SECRET_KEY handling, database config
- **URLs**: Check for URL pattern security, proper routing

## Flask Specific  
- **App Factory**: Review application factory pattern usage
- **Blueprints**: Analyze blueprint organization and security
- **Config**: Check configuration management, environment handling
- **Extensions**: Review Flask extension usage and security

## FastAPI Specific
- **Dependencies**: Analyze dependency injection patterns
- **Async**: Review async/await usage and performance implications
- **Validation**: Check Pydantic model validation and serialization
- **Documentation**: Verify auto-generated API documentation accuracy

# ADAPTIVE RECOMMENDATIONS
Adjust suggestions based on detected framework:
- Framework-specific security best practices
- Performance optimization patterns for the framework
- Testing approach recommendations
- Documentation standards for the framework