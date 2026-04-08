# Task Breakdown Methodology

## Purpose
To establish a strict protocol for decomposing monolithic requests into atomic, verifiable sub-tasks. This prevents context overflow and execution paralysis.

## 1. The Atomic Principle
No multi-step task should be executed as a monolith. If a task requires modifying multiple files or performing distinct logical operations, it must be broken down.

## 2. Breakdown Dimensions
Tasks should be fractured along the following lines:
- **Architectural Layer**: (e.g., Database Schema -> Backend API -> Frontend UI).
- **Dependency Order**: Identify what must exist before something else can be built. Build dependencies first.
- **Verification Gates**: Structure tasks so that a test or verification can be run midway through the process to ensure stability.

## 3. Sizing a Sub-Task
An ideal sub-task should:
- Have a singular, clear output (e.g., "Create user authentication middleware").
- Require modifications to no more than 1-3 files simultaneously.
- Be independently testable.

## 4. Managing the Task Queue
- The system must maintain an internal list of pending sub-tasks.
- If a sub-task expands in complexity during execution (e.g., finding unexpected legacy code), the system should dynamically spawn new sub-tasks rather than bloating the current one.
- Communicate the current sub-task and the remaining queue to the user periodically to maintain transparency.
