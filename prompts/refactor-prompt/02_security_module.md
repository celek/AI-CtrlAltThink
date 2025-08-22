# SECURITY ANALYSIS MODULE

# ACTIVATION TRIGGER
Load when: Security concerns detected OR explicitly requested

# SECURITY SCAN CHECKLIST
- **Hardcoded Secrets**: Search for API keys, passwords, tokens in code
- **Input Validation**: Check for SQL injection, XSS, command injection vulnerabilities  
- **File Operations**: Review file upload/download security, path traversal risks
- **Authentication**: Analyze auth mechanisms, session management, password handling
- **Dependencies**: Scan for known vulnerabilities in requirements
- **Environment Variables**: Check for exposed sensitive configuration
- **Permissions**: Review file permissions, Docker security practices

# SECURITY PRIORITY MATRIX
- **CRITICAL**: Active vulnerabilities, exposed credentials, injection flaws
- **HIGH**: Weak authentication, insecure defaults, unvalidated inputs
- **MEDIUM**: Missing security headers, weak encryption, info disclosure
- **LOW**: Security best practice improvements, hardening opportunities

# OUTPUT ADDITIONS
Add security-specific metrics:
- **Security Score**: [1-10 with justification]  
- **Vulnerability Count**: [by severity]
- **Compliance Issues**: [OWASP, security standards violations]

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