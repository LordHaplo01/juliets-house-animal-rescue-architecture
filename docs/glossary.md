# Glossary

## Purpose

This glossary defines the common business and technical terminology used throughout the Juliet's House Volunteer Platform architecture.

These definitions establish a shared vocabulary for stakeholders, architects, developers, and future contributors.

---

## Audience

- Leadership
- Volunteers
- Architects
- Developers
- Future Contributors

---

# People

## Volunteer

A Juliet's House volunteer interacting with the Volunteer Platform to capture information, search organizational knowledge, or perform operational tasks.

---

## Staff

Authorized Juliet's House personnel responsible for reviewing observations, managing organizational records, administering platform capabilities, and maintaining organizational content.

---

## Platform Administrator

Technical administrator responsible for configuring, maintaining, monitoring, and extending the Volunteer Platform.

---

# Business Concepts

## Observation Report

The primary business artifact captured by the Volunteer Platform.

An Observation Report represents organizational working information collected during rescue activities. It may later inform the creation or modification of an official organizational record through a separate Intake process.

An Observation Report may contain one or many Animal Observations.

---

## Animal Observation

Information describing a single observed animal within an Observation Report.

Examples include:

- Species
- Estimated age
- Physical condition
- Behavior
- Color and markings
- Notes

Animal Observations may later inform official animal records through a separate Intake process.

---

## Human Review

Human verification appropriate to the business decision being made.

The reporter reviews and confirms a proposed Observation Report before it is published as organizational working information. A later human organizational review determines whether a published Observation Report should proceed toward Intake and an official organizational record.

---

## Publish

The process of making a reporter-confirmed Observation Report available as organizational working information for downstream organizational review.

Publishing an Observation Report does not create an Intake or an official animal record.

---

# Platform Concepts

## Volunteer Platform

The collection of user experiences, optional AI Orchestration, Business Services, Platform Services, workflows, and Integration Services that support Juliet's House Animal Rescue operations.

Conversational AI is one experience within the platform rather than the platform itself.

External Systems interact with the Volunteer Platform but remain outside its boundary.

---

## AI Assistant

A conversational interface responsible for interacting with users, interpreting intent, collecting information, and orchestrating business capabilities.

The AI Assistant does not implement business rules or persist organizational data.

---

## Business Service

A reusable organizational capability implementing a discrete business function.

Examples include:

- Capture Field Observation
- Review Observation Report
- Publish Observation Report
- Knowledge Search

Business Services are independent of user interfaces.

---

## Platform Service

A reusable technical capability that supports one or more Business Services.

Platform Services encapsulate shared technical functionality that is independent of any single business capability.

Examples include:

- Document Service
- Configuration Service
- ID Generation Service
- Notification Service

Platform Services do not implement business rules.

---

## Document Service

A Platform Service responsible for managing supporting documents associated with business artifacts.

The Document Service is architecturally accepted but not implemented. It is the next implementation target.

Responsibilities include:

- Document validation
- Storage abstraction
- Metadata management
- Returning storage references

Business Services determine when documents are required. The Document Service manages their technical lifecycle.

---

## Workflow

An implementation of a Business Service that may orchestrate one or more Platform Services and Integration Services.

The current implementation uses n8n workflows, although the architectural concept is independent of any specific workflow platform.

---

## Tool

A Business Service exposed to the AI Assistant for invocation during a conversation.

---

# External Systems

## Pawlytics

The primary animal management system used by Juliet's House Animal Rescue and the authoritative system of record for official animal records.

---

## Knowledge Base

Organizational documentation indexed for semantic search.

The Knowledge Base provides organizational information to volunteers and staff without replacing official organizational records.

---

## Mailchimp

External communication platform used by Juliet's House.

Future integration scope remains under evaluation.

---

# Technical Concepts

## RAG (Retrieval-Augmented Generation)

A technique allowing the AI Assistant to retrieve relevant organizational documentation before generating a response.

---

## Vector Database

A database optimized for semantic similarity search.

The current implementation uses Qdrant.

---

## GraphQL Service

An internal integration service responsible for authenticated communication with external GraphQL APIs.

This service abstracts third-party implementations from business services.

---

# Architecture Concepts

## Architecture Decision Record (ADR)

A document capturing an important architectural decision, its context, alternatives considered, and rationale.

---

## C4 Model

A hierarchical architecture modeling approach consisting of:

- Context
- Containers
- Components
- Code

Used throughout this repository to communicate the platform architecture.

---

## Layered Architecture

An architectural style that separates the Experience Layer, optional AI Orchestration Layer, Business Services Layer, Platform Services Layer, Integration Services Layer, and External Systems Layer into six well-defined layers with clearly defined responsibilities.

Business capabilities communicate through these layers while remaining loosely coupled and independently maintainable.
