Title

Use a dedicated integration layer for Pawlytics rather than allowing workflows to communicate directly with the Pawlytics API.

Status

Accepted

Context

Multiple workflows require access to Pawlytics.

Future integrations may include:

• Create Animal
• Update Animal
• Adoption workflows
• Foster workflows
• Reporting
• Synchronization jobs

Direct API calls from each workflow would duplicate authentication, GraphQL queries, validation, and error handling.

Decision

A dedicated GraphQL integration layer will encapsulate all communication with Pawlytics.

Business workflows will invoke reusable integration workflows rather than constructing GraphQL requests directly.

Consequences

Benefits

• Centralized authentication
• Reusable GraphQL queries
• Consistent error handling
• Easier API upgrades
• Reduced duplication

Tradeoffs

• One additional abstraction layer
