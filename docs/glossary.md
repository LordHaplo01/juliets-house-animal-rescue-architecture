# Glossary

## Volunteer
A Juliet's House volunteer interacting with the Volunteer Platform.

---

## Staff
Authorized Juliet's House personnel responsible for reviewing intakes, managing records, maintaining organizational content, and administering platform features.

---

## Platform Administrator
Technical administrator responsible for configuring, maintaining, and extending the Volunteer Platform.

---

## Volunteer Platform
The collection of applications, workflows, AI assistants, and integrations that support Juliet's House Animal Rescue operations.

---

## AI Assistant
A large language model responsible for interacting with users, interpreting intent, and orchestrating business workflows.

---

## Workflow
An n8n workflow implementing a discrete business capability.

Examples include:

- Create Intake
- Update Animal
- Search Knowledge Base

---

## Tool
A workflow exposed to the AI Assistant that performs a specific business function.

---

## Backend Services
Internal services implementing business logic and integrations.

Examples include:

- n8n
- GraphQL Service
- Authentication
- Validation
- Notification Services

---

## Pawlytics
The primary animal management platform used by Juliet's House Animal Rescue.

---

## Knowledge Base
Organizational documentation indexed for semantic search.

Current implementation uses:

- Ollama Embeddings
- Qdrant Vector Database

---

## RAG (Retrieval-Augmented Generation)
Technique allowing the AI Assistant to retrieve relevant organizational documentation before generating a response.

---

## Vector Database
A database optimized for semantic similarity search.

Current implementation uses Qdrant.

---

## GraphQL Service
Internal integration layer responsible for authenticated communication with external APIs.

This abstracts third-party implementations from business workflows.

---

## Mailchimp
External marketing and communication platform used by Juliet's House.

(Current integration scope to be determined.)

---

## Human Review
A mandatory approval step before business data is created or modified.

---

## ADR (Architecture Decision Record)
A document capturing an important architectural decision, its context, alternatives considered, and rationale.

---

## C4 Model
A hierarchical architecture modeling approach consisting of:

- Context
- Containers
- Components
- Code

Used throughout this repository.