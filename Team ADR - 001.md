# Team ADR-001

## Context

The team’s status page must provide end users with clear information about the condition of monitored services. During team discussions, members expressed different preferences regarding how much information the page should present, ranging from a minimal current-status display to a richer view containing historical availability and incident context.

The team needed to balance simplicity and ease of interpretation against the usefulness of providing users with additional context about previous service disruptions. Because the selected design needed to bring together current monitoring results with historical and incident information, it also affected how multiple parts of the application would support the public-facing status experience.

## Decision

The team decided to design the public status page to present:

- The current status of each monitored service
- Timestamps to show when each monitored service was last checked
- A visual history of recent service availability and disruptions
- A related incident information and updates log describing known disruptions and how they progressed toward resolution.

## Alternatives Considered

### Alternative 1: Current Status Only

The public status page would display only the present condition of each monitored service, such as operating normally, experiencing problems, or unavailable.

**Reason not chosen:**

This approach would be the simplest to design and understand, but it would provide users with no historical context about previous disruptions. A user could determine whether a service is currently available but would not be able to see whether the service had experienced recent problems or when the service was last checked.

### Alternative 2: Current Status with Historical Availability Indicators Only

The public status page would display the current service condition together with a visual history showing recent periods or dates of normal operation and disruption. The page would show when a disruption occurred, but incident explanations and updates would not be connected to the historical indicators.

**Reason not chosen:**

This approach would provide more context than a current-status-only display, but users would still have limited information about what caused a disruption or how the issue progressed toward resolution. The team preferred a design that combines availability history with related incident information so users can understand both when a disruption occurred and the context surrounding it.

## Consequences

### Positive Consequences

- Users can determine the current condition of a monitored service quickly.
- Users can see when the service was last checked, helping them judge the freshness of the displayed status information.
- Users can also view recent availability information instead of seeing only the service's present state.
- Related incident information can explain service disruptions and provide updates on their progression and resolution.
- The public page provides users with both immediate service condition information and additional context about recent disruptions and their resolution.

### Negative Consequences

- The public status page will be more complex to design, implement, and test compared with either of the rejected alternatives and reduces the option of keeping the public status page minimal.
- The application must keep the availability information and related incident information consistent so that users are not shown misleading or mismatched context.
- The team must define how service disruptions are associated with the incident information presented to users.
