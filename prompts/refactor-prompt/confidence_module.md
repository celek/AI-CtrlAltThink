# CONFIDENCE SCORING MODULE

# CONFIDENCE CALCULATION
For each finding, assign confidence based on:
- **HIGH (90-100%)**: Definitive issues with clear evidence
- **MEDIUM (60-89%)**: Likely issues requiring verification
- **LOW (30-59%)**: Potential issues needing investigation

# CONFIDENCE FACTORS
- **Static Analysis Certainty**: How definitive the code pattern detection is
- **Context Availability**: Whether full context was available for analysis
- **Framework Knowledge**: Confidence in framework-specific recommendations
- **Test Coverage**: Whether the area has existing test coverage

# CONFIDENCE OUTPUT
Add to each finding:
- **Confidence Level**: [High/Medium/Low]
- **Uncertainty Factors**: [What might affect the recommendation]
- **Verification Priority**: [Immediate/Soon/When Convenient]