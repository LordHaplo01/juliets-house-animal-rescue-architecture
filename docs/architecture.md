# Architecture

## Overview

The Juliet's House Animal Rescue Volunteer Platform follows a layered architecture that separates conversational AI, business workflows, integration services, and external systems.

Each layer has clearly defined responsibilities and communicates only through well-defined interfaces.

---

## Layer 1 – Users

Volunteers interact with the platform using conversational interfaces.

Responsibilities

- Submit information
- Review summaries
- Approve changes

---

## Layer 2 – AI Layer

Responsible for understanding intent and orchestrating conversations.

Responsibilities

- Determine user intent
- Collect information
- Answer questions
- Present summaries
- Invoke business workflows

The AI does not

- Normalize data
- Validate business rules
- Authenticate to external systems
- Persist data

---

## Layer 3 – Business Workflows

Implemented using n8n.

Responsibilities

- Validation
- Normalization
- Business rules
- Orchestration

---

## Layer 4 – Integration Services

Provides reusable interfaces to external systems.

Responsibilities

- Authentication
- GraphQL execution
- Retry logic
- Response parsing
- Logging

---

## Layer 5 – External Systems

External systems own persistence.

Examples

- Pawlytics
- Mailchimp
- Google Workspace
- Future integrations

---

## Architectural Principles

- Human approval before writes.
- AI orchestrates rather than owns business logic.
- Business workflows are atomic and reusable.
- Integrations are isolated behind service workflows.
- External systems own persistent data.

## Architectural Style

The Juliet's House Animal Rescue Volunteer Platform follows a layered architecture.

Each layer has clearly defined responsibilities and communicates through well-defined interfaces.

### Experience Layer

Provides user-facing interfaces to the platform.

Examples include:

- AI Assistant
- Future Volunteer Portal
- Future Administrative Portal
- Future Telegram Bot
- Future Mobile Applications

### Business Services Layer

Implements organizational business capabilities.

Examples include:

- Create Intake
- Update Animal
- Search Animal
- Knowledge Search
- Follow-up Communications

### Integration Services Layer

Provides reusable interfaces to external systems.

Examples include:

- Authentication
- GraphQL
- Mailchimp
- Google Workspace
- Future APIs

### Data & External Systems Layer

Systems of record owned outside the platform.

Examples include:

- Pawlytics
- Google Workspace
- Mailchimp