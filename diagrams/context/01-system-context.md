# 01 - System Context

## Purpose

Describe the Juliet's House Animal Rescue Volunteer Platform as a single system and illustrate its relationships with users and external systems.

## Audience

- Leadership
- Volunteers
- Staff
- Developers

## Diagram

```mermaid
flowchart LR

%% Actors
Volunteer["👤 Volunteer"]
Staff["👥 Staff"]
Admin["🛠 Platform Administrator"]

%% Platform
Platform["🏠 Juliet's House Animal Rescue Volunteer Platform"]

%% External Systems
Pawlytics["🐾 Pawlytics"]
Google["📄 Google Workspace"]
Mailchimp["✉️ Mailchimp"]

%% Relationships
Volunteer -->|Uses| Platform
Staff -->|Uses| Platform
Admin -->|Maintains| Platform

Platform -->|Reads / Writes Animal Records| Pawlytics
Platform -->|Reads Documentation| Google
Platform -.->|Future Communications| Mailchimp

%% Styling
classDef actor fill:#d6ecff,stroke:#3b82f6,color:#000,stroke-width:2px;
classDef platform fill:#dff6dd,stroke:#2e7d32,color:#000,stroke-width:3px;
classDef external fill:#fff3d6,stroke:#d97706,color:#000,stroke-width:2px;

class Volunteer,Staff,Admin actor;
class Platform platform;
class Pawlytics,Google,Mailchimp external;
```

## Notes

This diagram represents the highest-level view of the platform.

Implementation details such as n8n, Ollama, Qdrant, Docker, GraphQL, hosting infrastructure, and workflow orchestration are intentionally omitted. Those belong in lower-level architecture diagrams.

The platform is shown as a single system because this diagram focuses on business interactions rather than technical implementation.

## References

- Vision
- Architecture
- ADR-001
## Notes

This diagram represents the highest-level view of the platform.

Implementation details such as n8n, Ollama, Qdrant, Docker, GraphQL, and hosting infrastructure are intentionally omitted. Those details belong in lower-level C4 diagrams.

The Platform is shown as a single system because this diagram focuses on business interactions rather than technical implementation.

## References

- Vision
- Architecture
- ADR-001 Platform First
- ADR-002 Business Workflows
- ADR-003 Integration Layer