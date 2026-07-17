# ADR-002

## Title

Reusable Business Services

## Status

Accepted

---

## Context

The Juliet's House Volunteer Platform provides reusable business capabilities that may be consumed by multiple user experiences.

Current and future consumers include:

- Conversational AI
- Scheduled automations
- Administrative applications
- Mobile applications
- Future integrations

Embedding business rules directly within individual user experiences would duplicate logic, increase maintenance effort, and create inconsistent behavior across the platform.

---

## Decision

Business capabilities will be implemented as reusable Business Services.

Current implementations may use workflow technology; however, the architectural concept is independent of any specific implementation platform.

User experiences are responsible for:

- Collecting information
- Understanding user intent
- Orchestrating Business Services
- Presenting results

Business Services are responsible for:

- Executing business rules
- Validating business data
- Coordinating business processes
- Invoking required integration services

Business logic shall not be embedded within AI prompts or user interface implementations.

---

## Consequences

### Benefits

- Single source of truth for business logic
- Consistent behavior across user experiences
- Reusable business capabilities
- Easier testing and validation
- Simplified AI prompts
- Simplified future integrations
- Clear separation of concerns

### Tradeoffs

- Additional orchestration between user experiences and business services
- Slight increase in implementation complexity
- Initial investment in defining reusable service boundaries

---

## Notes

Examples of Business Services include:

- Capture Field Observation
- Review Observation
- Publish Observation
- Update Animal
- Knowledge Search

The current implementation uses n8n workflows to realize these services, but the architectural decision remains valid regardless of the underlying workflow technology.