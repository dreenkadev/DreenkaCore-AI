# System Version

## Purpose
To track the architectural iteration of the `DreenkaCore - Ai` framework, ensuring all instances of the AI know which ruleset they are operating under.

## 1. Current Version Core
- **Version**: 1.0.0
- **Codename**: Genesis Hardened
- **Status**: Stable

## 2. Versioning Logic
The system uses Semantic Versioning (SemVer) tailored to prompt infrastructure:
- **MAJOR (`1.x.x`)**: Overhaul of core constraints, fundamental shifts in cognitive routing, or breaking changes to how memory is handled.
- **MINOR (`x.1.x`)**: Addition of new guardrails, prompt templates, or configuration profiles that do not alter the baseline operating philosophy.
- **PATCH (`x.x.1`)**: Typo fixes in documentation, rephrasing of ambiguous rules, or minor adjustments to temperature profiles.

## 3. Backward Compatibility
If an older project explicitly references an earlier iteration (e.g., `v0.9`) in its context, the AI must adapt its logic to abide by the constraints as they existed in v0.9, disabling v1.0 features if they conflict.
