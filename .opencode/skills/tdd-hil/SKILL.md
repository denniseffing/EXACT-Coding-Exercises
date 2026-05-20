---
name: tdd-hil
description: |
  Use ONLY when conducting TDD with Red-Green-Refactor phases that require human-in-the-loop checkpoints.
  Provides the mandatory confirmation rules after each TDD phase.
---

# Human-in-the-Loop TDD Rules

These rules ensure the human stays engaged and can provide guidance at critical decision points during Test-Driven Development. The AI must pause and explicitly ask for user feedback in these specific situations.

## Rule 1: End-of-Phase Confirmation

### When to Apply
At the **end of every TDD phase** (Red, Green, or Refactor), before proceeding to the next phase or test.

### What to Do
1. **Stop after completing the current phase**
2. **Summarize what was just completed in this phase**:

   **After Red Phase**:
   - Which test was activated
   - Prediction made and whether it was correct
   - Type of failure achieved (compilation / runtime error)

   **After Green Phase**:
   - Implementation approach taken (minimal code added)
   - Confirmation that test now passes
   - Any trade-offs or decisions made

   **After Refactor Phase**:
   - Refactorings attempted / completed:
     - Naming changes made
     - Mass calculations (before / after if applicable)
     - Structural improvements
     - Any refactoring opportunities that were rejected and why

3. **Explicitly ask for permission to continue**:
   - **After Red**: "Red phase complete. Should I proceed to Green phase?"
   - **After Green**: "Green phase complete. Should I proceed to Refactor phase?"
   - **After Refactor**: "Refactor phase complete. Should I proceed to the next test?"

## Rule 2: Failed Prediction Recovery

### When to Apply
When the **"Guessing Game" prediction fails** — the actual test result differs significantly from what was predicted.

### What to Do
1. **Stop the TDD cycle immediately**
2. **Explain the prediction failure**:
   - What was predicted (error type, expected / actual values)
   - What actually happened
   - Why the prediction was wrong (if clear)
3. **Assess the implications**:
   - Does this indicate a misunderstanding of the code?
   - Does this suggest the test or implementation has issues?
   - Is this a learning opportunity about the system behavior?
4. **Explicitly ask**:
   - "My prediction was incorrect. Should I continue with the TDD process, or would you like me to investigate this discrepancy further?"

## Core Principle: Never Proceed Without Permission
- **Stop after every single phase** (Red, Green, Refactor)
- **Implement only what the current phase requires**
- **No lookahead or anticipatory coding**
- **No additional features without explicit human approval**
- **Each phase must be approved before continuing to next phase**
