# ADR-0001

## Title

Platform-First Architecture

## Status

Accepted

---

## Context
...

---

## Decision

The solution will be architected as a single Volunteer Platform composed of:

- User Experiences
- Business Services
- Platform Services
- Integration Services

Conversational AI will be one user experience within the platform rather than the platform itself.

Business capabilities will be implemented as reusable Business Services that may be consumed by conversational interfaces, web applications, scheduled automations, and future user experiences.

---

## Consequences

- Business Services encapsulate reusable business capabilities.
- Platform Services encapsulate reusable technical capabilities.
- Integration Services encapsulate communication with external systems.
