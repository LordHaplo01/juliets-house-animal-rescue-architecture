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

# Architectural Consistency

- Architecture diagrams should remain consistent with the Architecture document.
- When architectural layers or terminology change, affected diagrams should be updated alongside the supporting documentation.
- Diagram terminology should be sourced from the Glossary whenever practical.

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

Describe the major Business Services and Platform Services within a container and their relationships.

Audience

- Developers

Examples

Business Services

- Capture Field Observation
- Publish Observation Report
- Update Animal
- Knowledge Search

Platform Services

- Document Service
- Notification Service
- Configuration Service

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
- Platform Services
- Integration Services
- External Systems

---

# Sequence Diagrams

Sequence diagrams describe runtime interactions.

Examples

- AI → Business Service
- Business Service → Platform Service
- Business Service → Integration Service
- Integration Service → External System

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

NN-descriptive-name.md

Examples

02-observation-capability-map.md

03-observation-workflow.md

04-observation-state-diagram.md

05-observation-sequence.md

README.md is the sole authoritative location for the C4 System Context diagram. Do not create a standalone duplicate.

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
