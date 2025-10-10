1. Introduction
2. Framework: Key Questions for RLHF Debugging
2.1 When to “Reset and Restart” vs. Adjust Hyperparameters
2.2 How to Detect “Gaming the System” (Reward Hacking)
2.3 Signs the SFT Foundation Is Insufficient
2.4 Identifying Preference Data Echo Chambers
2.5 Determining When SFT Alone Is Sufficient
3. Detecting the Chef Plateau
3.1 Evaluation Metrics Stagnation
3.2 Learning Curve Analysis
3.3 Behavioral Indicators
4. Pre-Flight Check: Verify the Foundation
4.1 SFT Model Capability Assessment
4.2 Preference Data Quality Audit
4.3 Task Complexity \& Baseline Benchmarks
5. Should We Go Further?
5.1 Data Ceiling \& Compute ROI
5.2 Task Necessity for RLHF
5.3 SFT Sufficiency Check
6. PPO-Specific Diagnostics
6.1 Common Failure Signatures
6.2 Diagnostic Techniques
6.3 Resolution Strategies
6.4 Prevention Measures
7. DPO-Specific Diagnostics
7.1 Common Failure Signatures
7.2 Diagnostic Techniques
7.3 Resolution Strategies
7.4 Prevention Measures
8. GRPO-Specific Diagnostics
8.1 Common Failure Signatures
8.2 Diagnostic Techniques
8.3 Resolution Strategies
8.4 Prevention Measures
9. Common Pitfalls (Universal RLHF Issues)
9.1 Reward Hacking
9.2 Echo Chamber Bias
9.3 Distribution Mismatch
10. Advanced Universal Issues
10.1 Curriculum Progression Traps
10.2 Reward Model Generalization Gaps
11. Tools \& Instrumentation
11.1 Monitoring with Weights \& Biases
11.2 TensorBoard Dashboards
11.3 Custom Logging \& Alerting
12. War Stories: End-to-End Debugging Case Studies
13. Debugging Cheat Sheet
13.1 Symptom → Likely Cause Mapping
13.2 Emergency Fixes
13.3 Hyperparameter Guidelines
14. Next Steps \& Investigation Plan
14.1 Timeline Estimates
14.2 Resource Allocation Guidance
14.3 Experiment Logging Templates