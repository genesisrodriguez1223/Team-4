# 1. Stakeholder Analysis: 

There are a few stakeholders to consider during the development of the application. These stakeholders each hold their own interests and influence over how its created: 

## i. The Professor (Michael Bartz):  

     i. His interests are to see a fully developed web application which fulfill every requirement set by the team and its guidelines set from previous assignments 

     ii. The influence the professor holds over the project is that he can dictate if the team is headed in the right direction or if they are staying from the overall objective. In such a case, he has the influence to tell the team to go back to previous steps and try to look for alternative approaches 

     iii. The item(s)/ideas the professor is looking for in, is a final deliverable application, in which it checks every requirement set by himself during the beginning of the semester. He is also looking for contributions each team member played during this process. 

## ii. Team Developers: 

    i.The team develops have an interest in wanting to design and implement a complete and function application that coincides with the scope they set themselves during the planning stages. 

    ii. They hold a medium-to-high amount of influence as they are responsible for any limitations that they have set themselves to, as well as having the control to modify their program to fulfill their needs as long as they are within the project's scope. 

    iii.The needs the team wishes to see is a testable application in which each function works as intended, and it matches the scope set by themselves which was approved by the professor at the beginning of the semester. 

## iii. Client: 

    i.The interest the client holds within the project is that they are expecting a final, polished end-product (the application) that meets their goals 

    ii.They hold a medium-to-low level of influence as the clients mainly want the finished product rather than wanting to know the details or difficulties that came from programming and testing it prior to its release. 

    iii.The needs that they want fulfilled is a fully useable, and reliable product that does not have any sort of difficulty operating on as well as completes the basic operational needs 

# 2. Functional Requirements: 
1) Service Registration
   - The system shall allow admins to configure health checks for registered services.
   
2) Health Check Configuration
   - The system shall allow configured health checks to run automatically on a schedule.
   
3) Service Status Display
   - The system shall provide a central status page that displays the current status of monitored services as operating normally, experiencing problems, or unavailable.
   
4) Automatic Incident Creation
  - The system shall be able to automatically create an incident when a health check identifies a service problem.

5) Incident Updates
  - The system shall allow administrators to add updates to an active incident throughout the resolution process.

 6) Incident Closure
  - The system shall allow administrators to close an incident after the issue has been resolved.

# 3. Non-Functional Requirements: 

#### 1) Page Load Time
The status page shall load within **3 seconds** under normal operating conditions.

#### 2) Notification Time
 Email and webhook notifications shall be sent within **60 seconds** after a relevant service status change is recorded.

#### 3) Access Control
Only users with **administrator permissions** shall be allowed to register services, configure health checks, update incidents, and close incidents.

#### 4) Browser Compatibility
The web application shall function on the **latest versions of Google Chrome, Microsoft Edge, and Mozilla Firefox**.




# 4. User stories & Epics, with acceptance criteria: 

## Epic 1 — Service & Component Management

### User Story 1 — Register a Service

**As an administrator, I want to register a service so that it can be monitored and displayed on the public status page.**
### Acceptance Criteria

- **Given** an administrator is logged in, **when** they provide a service name and required information, **then** the service can be registered.
- **Given** a service has been registered, **when** the administrator views the dashboard, **then** the registered service appears in the service list.
- **Given** a service has been registered, **when** a user views the public status page, **then** the service appears on the status page.
- **Given** a service already exists, **when** an administrator attempts to register a duplicate service, **then** the system prevents the duplicate registration.
---
### User Story 2 — Configure Service Health Checks

**As an administrator, I want to configure health checks for a service so that the system can determine whether the service is operating normally.**
### Acceptance Criteria

- **Given** a service has been registered, **when** an administrator configures a health check, **then** the health check is associated with that service.
- **Given** a health check has been configured, **when** its scheduled time occurs, **then** the system automatically runs the health check.
- **Given** a registered service, **when** an administrator manually triggers a health check, **then** the system runs the health check immediately.
- **Given** a health check has been completed, **when** the result is available, **then** the system records the result.
- **Given** a health check fails, **when** the system processes the result, **then** the associated service is identified as potentially experiencing a problem.

## Epic 2 — Public Service Status

### User Story 3 — View Service Status

**As a user, I want to view the current status of monitored services so that I know whether they are operating normally.**

### Acceptance Criteria

- **Given** the user visits the public status page, **when** the page loads, **then** monitored services are displayed.
- **Given** a monitored service is displayed, **when** the user views the service, **then** its current status is shown.
- **Given** a service has a status, **then** the status identifies whether the service is operating normally, experiencing problems, or unavailable.
- **Given** a health check has been completed, **when** the user views the status page, **then** the displayed service status reflects the most recent available health-check result.

---

### User Story 4 — View Service and Incident History

**As a user, I want to view previous service incidents so that I can understand the service's recent problems and resolutions.**

### Acceptance Criteria

- **Given** a service has previous incidents, **when** the user views the service history, **then** previous incidents are displayed.
- **Given** an incident is displayed, **then** the incident includes its date and current or final status.
- **Given** an incident contains updates, **when** the user views the incident, **then** the relevant incident updates are displayed.
- **Given** an incident has been resolved, **then** the incident is identified as closed or resolved.
- **Given** a service has no previous incidents, **then** the system displays that no incident history is available.


## Epic 3 — Incident Management

### User Story 5 — Create an Incident

**As an administrator, I want to create an incident when a service experiences a problem so that users can be informed about the issue.**

### Acceptance Criteria

- **Given** an administrator is logged in, **when** they create an incident, **then** the incident is associated with the affected service.
- **Given** a health check fails, **when** the configured incident conditions are met, **then** the system can automatically create an incident.
- **Given** an administrator identifies a service problem, **when** they manually create an incident, **then** the incident is added to the system.
- **Given** an incident is created, **then** it has an initial status indicating that the incident is active.
- **Given** an incident has been created, **then** the incident can be displayed on the public status page.

---

### User Story 6 — Update an Incident

**As an administrator, I want to post updates to an incident so that users can see the progress toward resolving the problem.**

### Acceptance Criteria

- **Given** an active incident exists, **when** an administrator adds an update, **then** the update is associated with the incident.
- **Given** an administrator submits an incident update, **then** the system records the date and time of the update.
- **Given** an incident has an update, **when** a user views the incident, **then** the update is displayed on the public status page.
- **Given** multiple updates exist for an incident, **then** the updates are displayed in chronological order.
- **Given** an incident is active, **then** administrators can continue adding updates until the incident is resolved.

---

### User Story 7 — Close an Incident

**As an administrator, I want to close a resolved incident and document a post-mortem so that the resolution is recorded for future reference.**

### Acceptance Criteria

- **Given** an active incident has been resolved, **when** an administrator closes the incident, **then** the incident status changes to resolved or closed.
- **Given** an administrator closes an incident, **then** the system records the date and time of closure.
- **Given** an incident is being closed, **when** the administrator provides post-mortem information, **then** the information is saved with the incident.
- **Given** an incident has been closed, **then** it remains available in the service's incident history.
- **Given** an incident is closed, **then** the public status page reflects that the incident has been resolved.

# 5. Traceability table: 

# 6. Authorship map: 

| Section | Author | Contributions |
|----------|---------|---------------|
| Stakeholder Analysis | Gabriel | Defined the stakeholder list and what their interests & Needs are |
| Functional requirements | Genesis | Entered functional requirements for site |
| Non-Functional Requirements | Genesis | Entered non-functional requirements for site |
| User stories and epics | Madison  | Defined user stories, epics, and acceptance criteria  |
| Traceability | (Insert name here) | (Insert description of what you did) |
| Authorship Map | Team | Provides insight into what the team did during the creation of this assignment |
| AI-Use Disclosure | Gabriel | Disclosed the use of AI and what will it be used for |


# 7. AI-use disclosure: 

1. The use of AI in the production of this application will be based on using it to help come up with general recommendations, serve as a secondary tool to help review code once the developers have reviewed and completed any programming they have been instructed to complete 

2. AI serves as a tool to ensure quality is at its highest rather than using it as a dependency and trying to complete every single part of a project without any human intervention 
