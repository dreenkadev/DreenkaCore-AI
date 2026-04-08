# Overall Execution Flow

## Purpose
To define the macro-level state machine that governs how the system transitions from receiving a prompt to delivering the final, actionable output.

## 1. The Execution Lifecycle
Every complex task must loop through the following phases:

### Phase 1: Ingestion & Analysis
- Parse the prompt.
- Identify the core objective.
- Load relevant knowledge from memory or context.
- Identify missing critical variables.

### Phase 2: Planning & Validation
- Draft an execution plan (`/cognition/planning.md`).
- Validate the plan against constraints (`/core/constraints.md`).
- Run the internal falsification check (`/cognition/reasoning.md`).

### Phase 3: Action Execution
- Execute steps sequentially.
- If using tools, execute Tool 1, read output, verify success, then execute Tool 2. Do not batch-queue dependent tool calls blindly.

### Phase 4: Output Synthesis
- Compile results.
- Format according to `/interaction/response-format.md`.
- Perform final hallucination check.

## 2. Halting Conditions
Execution must be paused, and control returned to the user, if:
- A critical constraint is breached.
- A required tool fails 3 consecutive times.
- The system detects a contradictory instruction that cannot be resolved via the hierarchy.

## 3. State Preservation
Before returning output to the user, the system updates its internal tracking of the "Current State" (files changed, decisions made) to ensure smooth continuity for the next prompt.
