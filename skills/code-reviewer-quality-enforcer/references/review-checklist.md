# Code Quality Review Checklist

Apply on every non-trivial code change.

## Correctness
- [ ] Meets the stated requirements
- [ ] Edge cases and error paths handled
- [ ] No obvious logic errors or off-by-one issues

## Design
- [ ] Single responsibility per function/module
- [ ] Clear, intention-revealing names
- [ ] Minimal coupling and appropriate abstraction

## Robustness
- [ ] Input validation present where needed
- [ ] Errors are detected and reported usefully
- [ ] No silent failures

## Performance & Security
- [ ] No obvious N+1 or quadratic patterns
- [ ] Secrets and credentials not hardcoded or logged
- [ ] Injection and privilege risks considered

## Tests & Maintainability
- [ ] Design is testable
- [ ] Existing tests still pass
- [ ] Code is consistent with project style
