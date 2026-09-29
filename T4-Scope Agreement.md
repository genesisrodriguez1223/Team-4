# Final Committed Scope

## 1. Committed Scope

Based on the team's decisions documented in **ADR-001**, the team commits to delivering a public status page that provides users with both the current condition of monitored services and additional context about recent service disruptions.

By Session 26, the following functionality will be demonstrably working:

### 1. Public Status Page

The public status page will allow users to:

- View the current status of each monitored service.
- See whether a service is operating normally, experiencing problems, or unavailable.
- View the timestamp of the most recent health check for each service.
- View a visual history of recent service availability and disruptions.
- View related incident information and updates.
- Follow the progression of known incidents toward resolution.

---

### 2. Service/Component Registry

The system will maintain a registry of monitored services/components.

Administrators will be able to:

- Add monitored services/components.
- View registered services/components.
- Update service information.
- Associate services with their current monitoring status.

Each service will include information such as:

- Service name
- Service description
- Current status
- Last health-check timestamp


---

### 3. Scheduled and On-Demand Health Checks

The system will perform health checks on registered services to determine their current condition.

The system will:

- Perform scheduled health checks.
- Support on-demand health checks.
- Record the result of each check.
- Update the service's current status based on the health-check result.
- Display the most recent check time on the public status page.

A failed health check will be reflected in the service's status and may be used to identify a potential incident.


---

### 4. User Issue/Ticket Reporting

Users will be able to submit a ticket/report when they notice that a monitored service is experiencing a problem.

A submitted report will contain information such as:

- Affected service
- Description of the problem
- Time the problem was reported
- Report status

This feature will provide a way for users to report problems that may not yet have been identified by an automated health check.


---

### 5. Incident Management

Administrators will be able to manage incidents associated with service disruptions.

The system will support:

- Creating an incident from a detected or reported problem.
- Identifying the affected service.
- Adding incident descriptions.
- Posting incident updates.
- Updating the incident's status.
- Closing/resolving an incident.

Incident information will be connected to the affected service and displayed on the public status page.


---

### 6. Service and Incident History

The system will maintain historical information about service availability and incidents.

Users will be able to:

- View recent service availability.
- Identify periods of service disruption.
- View previous incidents.
- View incident updates and resolution information.

The historical availability information and incident information should correspond to the affected service so that users can understand both **when a disruption occurred and what happened during the incident**.


---

# 2. Explicitly Deferred Functionality

The following T2 functionality will be intentionally deferred from the final committed scope:

- [ ] User subscriptions
- [ ] Email notifications
- [ ] Webhook notifications
- [ ] AI-assisted incident summaries using logs and error traces
- [ ] Advanced analytics and reporting
- [ ] Additional notification and automation features

These features were considered as part of the project's broader scope but will not be required for the Session 26 demonstration.

The team is intentionally prioritizing the core status-monitoring, reporting, and incident-management functionality so that the committed features can be fully implemented, integrated, and tested.

---

# 3. Traceability to T2 Requirements

| Committed Feature | T2 Requirement |
|---|---|
| Public Status Page | Web-based public status page and dashboard |
| Service/Component Registry | Service/component registry |
| Scheduled Health Checks | Scheduled and on-demand health checks |
| On-Demand Health Checks | Scheduled and on-demand health checks |
| User Issue/Ticket Reporting | Incident creation and reporting |
| Incident Creation | Automatic and manual incident creation from failed checks |
| Incident Updates | Incident updates, closure, and post-mortem documentation |
| Incident Closure | Incident updates, closure, and post-mortem documentation |
| Service Availability History | Service and incident history |
| Incident History | Service and incident history |

---

# 4. Delivery Risks

The team identified the following risks that could affect delivery by Session 26:

### Risk 1: Frontend and Backend Integration

The public status page, health-check system, ticket reporting, and incident management features must communicate correctly with the backend.

**Potential impact:** Features may work individually but fail when integrated.

### Risk 2: Health-Check Reliability

Automated health checks may require additional development and testing to ensure that service failures are detected and reflected correctly.

**Potential impact:** Incorrect service statuses could be displayed to users.

### Risk 3: Incident and Service History Integration

The system must correctly connect service disruptions, health-check results, user reports, and incidents.

**Potential impact:** Users could see incomplete or mismatched incident information.

### Risk 4: Limited Development Time

The team has approximately two sprints remaining to implement, integrate, and test the committed functionality.

**Potential impact:** Additional features could prevent the team from completing the core functionality.

---

# 5. Cut Order

If development falls behind schedule, the team will reduce scope in the following order:

1. Advanced incident information and additional documentation
2. Enhanced service-history visualizations
3. On-demand health checks, while retaining scheduled health checks
4. Additional administrative functionality

The team will prioritize keeping the following functionality working:

- Public status page
- Current service status
- Last health-check timestamp
- Basic service history
- Basic health checks
- User issue/ticket reporting
- Basic incident creation
- Incident updates
- Incident closure
- Basic incident history

These features represent the core functionality of the team's status-page system and directly support the design decision documented in **ADR-001**.

---

# 6. Definition of Done

A committed feature will be considered complete when:

- [ ] The feature is implemented in the application.
- [ ] The feature works with the project's frontend and backend.
- [ ] The feature has been tested by the team.
- [ ] The feature can be demonstrated during the final presentation.
- [ ] The feature works together with the other committed functionality.
- [ ] Any known critical bugs affecting the feature have been addressed.

The team will consider the project ready for the final demonstration when the committed scope can be demonstrated as one integrated system rather than as separate unfinished features.
