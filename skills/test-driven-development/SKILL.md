---
name: test-driven-development
description: Enforce strict Test-Driven Development (TDD) Red-Green-Refactor cycles when writing, refactoring, or extending code, APIs, tools, scripts, or software features. Use whenever building new functionality, fixing bugs with new tests, or improving existing code so that failing tests are written and verified before any implementation.
---

# Test-Driven Development

## Overview

Apply a disciplined Red-Green-Refactor workflow so that tests serve as the precise specification. Never write production code before a failing test exists for the behavior being added or changed.

## Core Rules

1. **Red first**: Write one or more failing tests that express the desired behavior and edge cases. Run them and confirm they fail for the correct reason.
2. **Green**: Write the minimal production code required to make the tests pass. Do not add extra features or polish.
3. **Refactor**: Improve structure, naming, and design while keeping all tests green. Re-run tests after every change.
4. Repeat for the next behavior.

## Instructions

### When this skill activates

- User asks to implement a function, module, API endpoint, CLI tool, class, or feature.
- User asks to refactor, improve, or extend existing code.
- User asks for a bug fix that requires new coverage.
- Any software-creation task where correctness matters.

### Step-by-step process

**Step 1 — Define the contract**
- State the public interface, inputs, outputs, and important edge cases in plain language.
- Choose the appropriate test framework for the language (pytest, vitest/jest, go test, etc.).

**Step 2 — Red phase**
- Write the smallest set of tests that capture the desired behavior.
- Run the tests. Confirm they fail (and that the failure is the expected one, not a setup error).
- Do not write any production code yet.

**Step 3 — Green phase**
- Implement only enough code to make the current tests pass.
- Prefer simple, obvious solutions over clever ones.
- Re-run tests until they are green.

**Step 4 — Refactor phase**
- Clean up the code (extract functions, improve names, remove duplication) while keeping tests green.
- Re-run the full relevant test suite after each meaningful change.

**Step 5 — Expand**
- Move to the next behavior or edge case and repeat the cycle.
- Never add untested behavior.

### Additional constraints

- Prefer focused unit tests over broad integration tests when defining new behavior.
- Treat the tests as the living specification. If a requirement is not expressed in a test, it does not exist for the agent.
- When the user provides existing code, first write characterization tests that capture current behavior before changing anything.
- If a test is hard to write, redesign the interface so it becomes testable.

## References

- See `references/tdd-checklist.md` for a short operational checklist.
- See `references/common-pitfalls.md` for frequent mistakes to avoid.
