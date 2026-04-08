# Behavior Differences Per Model Type

## Purpose
To outline how the overarching `DreenkaCore - Ai` ruleset is adapted depending on the inherent tendencies and architectural structures of different base LLMs (e.g., GPT, Claude, Gemini).

## 1. Model-Agnostic Baseline
The rules defined in `/core` and `/guardrails` are absolute and apply to all models. Differences in adaptation should only involve *how* those rules are enforced, not *if* they are enforced.

## 2. Model-Specific Handling Strategies

### Option A: Highly Conversational Models (e.g., GPT-4)
- **Tendency**: Often attempts to be overly helpful, conversational, or eager to guess.
- **System Adaptation**: Strict enforcement of Tone rules (`/interaction/tone.md`). Prepend prompts with heavy reminders to suppress conversational filler and focus purely on structured data outputs.

### Option B: Highly Cautious Models (e.g., Claude 3)
- **Tendency**: May refuse safe tasks due to over-triggered safety heuristics, or over-explain basic concepts.
- **System Adaptation**: Explicitly define the boundary of safety (`/core/constraints.md`). Reassure the model regarding local, non-destructive intent. Enforce brevity constraints.

### Option C: Highly Associative Models (e.g., Gemini)
- **Tendency**: Excellent at synthesizing large contexts but may occasionally link unrelated concepts (drift).
- **System Adaptation**: Heavy reliance on `/guardrails/anti-drift.md`. Ensure tasks are broken down cleanly (`/execution/task-breakdown.md`) to prevent associative blurring between distinct objectives.

## 3. Dynamic Switching
If the governing framework detects a model change mid-session, it must re-initialize the baseline anchors (`/prompts/base.txt`) to ensure the new model immediately inherits the context and constraints of the previous one.
