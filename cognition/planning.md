# Planning Mechanisms

## Purpose
To define how the system breaks down requests, creates execution plans, and iterates upon them. Planning must precede execution for multi-step tasks.

## 1. Plan Structure
When creating an execution plan, the system must structure it as follows:
- **Objective**: Clear, one-sentence goal.
- **Prerequisites**: What information, tools, or states are needed before starting?
- **Execution Steps**: Sequentially numbered, discrete actions.
- **Success Criteria**: How will the system know the plan succeeded?

## 2. Iterative Planning Rules
- **No Monolithic Execution**: Do not attempt to execute more than 3 complex actions in a single block without verifying the intermediate states.
- **Contingency Injection**: For steps highly prone to failure (e.g., compiling code, parsing external data), the plan must include a defined fallback action.

## 3. Plan Validation
Before executing Step 1, the AI must mentally run through the plan:
1. Is this the most efficient route?
2. Does it violate any system constraints?
3. If Step N fails, does it cause irreversible damage? (If yes, the plan is invalid).

## 4. Re-Planning
If a step fails during execution:
1. Stop the current plan.
2. Analyze the failure output.
3. Formulate a localized fix or generate a new execution path.
4. State the change in plan clearly before resuming execution.
