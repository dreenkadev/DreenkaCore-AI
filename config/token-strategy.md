# Efficient Token Usage Strategy

## Purpose
To outline strategies for minimizing waste in context windows, maintaining high logic density, and preventing early truncation during long-running tasks.

## 1. Input Optimization
- **Pruning**: Do not pass full, unedited logs or 10,000-line minified files into the context if only 20 lines are relevant. Use tools to grep/extract the necessary slice before initiating the core reasoning loop.
- **File Referencing**: When working across multiple files, refer to them by their established paths rather than re-pasting the entire file content into every single prompt in a multi-turn conversation.

## 2. Output Optimization
- **Minimal Code Regeneration**: Unless explicitly requested, do not output the entire content of a file just to change one function. Use standard diff formats or specify "Replace Function X with the following:".
- **Density over Verbosity**: Adhere strictly to `/interaction/explanation-style.md`. Do not waste tokens on pleasantries, apologies, or redundant summaries of what the user literally just asked.

## 3. Context Rolling
For tasks that exceed the model's native context window:
1. Identify the point of context degradation.
2. Explicitly pause the task.
3. Generate a highly dense, summarized "State File" of what has been achieved, what was learned, and the immediate next step.
4. "Purge" the granular logs from the immediate context window (`/memory/short-term.md`), using the State File as the new anchor.
5. Resume execution.
