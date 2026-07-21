# Capture Field Observation

## Purpose

Describe the business capability for structuring observations made by volunteers and staff during rescue activities as a proposed Observation Report.

This capability produces a proposed Observation Report for review and confirmation by the reporter.

---

## Audience

- Volunteers
- Staff
- Architects
- Developers

---

# Business Goal

Enable Juliet's House to capture accurate field observations at the point of discovery, reduce information loss, standardize observation information, preserve supporting evidence, and require reporter confirmation before publication.

---

# Actors

## Volunteer

Captures information observed during rescue activities.

## Staff

Captures information when acting as the reporter.

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
6. The proposed Observation Report is made available to the reporter for review and confirmation.
7. Confirmed Observation Reports may later be published through a separate capability.

---

# Business Rules

- One Observation Report may contain multiple Animal Observations.
- The Observation Report is the primary business artifact produced by this capability.
- Official organizational records are not created or modified during capture.
- Reporter review and confirmation are required before Observation publication.
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

- Review Observation Report
- Publish Observation Report

---

# Platform Services

The following established Platform Services support this capability:

- Configuration Service
- ID Generation Service

The following Platform Service is architecturally accepted but not implemented:

- Document Service

---

# Integration Services

No Integration Services are required during initial capture.

Communication with the current working-information destination occurs through Publish Observation Report.

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

Every proposed Observation Report requires review and confirmation by the reporter before it is published as organizational working information.

This reporter confirmation is distinct from the later organizational review that may determine whether a published Observation Report should proceed toward Intake.

---

# Security Considerations

- Access to Observation Reports should be limited to appropriate volunteers and staff.
- Supporting documents should be protected as part of the Observation Report.
- Creation, review, confirmation, and publication activities should remain auditable.

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
