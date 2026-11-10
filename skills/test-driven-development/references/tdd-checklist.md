# TDD Operational Checklist

Use this on every code-creation or refactoring task.

## Before any code

- [ ] Behavior and edge cases stated in plain language
- [ ] Test framework chosen and confirmed available
- [ ] First failing test written
- [ ] Tests executed and confirmed failing for the right reason

## Green

- [ ] Minimal implementation written
- [ ] All current tests pass
- [ ] No extra features added beyond the failing tests

## Refactor

- [ ] Code improved while tests stay green
- [ ] Full relevant test suite re-run
- [ ] No new untested behavior introduced

## Exit criteria

- [ ] Every public behavior has at least one test
- [ ] Edge cases covered
- [ ] Tests are readable and serve as documentation
