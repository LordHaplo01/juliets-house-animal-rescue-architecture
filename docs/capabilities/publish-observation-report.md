# Publish Observation Report

## Purpose

Describe the organizational responsibility for publishing approved Observation Reports to one or more official systems of record.

Publication represents the transition from a reviewed and approved Observation Report to one or more official organizational records.

This capability begins after an Observation Report has been approved through Review Observation Report.

---

## Audience

- Staff
- Administrators
- Architects
- Developers

---

# Business Goal

Ensure approved information becomes part of the organization's official records, preserve consistency between Observation Reports and systems of record, prevent unauthorized publication, and maintain traceability between each Observation Report and the resulting organizational records.

---

# Actors

## Staff Reviewer

Provides the human approval required before publication may proceed.

## Publishing Process

Carries out the organizational responsibility for creating or updating official organizational records from approved information.

The Publishing Process represents an organizational responsibility rather than a user.

---

# Preconditions

- An Observation Report exists.
- The Observation Report has been approved.
- Publication has not already completed.
- Information required for publication is available.

---

# Trigger

This capability begins when an approved Observation Report is ready for publication.

---

# Business Flow

1. Publication is initiated.
2. Publication prerequisites are verified.
3. Official organizational records are created or updated.
4. The publication outcome is recorded.
5. The Observation Report reflects its publication status.

---

# Business Rules

- Only approved Observation Reports may be published.
- Publication creates or updates official organizational records.
- Publication outcomes are auditable.
- Supporting documents remain associated with the originating Observation Report.
- Publication should avoid creating duplicate organizational records.

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

Review Observation Report is the upstream capability that provides the required human approval.

---

# Platform Services

The following Platform Services support this capability:

- Document Service
- Configuration Service
- ID Generation Service

---

# Integration Services

This capability communicates with one or more systems of record through Integration Services.

Integration Services encapsulate external communication while the Business Service remains responsible for publication rules and outcomes.

---

# User Experiences

Publication is generally initiated as part of organizational operations rather than through direct volunteer interaction.

User Experiences may include:

- Administrative review interface
- Future operational dashboards

User Experiences may initiate or present publication activity but do not implement publication rules.

---

# Validation

Business validation confirms that:

- The Observation Report has been approved.
- Information required for publication is present.
- The Observation Report is eligible for publication.
- Publication has not already completed.

---

# Error Conditions

Business-level error conditions include:

- The Observation Report has not been approved.
- Required information is missing.
- Publication cannot be completed.
- An official organizational record cannot be created or updated.

---

# Human Review Requirements

This capability relies on prior human approval through Review Observation Report and does not replace that review.

Publication cannot proceed without the required approval.

---

# Security Considerations

- Publication should be limited to authorized organizational operations.
- Publication activity and outcomes should remain auditable.
- The integrity of official organizational records should be protected throughout publication.
- Traceability between an Observation Report and resulting organizational records should be preserved.

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
