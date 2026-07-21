# Contributing

Thank you for your interest in contributing to the Juliet's House Volunteer Platform.

This repository follows an **architecture-first** development approach. Documentation and architecture are first-class engineering artifacts and serve as the authoritative reference for the platform.

The goal is not simply to add functionality, but to ensure the platform remains maintainable, extensible, portable, and understandable over time.

---

# Guiding Principles

Contributors should strive to:

- Follow established enterprise architecture practices.
- Preserve consistency with existing architectural decisions.
- Understand the business problem before designing a solution.
- Prefer reusable Business Services over duplicated logic.
- Keep business logic separate from infrastructure and integrations.
- Favor maintainability over short-term convenience.
- Design for portability and minimize vendor lock-in where practical.
- Prefer simple, atomic, and loosely coupled workflows.
- Use AI to augment people rather than replace human judgment.
- Require human review before externally modifying organizational data.
- Document significant architectural decisions.

---

# Architecture-First Change Process

Significant changes should progress through the following stages.

## 1. Discovery

Understand the stakeholder need and the current business process before proposing a technical solution.

Discovery should identify:

- The problem being experienced
- The people involved
- The current process
- Existing constraints
- Operational variations
- Assumptions requiring validation

The initial request should not automatically be treated as the correct solution definition.

## 2. Business Analysis

Determine the underlying business capability rather than designing only for the immediate example.

Analysis should identify:

- The Business Capability
- Business actors
- Primary business artifacts
- Artifact lifecycles
- Business rules
- Human review or approval requirements
- Opportunities for reuse

For example, a request involving one operational activity may reveal a reusable capability that supports multiple activities.

## 3. Architecture Review

Evaluate how the proposed capability fits within the existing platform architecture.

The review should determine:

- Whether a new Business Capability is required
- Whether new or changed Business Services are required
- Whether a new or shared Platform Service should be introduced
- Whether new workflows are required
- Whether an Integration Service is required
- Whether existing services can be reused
- Whether an ADR is required
- Which architecture documents must be updated
- Whether the proposal conflicts with an existing architectural decision

Architectural impacts should be understood before implementation begins.

## 4. Documentation

Accepted architectural changes should be documented before implementation whenever practical.

Depending on the change, this may include updates to:

- Vision
- Architecture
- Roadmap
- Assumptions
- Glossary
- ADRs
- Diagrams
- Solution design documentation

Documentation must clearly distinguish between:

- Implemented capabilities
- Architecturally accepted but not yet implemented capabilities
- Planned capabilities
- Ideas still under consideration

The architecture repository documents accepted architecture. Unapproved ideas should remain in discussions, proposals, or the backlog until a decision is made.

## 5. Solution Design

After the architectural direction is accepted, define the implementation-level design.

Solution design may include:

- User experience
- Business Service contracts
- Workflow behavior
- Data models
- APIs
- Integration behavior
- Authentication and authorization
- Validation
- Error handling
- Observability
- Deployment considerations
- Testing strategy

Implementation technologies should support the architecture rather than define it.

## 6. Implementation

Implementation should begin only after the change has been sufficiently understood and designed.

Contributors should:

- Preserve separation of concerns.
- Keep workflows atomic and loosely coupled.
- Avoid duplicating business logic.
- Use Business Services as reusable business capability boundaries.
- Implement shared technical functionality within Platform Services.
- Isolate external-system behavior within Integration Services.
- Preserve mandatory human-review controls.
- Implement appropriate logging, monitoring, and error handling.
- Keep implementation aligned with the approved documentation.

## 7. Validation

Completed functionality should be validated with the appropriate stakeholders.

Validation should confirm:

- The capability solves the identified business problem.
- The implementation reflects the documented design.
- Human-review and approval requirements are preserved.
- Operational variations are supported.
- Documentation remains accurate.
- New assumptions or architectural implications have been captured.

Stakeholder feedback may lead to iterative refinement of both the implementation and the architecture.

---

# Before Making Changes

Before implementing significant functionality:

1. Review the Vision and Architecture documents.
2. Review applicable Architecture Decision Records.
3. Review relevant diagrams, assumptions, roadmap items, and glossary terms.
4. Understand whether the capability is implemented, accepted, planned, or still under consideration.
5. Identify architectural and documentation impacts.
6. Confirm that the proposed change does not duplicate an existing Business Service.
7. Resolve material assumptions before beginning implementation.

Do not silently introduce architectural decisions through implementation.

---

# Architectural Decision Records

Significant architectural decisions should be captured as an ADR.

Examples include:

- New architectural principles
- New platform-wide business models
- Major capability boundaries
- Integration strategies
- Architectural patterns
- Changes to deployment strategy
- Major technology selections with long-term architectural consequences
- Changes to previously accepted architectural decisions

An ADR records an accepted decision and its consequences.

Ideas under consideration should not be recorded as accepted ADRs.

Minor implementation details generally do not require an ADR.

---

# Documentation

Documentation is part of the engineering deliverable.

When appropriate, update:

- Vision
- Architecture
- Roadmap
- Assumptions
- Glossary
- Diagram Standards
- ADRs
- Diagrams
- Solution design documentation

Documentation must remain consistent with both the accepted architecture and the implementation state.

A planned or architecturally accepted capability must not be described as currently available unless it has been implemented and validated.

---

# Diagram Standards

Architecture diagrams should follow the standards defined in:

`docs/diagram-standards.md`

Where appropriate, diagrams should follow the C4 Model.

Each diagram should include:

- Purpose
- Audience
- Diagram
- Notes
- References

Context diagrams should use business language. Implementation details should be reserved for lower-level diagrams.

Portable Mermaid syntax should be preferred over renderer-specific features.

---

# Engineering Philosophy

The platform is designed around:

- Architecture-first delivery
- Human-centered AI
- Reusable Business Services
- Reusable Platform Services
- Atomic workflows
- Separation of concerns
- Loose coupling
- High cohesion
- API-first integrations
- Human review before external data modification
- Deployment portability
- Documentation as an authoritative engineering artifact
- Continuous architectural refinement

Contributors are encouraged to improve the platform while preserving these principles.

---

# Questions and Discussion

When proposing architectural changes:

- Explain the business problem.
- Identify assumptions.
- Explain the proposed architectural impact.
- Discuss benefits and tradeoffs.
- Check consistency with existing ADRs.
- Avoid unnecessary complexity.
- Prefer iterative refinement over complete redesign.
- Identify which documents require updates.
- Distinguish implemented functionality from planned functionality.

Architecture is expected to evolve as organizational needs become better understood.

Thoughtful challenge and discussion are encouraged.
