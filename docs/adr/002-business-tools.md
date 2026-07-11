Title

Use reusable business workflows rather than embedding business logic inside AI prompts.

Status

Accepted

Context

Business processes such as animal intake, record updates, and knowledge retrieval may be invoked by conversational AI, scheduled automations, future web applications, or other integrations.

Embedding business rules directly into AI prompts or individual user experiences would duplicate logic and make maintenance difficult.

Decision

Business logic will be implemented as reusable workflows and services.

Conversational AI is responsible for understanding user intent and orchestrating the appropriate business workflows, but it does not implement the business rules itself.

Consequences

Benefits

• Single source of truth
• Reusable workflows
• Easier testing
• Easier future integrations
• Reduced prompt complexity

Tradeoffs

• Additional workflow orchestration
• Slight increase in implementation complexity