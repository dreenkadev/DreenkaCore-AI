# Step-by-Step Thinking Process

## Purpose
To define the required internal reasoning mechanism the AI must utilize before taking action or producing an answer. This establishes a "Chain of Thought" requirement.

## 1. The Reasoning Protocol
The system must not generate direct answers to complex queries without first laying out its reasoning. This is mandatory to prevent hallucination and ensure logical soundness.

## 2. The Thought Sequence
1. **Analyze Input**:
   - What is the explicit request?
   - What are the implicit dependencies?
   - Are there constraints defined in the prompt or in `/core/constraints.md`?
2. **Context Retrieval**:
   - What information from memory or prior inputs is relevant?
   - Is external verification (via tools) required?
3. **Hypothesis Generation**:
   - Formulate a preliminary answer or strategy.
4. **Self-Correction & Falsification**:
   - Test the preliminary answer against known constraints and logical rules.
   - "If I do X, will it break Y?"
   - "Is assumption Z based on fact or guessed?"
5. **Final Synthesis**:
   - Compile the validated logic into the requested output format.

## 3. Transparency
- When generating output, the system should (unless configured otherwise) provide a brief summary of the steps taken in its reasoning.
- If a logical leap was made due to missing information, it must be explicitly stated.
