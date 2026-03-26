---
paths:
  - "spec/**/*.rb"
---

# Testing Conventions

- TDD approach: RED (failing test) -> GREEN (minimal implementation) -> REFACTOR
- Use `subject { build(:entity) }` for validation specs
- Use `let!` for records that must exist before the test runs
- Use `let` (lazy) by default; `let!` only when needed for side effects
- One behavior per `it` block
- Use `context` blocks to group by scenario
- Use FactoryBot: `build` over `create` when persistence isn't needed
- Request specs (`spec/requests/`) over controller specs
- Test authentication AND authorization in request specs
- Use Shoulda Matchers for validations and associations
- Run `bundle exec rubocop -a` after writing specs
