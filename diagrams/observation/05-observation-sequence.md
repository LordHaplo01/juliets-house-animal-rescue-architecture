# 05 - Observation Sequence

## Status

Draft

## Purpose

Illustrate the major runtime interactions involved in Observation Management from field capture through human review and publication.

## Audience

- Staff
- Architects
- Developers
- Future Maintainers

## Diagram

```mermaid
sequenceDiagram

    participant Volunteer
    participant UserExperience as User Experience
    participant Capture as Capture Field Observation
    participant DocumentService as Document Service
    participant StaffReviewer as Staff Reviewer
    participant Review as Review Observation Report
    participant Publish as Publish Observation Report
    participant IntegrationService as Integration Service
    participant SystemOfRecord as System of Record

    Volunteer->>UserExperience: Submit observation information
    UserExperience->>Capture: Invoke observation capture

    opt Supporting documents provided
        Capture->>DocumentService: Store supporting documents
        DocumentService-->>Capture: Return document references
    end

    Capture-->>UserExperience: Create Observation Report and make available for review

    StaffReviewer->>UserExperience: Open Observation Report for review
    UserExperience->>Review: Invoke observation review
    Review-->>UserExperience: Provide Observation Report for review
    StaffReviewer->>UserExperience: Provide review decision
    UserExperience->>Review: Submit review decision

    alt Approved
        Review->>Publish: Authorize progression to publication
        Publish->>IntegrationService: Publish approved information
        IntegrationService->>SystemOfRecord: Create or update official organizational record
        SystemOfRecord-->>IntegrationService: Return publication outcome
        IntegrationService-->>Publish: Return publication outcome
    else Rejected
        Review-->>UserExperience: Confirm rejected disposition
        UserExperience-->>StaffReviewer: Present rejected disposition
    end
```

## Notes

This diagram represents major runtime interactions across architectural responsibilities.

Business Services remain independent of the User Experience.

Supporting documents are managed through the reusable Document Service.

External-system communication occurs through Integration Services.

Human approval is required before publication.

Implementation-level workflow behavior is intentionally omitted.

## References

- [Architecture](../../docs/architecture.md)
- [Capture Field Observation](../../docs/capabilities/capture-field-observation.md)
- [Review Observation Report](../../docs/capabilities/review-observation-report.md)
- [Publish Observation Report](../../docs/capabilities/publish-observation-report.md)
- [ADR-002 — Reusable Business Services](../../docs/adr/002-reusable-business-services.md)
- [ADR-003 — Dedicated GraphQL Integration Layer](../../docs/adr/003-dedicated-graphQL-integration-layer.md)
- [ADR-004 — Observation-First Business Model](../../docs/adr/004-observation-first-business-model)
- [ADR-005 — Reusable Document Service](../../docs/adr/005-reusable-document-service.md)
