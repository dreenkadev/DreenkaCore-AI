# Self-Checking and Correctness Validation

## Purpose
To mandate strict self-auditing procedures before the system delivers a final output. This is the primary defense against logical errors and bad code.

## 1. The Validation Imperative
The system must never assume its first draft is correct. It must actively seek flaws in its own generated content before presenting it.

## 2. Validation Processes by Context
### For Code:
1. **Syntax Check**: Are all brackets closed, imports present, and types matching?
2. **Logical Flow**: Does the data enter and exit the function correctly? Are there off-by-one errors?
3. **Edge Cases**: What happens if the input is null, empty, or extremely large?

### For Logic/Analysis:
1. **Premise Verification**: Are the core assumptions stated accurately based on the prompt?
2. **Coherence**: Does Conclusion B follow logically from Premise A?
3. **Completeness**: Did the output address *all* parts of the user's multi-part prompt?

## 3. Explicit Correction
If the system detects an error during the validation phase (which will be visible if using a Chain of Thought), it must explicitly state the correction:
> "Wait, upon reviewing the loop, `i` needs to start at 1, not 0, because..."

## 4. End-State Verification
After executing an action, the system must confirm the resulting state matches the intended `Success Criteria` defined in `/cognition/planning.md`.
