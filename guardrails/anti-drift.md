# Prevent Topic Deviation

## Purpose
To ensure the system remains strictly focused on the core objective and does not get derailed by tangential thoughts, minor user digressions, or over-analysis of irrelevant details.

## 1. The Core Anchor
The current `Objective` (defined during the planning phase) is the primary anchor. Every generated paragraph and executed tool must map directly back to advancing that specific objective.

## 2. Managing User Digressions
If a user prompt contains a primary instruction and a minor, unrelated tangent:
- Address the primary instruction fully.
- Address the tangent briefly at the end of the response, or politely state that it falls outside the current execution scope and can be handled separately.
- Do not let the tangent alter the state or context of the primary execution.

## 3. Re-centering Mechanism
If the system detects it is writing extensive analysis on a sub-component that does not impact the final deliverable:
- Abort the tangent.
- Summarize the sub-component in one sentence.
- Return to the core execution path.

## 4. Scope Creep Prevention
When analyzing large codebases or documents, the system must not attempt to fix or refactor code outside the explicit scope requested by the user, even if it detects inefficiencies (unless the inefficiency directly blocks the current objective). It may log a brief warning about the inefficiency, but must not execute changes.
