---
name: code-reviewer-quality-enforcer
description: Automatically perform a structured quality review pass over generated or existing code, checking single-responsibility violations, logic flaws, performance issues, naming, error handling, and security, then fix the problems before considering the work complete. Use after writing code, before shipping, or when the user asks for a review or quality pass.
---

# Code Reviewer & Quality Enforcer

## Overview

Run a disciplined, multi-axis review on any code the agent has just produced or is asked to improve. Identify defects, then correct them. Do not present incomplete or low-quality code as finished.

## Review Axes

Examine the code against these dimensions in order:

1. **Correctness** — Does it do what was requested? Edge cases handled?
2. **Single Responsibility** — Does each function/module do one thing?
3. **Naming & Clarity** — Are names precise and intention-revealing?
4. **Error Handling** — Are failures detected, reported, and recoverable where appropriate?
5. **Performance** — Obvious N+1 queries, unnecessary loops, quadratic behavior, or excessive allocations?
6. **Security** — Input validation, injection risks, secret handling, privilege issues?
7. **Testability** — Is the design easy to unit-test?
8. **Style & Consistency** — Matches project conventions and language idioms?

## Instructions

### When this skill activates

- Immediately after generating non-trivial code.
- When the user asks for a review, quality pass, cleanup, or “make it production-ready”.
- Before declaring any implementation complete.

### Process

1. **Read the full relevant code** (new and surrounding context).
2. **Walk each review axis** and list concrete findings with location references.
3. **Prioritize** by severity (correctness and security first).
4. **Fix** every high- and medium-severity issue in place.
5. **Re-verify** by re-reading the changed code and, when possible, re-running tests.
6. **Report** a short summary of what was found and fixed (or that the code already met the standard).

### Rules

- Never leave known correctness or security problems unaddressed.
- Prefer small, focused fixes over large rewrites unless the design is fundamentally broken.
- Preserve existing tests; add characterization or regression tests when changing behavior.
- If a problem requires architectural change, state it clearly and propose the minimal viable improvement.
- Do not invent requirements that were not requested.

## References

- See `references/review-checklist.md` for a compact checklist to apply on every pass.
