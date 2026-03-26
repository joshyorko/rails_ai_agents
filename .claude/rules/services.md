---
paths:
  - "app/services/**/*.rb"
  - "spec/services/**/*.rb"
---

# Service Object Conventions

- Single public method: `#call`
- Class-level shortcut: `self.call(...)` delegates to `new(...).call`
- Always return a Result object (`Data.define(:success, :data, :error)`)
- Never raise exceptions for business logic failures; use `failure(message)`
- Namespace by domain: `Entities::CreateService`, `Orders::CancelService`
- Inject dependencies via constructor for testability
- Wrap multi-model operations in `ActiveRecord::Base.transaction`
- Test both success and failure paths with `subject(:result)`
- Base class in `app/services/application_service.rb`
