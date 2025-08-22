<img src="https://r2cdn.perplexity.ai/pplx-full-logo-primary-dark%402x.png" style="height:64px;margin-right:32px"/>

# Modular Repository Analysis System

A comprehensive, AI-driven code analysis framework that uses modular prompts to perform systematic repository health assessments with safety-first principles.

## **Overview**

This system replaces monolithic code analysis prompts with a **modular, step-by-step approach** that:

- **Scales efficiently** from small scripts to enterprise repositories
- **Prioritizes critical issues** through structured severity classification
- **Maintains safety** with read-only analysis and reversible recommendations
- **Adapts intelligently** by loading only relevant analysis modules
- **Provides actionable results** with clear fix plans and verification steps


## **Design Philosophy**

### **Core Principles**

1. **Safety First**: All analysis is read-only; all recommendations are reversible
2. **Modular Architecture**: Load only what you need to reduce cognitive overhead
3. **Priority-Driven**: Address critical security and functionality issues first
4. **Evidence-Based**: Every finding includes confidence scoring and verification steps
5. **Framework-Aware**: Adapt analysis and recommendations to detected technology stack

### **Why Modular Instead of Monolithic?**

**Traditional Approach Problems:**

- 2000+ word prompts overwhelm AI attention capacity
- Generic analysis misses framework-specific issues
- All-or-nothing approach wastes resources on irrelevant checks
- No systematic progression through analysis phases

**Our Modular Solution:**

- **Phase 1**: Lightweight discovery (500-800 words)
- **Phase 2**: Load relevant modules based on findings (300-500 words each)
- **Phase 3**: Self-review and validation (200-300 words)
- **Total**: Adaptive complexity based on repository needs


## **System Architecture**

```
┌─────────────────┐    ┌──────────────────┐    ┌─────────────────┐
│   CORE PROMPT   │───→│  DISCOVERY PHASE │───→│  MODULE LOADER  │
│   (Phase 1)     │    │                  │    │                 │
│   650 words     │    │ • Scan structure │    │ • Select modules│
└─────────────────┘    │ • Detect stack   │    │ • Set priorities│
                       │ • Flag critical  │    └─────────────────┘
                       └──────────────────┘              │
                                                        ▼
┌─────────────────────────────────────────────────────────────────┐
│                     ANALYSIS MODULES                            │
├─────────────────┬─────────────────┬─────────────────┬───────────┤
│ Security        │ Dependencies    │ Code Quality    │Framework  │
│ • Vulnerabilities│ • Outdated pkgs │ • Code smells  │-Specific  │
│ • Credentials   │ • Unused deps   │ • Complexity   │• Django   │
│ • Injection     │ • Conflicts     │ • Standards    │• Flask    │
└─────────────────┴─────────────────┴─────────────────┴───────────┘
                                │
                                ▼
                    ┌─────────────────────┐
                    │   SELF-REVIEW       │
                    │   • Validate findings│
                    │   • Remove false +  │
                    │   • Refine priorities│
                    └─────────────────────┘
```


## **Module Structure**

### **Core Prompt (Always First)**

- **Purpose**: Repository discovery and initial assessment
- **Output**: Technology stack detection, critical issue flagging, module recommendations
- **Size**: 650 words
- **Always runs**: This is your entry point


### **Analysis Modules (Load as Needed)**

Each module follows this standardized structure:

```markdown
# [MODULE NAME] MODULE

# ACTIVATION TRIGGER
Load when: [Specific conditions]

# [MODULE] SCAN AREAS
- **Area 1**: [What to analyze]
- **Area 2**: [Specific patterns to detect]

# PRIORITY MATRIX
- **CRITICAL**: [Issues requiring immediate attention]
- **HIGH**: [Important issues for next sprint]
- **MEDIUM**: [Improvements for next iteration]  
- **LOW**: [Nice-to-have optimizations]

# OUTPUT ADDITIONS
[Module-specific metrics and recommendations]

# MODULE COMPLETION PROTOCOL
[How module signals completion and suggests next steps]
```


### **Available Modules**

| Module | Purpose | Load When | Size |
| :-- | :-- | :-- | :-- |
| **Security Analysis** | Vulnerability detection | Critical security issues found | 400 words |
| **Framework Detection** | Django/Flask/FastAPI analysis | Web framework detected | 500 words |
| **Dependency Analysis** | Package management review | Requirements files present | 350 words |
| **Code Quality** | Code smells and technical debt | General quality assessment needed | 450 words |
| **Performance Analysis** | Optimization opportunities | Performance concerns identified | 400 words |
| **Documentation** | Documentation coverage audit | Missing docs detected | 300 words |
| **Confidence Scoring** | Finding reliability assessment | Always recommended | 250 words |
| **Self-Review** | Validation and refinement | Always end with this | 300 words |

## **Usage Instructions**

### **Step 1: Run Core Prompt**

```markdown
[Paste the entire Core Prompt]
```

**Expected Output**: Phase 1 Discovery Report with:

- Repository summary and technology stack
- Critical issues flagged
- Module recommendations for Phase 2


### **Step 2: Load Recommended Modules**

Based on discovery results, create module loading prompt:

```markdown
**EXECUTE PHASE 2 ANALYSIS**

Based on Phase 1 discovery results, load and execute these modules:

1. **Security Analysis Module** - [Reason for loading]
2. **Framework Detection Module ([Framework])** - [Reason for loading]  
3. **Dependency Analysis Module** - [Reason for loading]
4. **Confidence Scoring Module** - [Always include]

**Context from Phase 1:**
- Repository: [Type and size]
- Critical findings: [Summary of issues]
- Framework: [Detected technology]

**Execute systematic analysis now.**

[Paste selected module prompts]
```


### **Step 3: Self-Review (Recommended)**

```markdown
**EXECUTE PHASE 3: SELF-REVIEW**

Load Self-Review Module to validate Phase 2 analysis:

**Review Focus:**
- Validate findings for false positives
- Cross-check recommendations against detected patterns
- Verify all fix plans are reversible and preserve functionality
- Refine confidence scores and effort estimates

**Execute self-review process and generate final report.**

[Paste Self-Review Module prompt]
```


### **Step 4: Implementation (Optional)**

Request specific fix implementation:

```markdown
**IMPLEMENT FIX FOR FINDING [N]**

Please implement the fix for "[Finding Title]" with:
- Step-by-step implementation
- Verification protocol
- Rollback instructions
```


## **Module Selection Guidelines**

### **Always Load**

- **Core Prompt** (Phase 1 - always first)
- **Confidence Scoring Module** (adds reliability to findings)
- **Self-Review Module** (Phase 3 - always last)


### **Load Based on Discovery**

- **Security Module**: If any security issues flagged in discovery
- **Framework Module**: If web framework detected (Django/Flask/FastAPI)
- **Dependency Module**: If requirements files present or dependency issues found
- **Code Quality Module**: For general quality assessment (most repositories benefit)
- **Performance Module**: If performance concerns noted or large codebase
- **Documentation Module**: If documentation gaps identified


### **Typical Module Combinations**

**Small Script/Tool**: Core → Code Quality → Confidence → Self-Review
**Web Application**: Core → Security → Framework → Dependencies → Code Quality → Confidence → Self-Review
**Library/Package**: Core → Dependencies → Code Quality → Documentation → Confidence → Self-Review
**Enterprise System**: All modules (full comprehensive analysis)

## **Implementation Details**

### **Module Loading Syntax**

Each module is self-contained and can be loaded by pasting its full text. Modules read context from previous phases but don't modify earlier results.

### **Context Passing**

- **Phase 1 → Phase 2**: Technology stack, critical issues, file inventory
- **Phase 2 → Phase 3**: All findings, confidence scores, recommendations
- **Module → Module**: Findings build cumulatively within Phase 2


### **Output Format Consistency**

All modules follow the standardized finding format:

```markdown
### Finding [N]: [Title] (Confidence: [Level])
- **Files**: `path/file.py:line-range`
- **Category**: [Security/Performance/Quality/etc.]
- **Issue**: [Description]
- **Impact**: [Risk/cost]
- **Fix Plan**: [Implementation approach]
- **Verification**: [Test steps]
- **Effort**: [S/M/L/XL]
```


## **Best Practices**

### **For Users**

1. **Always start with Core Prompt** - don't skip discovery phase
2. **Load modules incrementally** - don't overwhelm with all modules at once
3. **Read discovery results carefully** - they guide optimal module selection
4. **Always end with Self-Review** - it catches false positives and improves quality
5. **Request specific implementations** - the system can guide fix execution

### **For Module Development**

1. **Keep modules focused** - each should have a clear, single responsibility
2. **Include completion protocols** - modules should guide next steps
3. **Maintain consistent output format** - findings should be comparable across modules
4. **Add confidence indicators** - help users prioritize attention
5. **Provide verification steps** - every recommendation needs testing guidance

## **Troubleshooting**

### **Common Issues**

**"Module recommends running [X] but [X] doesn't exist"**

- Check that all referenced modules are included in the Available Modules list
- Verify module names match exactly between references and implementations

**"Getting inconsistent outputs between runs"**

- Ensure you're providing consistent context between phases
- Use the same discovery results when loading Phase 2 modules

**"Too many findings to process"**

- Focus on Critical and High priority findings first
- Use confidence scoring to prioritize attention
- Consider loading fewer modules for initial assessment

**"Module seems to miss framework-specific issues"**

- Ensure Framework Detection module is loaded when web frameworks detected
- Check that framework detection in Phase 1 was accurate


### **Quality Control**

- Each module includes self-validation logic
- Self-Review module catches cross-module conflicts
- Confidence scoring helps identify uncertain findings
- All recommendations include reversibility instructions


## **Evolution and Maintenance**

This system is designed to be **extensible**:

- **Add new modules** for emerging technologies or analysis types
- **Modify existing modules** based on effectiveness feedback
- **Adjust module combinations** based on usage patterns
- **Refine output formats** as user needs evolve

The modular architecture ensures changes to one module don't impact others, making the system maintainable and adaptable to new requirements.

***

**Ready to analyze your repository? Start with the Core Prompt and follow the phase-by-phase workflow above.**

