# Architecture

## Purpose

Describe the architectural structure, guiding concepts, and major responsibilities of the Juliet's House Volunteer Platform.

---

## Audience

- Enterprise Architects
- Solution Architects
- Developers
- Technical Leadership
- Future Contributors

---

# Overview

The Juliet's House Volunteer Platform follows a layered architecture that separates user experiences, conversational AI, business services, platform services, integration services, and external systems.

Each architectural layer has clearly defined responsibilities and communicates through well-defined interfaces. This separation enables business capabilities to remain reusable, maintainable, and independent of any single user interface or third-party platform.

The platform is designed around the principle that rescue work occurs before administrative work. Information should be captured wherever rescue activities occur, confirmed by the reporter, and published as organizational working information through reusable Business Services. A later human organizational review determines whether that information should become an official organizational record.

---

# Architectural Principles

The platform follows several core architectural principles:

- AI augments people; it does not replace human judgment.
- Human approval is required before official organizational records are created or modified.
- Business capabilities are implemented as reusable Business Services.
- Reusable technical capabilities are implemented as Platform Services.
- Business logic is independent of user interfaces.
- Integrations are isolated behind reusable services.
- External systems remain the authoritative owners of persistent organizational data.
- Documentation evolves alongside implementation.
- The platform remains portable and deployment-agnostic whenever practical.
- Prefer simplicity over unnecessary complexity.

---

# Primary Business Artifact

The platform's primary business artifact is the **Observation Report**.

An Observation Report represents organizational working information captured during rescue activities. It may later inform an official organizational record through a separate Intake process.

An Observation Report may contain:

- Reporter
- Timestamp
- Location
- Voice transcript
- Documents (photographs, videos, and future supporting files)
- Observation summary
- One or more Animal Observations

An Observation Report may ultimately inform one or many official animal records through a separate Intake process.

This separation allows field observations to be captured naturally while administrative processes occur later.

---

# Information Lifecycle

Information moves through the platform using a consistent lifecycle.

```text
Capture
    ↓
Validate
    ↓
Review
    ↓
Confirm
    ↓
Publish
```

### Capture

Information is collected through conversational experiences such as voice, text, and supporting documents.

### Validate

Business Services validate captured information, normalize data, and prepare it for review.

### Review

The proposed Observation Report is presented to the reporter for verification.

### Confirm

The reporter confirms the information before publication as organizational working information.

### Publish

Confirmed information is published as an Observation Report that remains organizational working information and is available for downstream organizational review.

Observation publication does not create an Intake or an official animal record. The publishing destination may evolve over time without affecting the user experience or Business Services.

---

# Layered Architecture

## Layer 1 — Experience Layer

Provides user-facing experiences that interact with the platform.

### Responsibilities

- Capture observations
- Present organizational knowledge
- Display summaries
- Collect confirmations and approvals
- Initiate business capabilities

### Examples

- AI Assistant
- Future Volunteer Portal
- Future Administrative Portal
- Future Mobile Applications
- Future Messaging Integrations

---

## Layer 2 — AI Orchestration Layer

Responsible for understanding user intent and orchestrating platform capabilities.

This layer is used by AI-enabled experiences and is not required for User Experiences that do not use AI.

### Responsibilities

- Determine user intent
- Conduct conversations
- Extract structured information
- Summarize observations
- Invoke business workflows

### The AI does not

- Implement business rules
- Validate organizational policies
- Authenticate with external systems
- Persist organizational data

---

## Layer 3 — Business Services Layer

Implements reusable organizational capabilities.

Business Services are independent of the user interface and may be consumed by conversational AI, future web applications, scheduled automations, or additional integrations.

### Implemented and Tested Business Capabilities

- Capture Field Observation
- Review Observation Report
- Publish Observation Report

### Implemented Business Capabilities

- Knowledge Search

### Not Implemented

- Update Animal

### Future Business Capabilities

- Create Official Intake
- Foster Management
- Adoption Assistance
- Volunteer Management
- Reporting

### Responsibilities

- Business validation
- Data normalization
- Business rules
- Workflow orchestration
- Human approval
- Business policy enforcement

---

## Layer 4 — Platform Services Layer

Provides reusable technical capabilities shared across Business Services.

Platform Services encapsulate technical functionality that is not specific to a single business capability and promote reuse across the platform.

### Established Platform Services

- Configuration Service
- ID Generation Service

### Architecturally Accepted / Not Implemented

- Document Service

### Planned Platform Services

- Notification Service
- Audit Service

### Responsibilities

- Shared technical capabilities
- Document management
- Identifier generation
- Configuration management
- Cross-cutting platform functionality

---

## Layer 5 — Integration Services Layer

Provides reusable interfaces to external systems.

### Responsibilities

- Authentication
- API execution
- GraphQL execution
- Retry logic
- Response parsing
- Error handling
- Logging

Business Services communicate with external systems only through this layer.

---

## Layer 6 — External Systems Layer

External systems own persistent organizational data.

External Systems are represented as the sixth architectural layer but remain outside the Volunteer Platform boundary.

### Examples

- Pawlytics
- Google Workspace
- Mailchimp
- Future organizational systems

The Volunteer Platform augments these systems but does not replace them.

---

# Architectural Data Flow

A simplified view of permitted dependencies within the platform is shown below.

```text
Experience Layer
    ├── AI Orchestration Layer, when the experience is AI-enabled
    │       └── Business Services Layer
    └── Business Services Layer, when AI orchestration is not required

Business Services Layer
    ├── Platform Services Layer, as required
    └── Integration Services Layer, as required

Integration Services Layer
    └── External Systems Layer
```

User Experiences may invoke Business Services directly or use AI Orchestration when appropriate. Business Services may orchestrate Platform Services and invoke Integration Services as required. Integration Services encapsulate communication with External Systems.

---

# Architectural Style

The Juliet's House Volunteer Platform follows a layered architecture composed of reusable Business Services supported by reusable Platform Services.

The architecture intentionally separates:

- User experiences
- Conversational orchestration
- Business capabilities
- Platform capabilities
- Integration services
- External systems

Business Services implement organizational capabilities such as capturing and publishing observations, with additional capabilities such as animal record updates introduced when implemented.

Platform Services provide reusable technical capabilities that support multiple Business Services. Examples include document management, configuration, identifier generation, notifications, and other shared infrastructure concerns.

This separation allows the platform to evolve by adding new user interfaces, business workflows, platform capabilities, or integrations without requiring significant architectural redesign.

Conversational AI is one experience into the platform rather than the platform itself.

Business capabilities remain reusable regardless of whether they are invoked by conversational interfaces, web applications, scheduled automations, or future integrations.
