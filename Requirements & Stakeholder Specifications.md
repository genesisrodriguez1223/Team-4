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

## Epic 4 — User Subscriptions & Notifications

### User Story 8 — Subscribe to a Service

**As a user, I want to subscribe to a service so that I can receive notifications when its status changes.**

### Acceptance Criteria

- **Given** a user is viewing a monitored service, **when** they choose to subscribe, **then** the system allows them to create a subscription.
- **Given** a user creates a subscription, **then** the subscription is associated with the selected service.
- **Given** a user has subscribed to a service, **then** the system stores the user's subscription information.
- **Given** a user has an existing subscription, **when** they choose to unsubscribe, **then** the system removes or disables the subscription.
- **Given** a user is subscribed to a service, **then** the subscription remains active until the user unsubscribes or the system disables it.

---

## User Story 9 — Receive Service Notifications

**As a subscribed user, I want to receive notifications when a service experiences a relevant status change so that I know when a problem occurs or is resolved.**

### Acceptance Criteria

- **Given** a user is subscribed to a service, **when** the service experiences a relevant status change, **then** the system generates a notification.
- **Given** a user has selected email notifications, **when** a relevant status change occurs, **then** the system sends an email notification.
- **Given** a user has configured a webhook, **when** a relevant status change occurs, **then** the system sends the notification to the configured webhook.
- **Given** a notification is generated, **then** it identifies the affected service and its current status.
- **Given** a notification cannot be delivered, **then** the system records the delivery failure for administrative review.


## Epic 5 — AI-Assisted Incident Communication

### User Story 10 — Generate an AI Incident Summary

**As an administrator, I want to generate an AI-assisted incident summary from logs and error traces so that I can quickly create a concise public-facing update.**

### Acceptance Criteria

- **Given** an administrator has incident information, **when** they provide relevant log excerpts or error traces, **then** the system can submit the information to the AI summarizer.
- **Given** the AI receives logs or error traces, **then** it generates a concise summary of the incident.
- **Given** an AI summary has been generated, **then** the summary is displayed to the administrator for review.
- **Given** an AI summary is generated, **then** the original logs and error traces are not automatically published as a public status update.
- **Given** the AI cannot generate a summary, **then** the system informs the administrator and allows them to create an update manually.

---

## User Story 11 — Review an AI-Generated Summary

**As an administrator, I want to review and edit an AI-generated incident summary so that inaccurate or inappropriate information is corrected before it becomes an official public update.**

### Acceptance Criteria

- **Given** an AI-generated summary exists, **when** an administrator opens the summary, **then** the generated content is displayed for review.
- **Given** an administrator is reviewing the summary, **then** they can edit the generated content.
- **Given** an administrator approves the summary, **then** the approved content can be used as an official incident update.
- **Given** an administrator rejects the summary, **then** the summary is not published as an official update.
- **Given** an AI-generated summary has not been approved by an administrator, **then** the system does not automatically publish it.
- **Given** an administrator edits an AI-generated summary, **then** the final approved version is used for the official incident communication.


## Epic 6 — Administrative Management

### User Story 12 — Manage Services and Incidents

**As an administrator, I want a centralized management dashboard so that I can monitor services and manage incidents from one location.**

### Acceptance Criteria

- **Given** an administrator is logged in, **when** they access the administrative dashboard, **then** the dashboard displays the services managed by the organization.
- **Given** services are registered, **then** the dashboard displays their current status.
- **Given** active incidents exist, **then** the dashboard displays the active incidents and their affected services.
- **Given** an administrator selects a service, **then** they can access the available service management functions.
- **Given** an administrator selects an incident, **then** they can access the available incident management functions.
- **Given** an administrator has permission to manage the platform, **then** they can create, update, and manage services and incidents through the dashboard.

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
