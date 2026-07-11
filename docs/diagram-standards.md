# Diagram Standards

This document defines the diagramming standards used throughout the Juliet's House Animal Rescue Architecture repository.

The goal is to ensure every diagram is consistent, easy to understand, and serves a clear architectural purpose.

---

# General Principles

- Every diagram answers one primary question.
- Each diagram should have a clearly defined audience.
- Use business language whenever possible.
- Avoid implementation details unless the diagram specifically requires them.
- Prefer simplicity over completeness.
- Diagrams should evolve alongside implementation.

---

# C4 Model

The repository follows the C4 Model where appropriate.

## Level 1 — System Context

Purpose

Describe the Juliet's House Volunteer Platform as a single system and show how it interacts with users and external systems.

Audience

- Executive Leadership
- Volunteers
- Staff
- Sponsors
- New Developers

Rules

- Show only the platform as a single system.
- Show actors as roles, not individuals.
- Show external systems only.
- Do not show implementation details.

Examples

✔ Pawlytics

✔ Google Workspace

✔ Mailchimp

✘ n8n

✘ Ollama

✘ Qdrant

✘ Docker

---

## Level 2 — Container Diagram

Purpose

Describe the major runtime components that make up the platform.

Audience

- Developers
- Architects

Rules

- Show deployable applications.
- Technology names are appropriate.
- Show communication paths.

Examples

✔ AI Assistant

✔ n8n

✔ GraphQL Integration

✔ Knowledge Base

---

## Level 3 — Component Diagram

Purpose

Describe the major business capabilities within each container.

Audience

- Developers

Examples

- Create Intake
- Update Animal
- Knowledge Search
- Notification Service

---

## Level 4

Implementation documentation.

The repository will primarily reference implementation through workflows and source code rather than traditional C4 Level 4 diagrams.

---

# Workflow Diagrams

Workflow diagrams document business processes.

Use workflow diagrams when describing:

- Animal Intake
- Update Existing Animal
- Knowledge Search
- Adoption
- Foster Management

Rules

- Use business terminology.
- One workflow per diagram.
- Show decision points.
- Show user interactions.

---

# Swimlane Diagrams

Swimlane diagrams describe responsibilities.

Preferred swimlanes include:

- Volunteer
- Staff
- Experience Layer
- Business Services
- Integration Services
- External Systems

---

# Sequence Diagrams

Sequence diagrams describe runtime interactions.

Examples

- AI → Business Service
- Business Service → GraphQL
- GraphQL → Pawlytics

---

# Deployment Diagrams

Deployment diagrams describe infrastructure.

These diagrams may include:

- Cloud services
- Self-hosted infrastructure
- Containers
- Reverse proxies
- Networking

Deployment diagrams should remain independent of business workflows.

---

# Naming Standards

Diagram files should follow:

NN-descriptive-name.mmd

Examples

01-system-context.mmd

02-container-platform.mmd

03-component-business-services.mmd

04-workflow-create-intake.mmd

---

# Status

Diagrams should indicate their current maturity.

Draft

Proposed

Approved

Implemented

Deprecated

---

# Revision Philosophy

Architecture documentation is considered a living artifact.

Documentation should evolve with implementation and remain the authoritative reference for platform design.