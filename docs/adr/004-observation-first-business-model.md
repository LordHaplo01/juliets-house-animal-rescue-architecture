# ADR-0004

## Title

Observation-First Business Model

## Status

Accepted

---

## Context

Initial platform planning assumed that the primary business process was the creation of animal intake records.

As stakeholder discussions continued, it became clear that this assumption did not accurately reflect Juliet's House's operational workflow.

Rescue activities typically begin with the collection of information in the field. Administrative processing occurs later after staff have had an opportunity to review, verify, and approve the information.

A single rescue activity may involve multiple animals, additional observations, photographs, or follow-up information before official organizational records are created.

Modeling the platform around official animal intake records would tightly couple field activities to administrative processes and reduce the platform's flexibility as organizational workflows evolve.

---

## Decision

The platform will adopt an Observation-First Business Model.

The primary business artifact within the platform is the **Observation Report**.

An Observation Report represents organizational working information captured during rescue activities.

Each Observation Report may contain one or more Animal Observations.

Reporter-confirmed Observation Reports are published as organizational working information.

Official animal records are created or updated only through a later Intake process after human organizational review and approval.

This business model separates field information capture from administrative record management while allowing both processes to evolve independently.

---

## Consequences

### Benefits

- Accurately reflects Juliet's House operational workflow
- Supports one-to-many relationships between rescue activities and observed animals
- Decouples field observations from administrative processing
- Simplifies mobile data capture
- Supports incremental information gathering
- Preserves human review before organizational records are published
- Provides flexibility for future workflow evolution

### Tradeoffs

- Introduces an additional business artifact
- Requires a separate downstream process before official animal records are created or updated
- Requires lifecycle management for Observation Reports

---

## Notes

This architectural decision establishes the Observation Report as the primary business artifact throughout the platform.

Future Business Services, workflows, integrations, and user experiences should operate on published Observation Reports as organizational working information rather than assuming immediate creation or modification of official organizational records.

External systems, including Pawlytics, remain the authoritative owners of official animal records.

Published Observation Reports remain organizational working information until a later human organizational review determines whether they should proceed toward Intake.
