# Review Observation Report

## Purpose

Describe the reporter's responsibility for reviewing and confirming a proposed Observation Report during the Capture Field Observation interaction.

The reporter determines whether the proposed Observation Report:

- Accurately represents the information provided
- Requires correction before publication
- Is ready to be confirmed for publication as organizational working information

This capability begins after Capture Field Observation structures the proposed Observation Report and ends when the reporter confirms it or requests corrections.

---

## Audience

- Volunteers
- Staff
- Architects
- Developers

---

# Business Goal

Ensure the proposed Observation Report accurately represents the reporter's information, correct errors before publication, and preserve human confirmation within the implemented Observation interaction.

---

# Actors

## Reporter

Reviews the proposed Observation Report and its supporting evidence and either confirms the information or requests corrections.

The reporter may be a volunteer or staff member.

---

# Preconditions

- An Observation Report exists.
- The proposed Observation Report has been structured through Capture Field Observation.
- Supporting documents are available when they are associated with the Observation Report.
- The reporter has not yet confirmed the proposed Observation Report.

---

# Trigger

This capability begins when a proposed Observation Report becomes available to the reporter for review.

---

# Business Flow

1. The reporter reviews the proposed Observation Report.
2. The reporter evaluates the captured information and supporting documents.
3. The reporter requests corrections when information is inaccurate or incomplete, when required.
4. The reporter confirms the proposed Observation Report when it accurately represents the information provided.
5. The confirmed Observation Report may proceed to Publish Observation Report.

---

# Business Rules

- Reporter review and confirmation are mandatory before Observation publication.
- Reporter confirmation is auditable.
- Confirmation precedes publication as organizational working information.
- Reporter confirmation does not approve an Intake or an official animal record.
- Supporting documents remain associated with the Observation Report.

---

# Business Artifacts

## Primary

- Observation Report

## Supporting

- Animal Observation
- Supporting Documents
- Reporter Confirmation

---

# Business Services

The following Business Service participates directly in this capability:

- Review Observation Report

Capture Field Observation is the upstream capability that structures the proposed Observation Report.

---

# Platform Services

The following established Platform Service supports this capability:

- Configuration Service

The following Platform Service is architecturally accepted but not implemented:

- Document Service

---

# Integration Services

No Integration Services are required for reporter review and confirmation.

Following confirmation, Publish Observation Report makes the Observation Report available as organizational working information.

---

# User Experiences

This capability may be performed through user experiences including:

- Conversational experience
- Administrative interface
- Future mobile experience

User Experiences support reporter review and confirmation but do not implement the governing business rules.

---

# Validation

The reporter validates that:

- Required observation information is present.
- The Observation Report and its Animal Observations accurately represent the information provided.
- Supporting documents are available and associated with the correct Observation Report.
- The captured information is ready for confirmation or requires correction.

---

# Error Conditions

Business-level error conditions include:

- The Observation Report is unavailable.
- Required information is missing.
- Supporting documents associated with the Observation Report are unavailable.
- Reporter confirmation cannot be completed.

---

# Human Review Requirements

This capability embodies reporter review and confirmation within the implemented Observation interaction.

It does not replace the later human organizational review required before a published Observation Report may proceed toward Intake or an official organizational record.

---

# Security Considerations

- Access should be limited to the reporter and other authorized users.
- Reporter actions and confirmation should remain auditable.
- Observation Reports and supporting documents should be protected throughout review.

---

# Observability

The organization should be able to determine:

- The reporter review history of an Observation Report.
- Corrections requested by the reporter.
- The current confirmation status.
- Timestamps associated with reporter actions and confirmation.

---

# Future Enhancements

Future considerations may include:

- Clarification requests

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

- Observation Lifecycle
- Review Workflow
- Observation State Diagram
