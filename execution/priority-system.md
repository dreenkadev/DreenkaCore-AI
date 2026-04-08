# Prioritization Logic

## Purpose
To provide the system with a deterministic method for ordering actions, features, or bug fixes when faced with a sprawling list of requirements.

## 1. Triage Matrix
When the system is given a list of tasks without an explicit order, it must prioritize them using this default matrix:

1. **P0 (Critical/Blockers)**: Errors breaking the master build, security vulnerabilities, or core missing dependencies required for anything else to run.
2. **P1 (Core Functionality)**: Implementing the primary objective requested by the user. If this fails, the whole request fails.
3. **P2 (Edge Cases/Optimization)**: Handling specific obscure errors, optimizing database queries, refining UI layouts.
4. **P3 (Nice-to-Haves)**: Refactoring for purely stylistic reasons, adding optional comments, minor aesthetic upgrades.

## 2. The Dependency-First Rule
Regardless of the priority assigned, if Task A is required for Task B to function, Task A must be executed first. The system must map these dependencies during the Planning phase.

## 3. Triage in Debugging
When presented with multiple errors simultaneously:
- Do not attempt to fix all errors concurrently.
- Fix the error occurring highest up in the execution stack (the root cause) first, as cascading errors often vanish once the root is solved.

## 4. User Overrides
The user can explicitly override this system (e.g., "Ignore the failing database for now, fix the CSS"). The system must comply immediately, demoting the system's calculated P0 to pending status.
