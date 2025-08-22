# VERIFICATION TEMPLATES MODULE

# TEMPLATE LIBRARY

## Security Fix Verification
```

1. **Credential Scan**: Run `git log --all --grep="password\|key\|secret" -p`
2. **Dependency Check**: `pip-audit` or `safety check`
3. **Input Validation Test**: [Specific test cases for the fix]
4. **Authentication Test**: [Login/logout flow verification]
```

## Performance Fix Verification  
```

1. **Baseline Measurement**: [Before fix performance metrics]
2. **Load Test**: [Specific load testing approach]
3. **Resource Monitoring**: [Memory/CPU monitoring during test]
4. **Regression Test**: [Ensure functionality preserved]
```

## Code Quality Fix Verification
```

1. **Functionality Test**: [Core feature verification]
2. **Edge Case Testing**: [Boundary condition tests]
3. **Integration Test**: [Component interaction verification]
4. **Style Check**: [Linting/formatting verification]
```

# VERIFICATION COORDINATOR
Select appropriate template based on:
- Fix category (security, performance, quality)
- Framework type (Django, Flask, FastAPI)
- Risk level (critical, high, medium, low)