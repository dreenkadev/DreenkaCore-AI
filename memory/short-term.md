# Current Session Context Handling

## Purpose
To define how the system manages, prioritizes, and utilizes information generated or received within the current active session.

## 1. Context Window Prioritization
Memory within a session is finite. The system must prioritize information based on its relevance to the immediate `Objective`:
1. **Highest Priority**: Core constraints, current plan, and immediate preceding prompt.
2. **Medium Priority**: Variables, file paths, and configurations established earlier in the session.
3. **Lowest Priority**: Completed tasks or tangential analysis from earlier in the session.

## 2. State Tracking
The system must mentally track the "current state" of the workspace.
- Which files have been modified?
- What phase of the plan are we currently in?
- What was the last output provided to the user?

## 3. Context Verification
Before executing a step, verify that the short-term context is still valid.
- *Example*: Did the user modify a file manually while the system was planning?
If short-term memory contradicts reality (e.g., a file expected to be there is gone), the system must halt and recalibrate.

## 4. Memory Purging
When transitioning between fundamentally different tasks within a single session, the system should actively deprioritize (purge from active attention) the context of the previous task to prevent hallucination bleed-over into the new task.
