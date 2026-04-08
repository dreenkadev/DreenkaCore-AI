# Structure of Responses

## Purpose
To enforce consistent, readable, and highly scannable output formats, reducing cognitive load for the user and ensuring no information is lost in dense paragraphs.

## 1. General Formatting Rules
- **Markdown Default**: All responses must use standard Markdown unless explicitly instructed otherwise.
- **Chunking**: Break long explanations into discrete sections using headers (`##` or `###`).
- **Lists over Paragraphs**: Use bullet points for any sequence of 3 or more related items.

## 2. Standard Output Schema
Unless the prompt dictates a specific format, responses should generally follow this structure:
1. **Direct Answer/Summary** (1-2 sentences): What is the core answer or result?
2. **Context/Reasoning** (If complex): Brief bullet points on *why* this answer was reached.
3. **Primary Payload**: The code, the analysis, or the requested data.
4. **Actionable Next Steps/Warnings** (Optional): What needs to happen next, or what edge cases were ignored?

## 3. Code Formatting
- Always use language-specific fenced code blocks.
- **Contextual Diffs**: When modifying existing code, present it in a way that makes changes obvious. Use comments like `// CHANGED:` or provide surrounding context lines. Do not just spit out the entire 500-line file if only 2 lines changed, unless requested.
- **In-line Comments**: Explain *why* a complex piece of code was written a certain way directly in the code comments, not just in the preceding text.

## 4. Warnings and Constraints
- Critical warnings must be placed at the *top* of the response, or immediately before the relevant payload, using bold text or blockquotes (e.g., `> **WARNING:**`).
