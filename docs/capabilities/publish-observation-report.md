# Publish Observation Report

## Purpose

Describe the organizational responsibility for publishing reporter-confirmed Observation Reports as organizational working information.

Publication represents the transition from a proposed Observation Report to published working information available for downstream organizational review.

This capability begins after an Observation Report has been confirmed through Review Observation Report.

---

## Audience

- Staff
- Administrators
- Architects
- Developers

---

# Business Goal

Ensure reporter-confirmed information becomes available as organizational working information, prevent unauthorized publication, and maintain traceability for each published Observation Report.

---

# Actors

## Reporter

Provides the confirmation required before Observation publication may proceed.

## Publishing Process

Carries out the organizational responsibility for making the confirmed Observation Report available as working information.

The Publishing Process represents an organizational responsibility rather than a user.

---

# Preconditions

- An Observation Report exists.
- The Observation Report has been confirmed by the reporter.
- Publication has not already completed.
- Information required for publication is available.

---

# Trigger

This capability begins when a reporter-confirmed Observation Report is ready for publication.

---

# Business Flow

1. Publication is initiated.
2. Publication prerequisites are verified.
3. The confirmed Observation Report is published as organizational working information.
4. The publication outcome is recorded.
5. The Observation Report reflects its publication status.

---

# Business Rules

- Only reporter-confirmed Observation Reports may be published.
- Publication creates organizational working information, not an Intake or an official animal record.
- Publication outcomes are auditable.
- Supporting documents remain associated with the originating Observation Report.
- Publication should avoid duplicating the published Observation Report.

---

# Business Artifacts

## Primary

- Observation Report

## Supporting

- Animal Observation
- Publication Result

---

# Business Services

The following Business Service participates directly in this capability:

- Publish Observation Report

Review Observation Report is the upstream capability that provides the required reporter confirmation.

---

# Platform Services

The following established Platform Services support this capability:

- Configuration Service
- ID Generation Service

The following Platform Service is architecturally accepted but not implemented:

- Document Service

---

# Integration Services

This capability communicates with the current publication destination through an Integration Service.

The current implementation publishes to Excel for intermediate persistence and visualization. Excel is not the authoritative animal system of record, and the Business Service remains independent of that implementation mechanism.

---

# User Experiences

Publication occurs within the same user interaction in which the reporter captures, reviews, and confirms the Observation Report.

User Experiences may include:

- Conversational experience
- Administrative interface
- Future operational dashboards

User Experiences may initiate or present publication activity but do not implement publication rules.

---

# Validation

Business validation confirms that:

- The Observation Report has been confirmed by the reporter.
- Information required for publication is present.
- The Observation Report is eligible for publication.
- Publication has not already completed.

---

# Error Conditions

Business-level error conditions include:

- The Observation Report has not been confirmed by the reporter.
- Required information is missing.
- Publication cannot be completed.
- The organizational working information cannot be published.

---

# Human Review Requirements

This capability relies on prior reporter confirmation through Review Observation Report and does not replace that review.

Publication does not replace the later human organizational review that may determine whether the Observation Report should proceed toward Intake.

---

# Security Considerations

- Publication should be limited to authorized organizational operations.
- Publication activity and outcomes should remain auditable.
- The integrity of published organizational working information should be protected.
- Traceability to the originating Observation Report should be preserved.

---

# Observability

The organization should be able to determine:

- The publication history of an Observation Report.
- The current publication status.
- Timestamps associated with publication activity.
- The outcome of each publication attempt.

---

# Future Enhancements

Future considerations may include:

- Multiple destination systems
- Publication retries
- Partial publication handling
- Publication notifications

These items represent possible evolution and do not establish new architectural decisions.

---

# Related ADRs

- ADR-001 — Platform-First Architecture
- ADR-002 — Reusable Business Services
- ADR-003 — Dedicated GraphQL Integration Layer
- ADR-004 — Observation-First Business Model
- ADR-005 — Reusable Document Service

---

# Related Diagrams

Anticipated diagrams include:

- Observation Lifecycle
- Publication Workflow
- Observation State Diagram
