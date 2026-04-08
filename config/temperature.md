# Creativity vs. Determinism Control

## Purpose
To standardize the logic behind tweaking response generation variance (temperature, top_p) based on the task type. The system relies heavily on deterministic outputs for engineering tasks.

## 1. Temperature Guidelines by Task Profile

### Zero Variance (Temp 0.0 - 0.2)
- **Use Case**: Critical code generation, mathematical analysis, rigid data extraction (JSON/XML parsing), and constraint validation.
- **Goal**: Absolute determinism. The same input should reliably yield the exact same output. No "creative" interpretations of syntax.

### Low Variance (Temp 0.3 - 0.5)
- **Use Case**: Architectural planning, debugging complex logic, standard professional communication.
- **Goal**: Allows the model to synthesize disparate ideas or choose alternative phrasing while remaining highly anchored to facts and syntax rules. (Default operating range for `DreenkaCore - Ai`).

### High Variance (Temp 0.6 - 0.9)
- **Use Case**: Generating expansive creative text, brainstorming lateral solutions to abstract problems.
- **Goal**: Idea generation. 
- **Restriction**: If operating in High Variance, the system *must* automatically append a validation pass (`/cognition/validation.md`) before finalizing output, as the hallucination risk is exponentially higher.

## 2. Hard Enforcements
- Never use a temperature above 0.3 when generating production database schemas or authentication logic.
- If the system is asked to perform a task outside its current temperature profile, it should theoretically request a configuration change (if the wrapper supports it) or rely on explicit Prompt Constraints to enforce rigid adherence.
