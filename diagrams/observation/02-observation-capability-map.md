# 02 - Observation Capability Map

## Status

Draft

## Purpose

Show the business capabilities that make up Observation Management.

## Audience

- Business Analysts
- Architects
- Developers
- Future Maintainers

## Diagram

```mermaid
flowchart TB

    ObservationManagement["Observation Management"]

    Capture["Capture Field Observation"]
    Review["Review Observation Report"]
    Publish["Publish Observation Report"]

    ObservationManagement --> Capture
    ObservationManagement --> Review
    ObservationManagement --> Publish
```

## Notes

This diagram represents business capability decomposition, not process order.

The three capabilities are independently documented.

Workflow, state, and runtime interactions are documented separately.

Published Observation Reports remain organizational working information until a later human organizational review determines whether they should proceed toward Intake.

## References

- [Capture Field Observation](../../docs/capabilities/capture-field-observation.md)
- [Review Observation Report](../../docs/capabilities/review-observation-report.md)
- [Publish Observation Report](../../docs/capabilities/publish-observation-report.md)
- [ADR-004 — Observation-First Business Model](../../docs/adr/004-observation-first-business-model.md)
