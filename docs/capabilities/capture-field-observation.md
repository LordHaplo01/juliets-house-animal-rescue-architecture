# Capture Field Observation

## Purpose

Describe the business capability for capturing observations made by volunteers and staff during rescue activities before those observations become official organizational records.

This capability produces Observation Reports for human review.

---

## Audience

- Volunteers
- Staff
- Architects
- Developers

---

# Business Goal

Enable Juliet's House to capture accurate field observations at the point of discovery, reduce information loss, standardize intake information, preserve supporting evidence, and require human review before publication.

---

# Actors

## Volunteer

Captures information observed during rescue activities.

## Staff Reviewer

Reviews captured information before it may proceed to publication.

Future user experiences may support additional organizational roles without changing this capability's business behavior.

---

# Preconditions

- A user has an observation to report.
- Sufficient information is available to begin capturing the observation.
- Supporting documents may be available.

---

# Trigger

This capability begins when:

- A volunteer observes one or more animals.
- A staff member records observation information received from another source.

---

# Business Flow

1. The observation is initiated.
2. Observation details are collected.
3. Supporting documents are associated with the observation.
4. An Observation Report is created.
5. The Observation Report is validated.
6. The Observation Report enters human review.
7. Approved observations may later be published through a separate capability.

---

# Business Rules

- One Observation Report may contain multiple Animal Observations.
- The Observation Report is the primary business artifact produced by this capability.
- Official organizational records are not created or modified directly during capture.
- Human review and approval are required before publication.
- Supporting documents remain associated with the Observation Report.

---

# Business Artifacts

## Primary

- Observation Report

## Supporting

- Animal Observation
- Supporting Documents

---

# Business Services

The following Business Service participates directly in this capability:

- Capture Field Observation

Additional Business Services participate in later lifecycle stages:

- Review Observation
- Publish Observation

---

# Platform Services

The following Platform Services support this capability:

- Document Service
- Configuration Service
- ID Generation Service

---

# Integration Services

No Integration Services are required during initial capture.

Communication with external systems occurs through later publication capabilities.

---

# User Experiences

This capability may be initiated through multiple user experiences, including:

- Conversational AI
- Future mobile application
- Future administrative application

User Experiences orchestrate this capability but do not implement its business rules.

---

# Validation

Business validation confirms that:

- Required observation information is present.
- The Observation Report and its Animal Observations have a valid business structure.
- Supporting documents are associated with the correct Observation Report.

---

# Error Conditions

Business-level error conditions include:

- Insufficient information to create an Observation Report.
- Invalid observation information.
- Missing required information.
- An Observation Report that cannot proceed to human review.

---

# Human Review Requirements

Every Observation Report requires human review and approval before publication to an external system of record.

Capture does not authorize the creation or modification of official organizational records.

---

# Security Considerations

- Access to Observation Reports should be limited to appropriate volunteers and staff.
- Supporting documents should be protected as part of the Observation Report.
- Creation, review, approval, and publication activities should remain auditable.

---

# Observability

The organization should be able to determine:

- When an Observation Report was created.
- The current review status.
- The current publication status.
- The audit history associated with the Observation Report.

---

# Future Enhancements

Future considerations may include:

- GPS assistance
- Offline capture
- Batch observations
- Additional evidence types

These items represent possible evolution and do not establish new architectural decisions.

---

# Related ADRs

- ADR-001 — Platform-First Architecture
- ADR-002 — Reusable Business Services
- ADR-004 — Observation-First Business Model
- ADR-005 — Reusable Document Service

---

# Related Diagrams

Anticipated diagrams include:

- Observation Workflow
- Observation Lifecycle
- Observation Sequence
