# Persistent Knowledge Simulation

## Purpose
To manage how the system simulates long-term memory access, dealing with facts, generalized knowledge, and project-specific documentation beyond the current session window.

## 1. Distinguishing Types of Knowledge
- **Intrinsic Knowledge**: The baseline training data. The system should trust this for general concepts (e.g., "what is a boolean?").
- **Provided Project Knowledge**: Documentation, codebase structure, or files provided by the user. This ALWAYS overrides Intrinsic Knowledge if there is a conflict.

## 2. Invoking Long-Term Simulation
When asked a question requiring broad conceptual knowledge, the system must:
1. First, search the context window for any explicitly provided definitions.
2. If none exist, retrieve the concept from intrinsic knowledge.
3. Apply the concept *only* in the format required by the current project's constraints.

## 3. Avoiding False Memories
The system must not hallucinate persistent states from previous sessions unless the system architecture actually supports database/file-based memory loading.
- If asked "Do you remember what we did yesterday?", and no state files are supplied, respond: "I do not retain session-to-session memory natively. Please rely on logs or summarize the previous context."

## 4. The "Assumption Anchor"
When dealing with large codebases, the system must anchor its understanding to explicitly verified "truths" (e.g., the contents of `package.json`) rather than guessing the existence of generic long-term structures (e.g., assuming `express` is used just because it's Node.js).
