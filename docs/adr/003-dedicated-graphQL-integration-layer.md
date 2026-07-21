# ADR-0003

## Title

Dedicated GraphQL Integration Layer

## Status

Accepted

---

## Context

Multiple Business Services require access to Pawlytics.

Future platform capabilities requiring official animal record access include:

- Update Animal
- Official Animal Intake
- Adoption workflows
- Foster workflows
- Reporting
- Synchronization processes

Allowing each Business Service to communicate directly with the Pawlytics API would duplicate:

- Authentication
- GraphQL queries and mutations
- Validation
- Error handling
- Retry logic

Duplicated integration logic would increase maintenance effort and tightly couple Business Services to the implementation details of an external system.

---

## Decision

A dedicated GraphQL Integration Layer will encapsulate all communication with Pawlytics.

Business Services will invoke reusable Integration Services rather than constructing GraphQL requests directly.

The GraphQL Integration Layer is responsible for:

- Authentication
- Request construction
- Validation
- Error handling
- Retry behavior
- Future API compatibility

Business Services remain independent of Pawlytics implementation details.

Publish Observation Report does not use this Integration Layer to create official animal records. It publishes organizational working information for a later human review and Intake process.

---

## Consequences

### Benefits

- Centralized authentication
- Reusable GraphQL operations
- Consistent validation
- Consistent error handling
- Easier API upgrades
- Reduced duplication
- Loose coupling between business logic and external systems

### Tradeoffs

- One additional architectural layer
- Slight increase in implementation complexity
- Integration changes are centralized within a dedicated service

---

## Notes

This architectural decision applies to all future external GraphQL integrations, not solely Pawlytics.

By isolating third-party communication within a dedicated Integration Layer, Business Services remain portable, reusable, and independent of vendor-specific implementation details.
