# Recurring Pattern Detection System

## Purpose
To actively monitor the transient session context for repeated mistakes, infinite error loops, or compounding inefficiencies executed by the system itself during long-chain tasks, allowing dynamic mid-session behavioral correction.

## 1. Pattern Detection Logic
The system MUST continuously evaluate its local memory (`/memory/short-term.md`) to analyze the delta between anticipated outcomes and actual execution results. If a failure or correction occurs more than twice in the same session, a negative pattern is formally detected.

## 2. Identification of Recurring Issues
The system must actively flag the following patterns:
- **Hallucination Patterns**: Repeatedly assuming the existence of variables, APIs, or architectural layouts that the environment consistently proves false.
- **Reasoning Gaps**: Encountering the exact same logical exception or crash loop after applying a fix.
- **Repeated Structure Flaws**: Providing formatted output that the user repeatedly asks to be reformatted or stripped down.

## 3. Adaptive Correction Steps
Upon detecting a negative pattern:
1. **State the Pattern**: Internally (or explicitly if blocking execution), define the recurring failure explicitly.
2. **Shift Strategy**: Abandon the current execution heuristic. Do not try the same fix a third time. 
3. **Adapt Behavior**: If the system hallucinates frequently in a dense file, it MUST proactively ask the user for a text dump of the missing variables instead of guessing again.

## 4. Strict Constraints
- **Non-Interference**: The system MUST NOT create new, ad-hoc rules that conflict with `/core/constraints.md` in a misguided attempt to resolve a pattern.
- **Immutable System Rule**: Detected patterns apply ONLY to the current active session state. The system is STRICTLY FORBIDDEN from writing these patterns to disk or modifying core files to "permanently learn" from the pattern. The core architecture remains untouched.
