# ADR-005: Reusable Document Service

## Status

Proposed

---

## Context

The Juliet's House Volunteer Platform allows volunteers to attach supporting documents, such as photographs and videos, while capturing field observations.

Initially these documents support Observation Reports, but future platform capabilities are expected to require document management as well, including:

- Official Intakes
- Foster Management
- Volunteer Management
- Adoption Records
- Knowledge Management
- Future organizational workflows

Managing documents independently within each Business Service would duplicate validation logic, storage logic, and future enhancements.

The platform requires a reusable architectural approach that separates document management from business-specific workflows.

---

## Decision

The platform will implement a reusable **Document Service** as a Platform Service.

Business Services requiring document management will consume the Document Service rather than implementing document handling themselves.

The Document Service is responsible for the technical management of documents.

Business Services remain responsible for determining when documents are required and how they relate to business artifacts.

---

## Responsibilities

The Document Service is responsible for:

- Validating supported file types
- Validating file size limits
- Persisting documents
- Generating storage references
- Returning document metadata
- Associating documents with business artifacts
- Abstracting physical storage implementation

The service does **not** implement business rules.

---

## Architectural Placement

```text
Experience Layer
        │
        ▼
AI Orchestration
        │
        ▼
Business Services
        │
        ▼
Document Service
        │
        ▼
Storage
```

The Document Service is a reusable Platform Service consumed by Business Services.

---

## Consequences

### Positive

- Eliminates duplicate document handling logic.
- Encourages reuse across multiple Business Services.
- Simplifies future storage migrations.
- Enables future document capabilities without changing Business Services.
- Improves maintainability through separation of concerns.

### Negative

- Introduces an additional architectural component.
- Adds one additional service invocation during document processing.

These tradeoffs are considered acceptable given the expected growth of the platform.

---

## Future Evolution

The Document Service may later support capabilities including:

- Virus scanning
- OCR
- Image analysis
- Thumbnail generation
- Metadata extraction
- Duplicate detection
- Versioning
- Retention policies
- Cloud storage providers
- Document lifecycle management

These capabilities may be added without changing Business Services.

---

## Alternatives Considered

### Store documents directly inside each Business Service

Rejected.

This duplicates technical responsibilities and increases maintenance effort.

---

### Integrate directly with cloud storage providers

Rejected.

Business Services should remain independent of storage technology.

Storage should remain an implementation detail managed by the Document Service.

---

## Related Documents

- Architecture
- ADR-002 – Reusable Business Services
- ADR-003 – Dedicated GraphQL Integration Layer
- ADR-004 – Observation-First Business Model
- Documentation Style Guide