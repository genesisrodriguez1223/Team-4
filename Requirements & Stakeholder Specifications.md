# 1. Stakeholder Analysis: 

There are a few stakeholders to consider during the development of the application. These stakeholders each hold their own interests and influence over how its created: 

## i. The Professor (Michael Bartz) - SH-01:  

     i. His interests are to see a fully developed web application which fulfill every requirement set by the team and its guidelines set from previous assignments 

     ii. The influence the professor holds over the project is that he can dictate if the team is headed in the right direction or if they are staying from the overall objective. In such a case, he has the influence to tell the team to go back to previous steps and try to look for alternative approaches 

     iii. The item(s)/ideas the professor is looking for in, is a final deliverable application, in which it checks every requirement set by himself during the beginning of the semester. He is also looking for contributions each team member played during this process. 

## ii. Team Developers - SH-02: 

    i.The team develops have an interest in wanting to design and implement a complete and function application that coincides with the scope they set themselves during the planning stages. 

    ii. They hold a medium-to-high amount of influence as they are responsible for any limitations that they have set themselves to, as well as having the control to modify their program to fulfill their needs as long as they are within the project's scope. 

    iii.The needs the team wishes to see is a testable application in which each function works as intended, and it matches the scope set by themselves which was approved by the professor at the beginning of the semester. 

## iii. Service Administrators - SH-03:

    i. Service Administrators are interested in reliably monitoring registered services and managing incidents so that service problems can be identified, communicated, and resolved efficiently.

    ii. They hold a medium-to-high level of influence because their operational workflows define many of the application's administrative functions, including service registration, health-check management, incident management, and review of AI-assisted incident communications.

    iii. Service Administrators need the system to allow them to register services, configure and run health checks, create and manage incidents, document resolutions and post-mortems, use the administrative management interface, and review AI-generated incident summaries before they are used as official communication.

## iv. End Users / Subscribers SH-04:

    i. End Users and Subscribers are interested in knowing the current condition of monitored services and receiving clear information when service problems occur or are resolved.

    ii. They hold a medium level of influence because their information and notification needs drive the public-facing status, history, subscription, and notification functionality of the application.

    iii. End Users and Subscribers need the system to provide a public status page, service and incident history, service subscriptions, and email or webhook notifications for relevant service status changes.


# 2. Functional Requirements (Initial): 
1) Service Registration - FR-01
   - The system shall allow admins to configure health checks for registered services.
   
2) Health Check Configuration - FR-02
   - The system shall allow configured health checks to run automatically on a schedule.
   
3) Service Status Display - FR-03
   - The system shall provide a central status page that displays the current status of monitored services as operating normally, experiencing problems, or unavailable.
   
4) Automatic Incident Creation - FR-04
   - The system shall be able to automatically create an incident when a health check identifies a service problem.

5) Incident Updates - FR-05
   - The system shall allow administrators to add updates to an active incident throughout the resolution process.

6) Incident Closure - FR-06
   - The system shall allow administrators to close an incident after the issue has been resolved.

# 3. Non-Functional Requirements: 

#### 1) Page Load Time - NFR-01
The status page shall load within **3 seconds** under normal operating conditions.

#### 2) Notification Time - NFR-02
 Email and webhook notifications shall be sent within **60 seconds** after a relevant service status change is recorded.

#### 3) Access Control - NFR-03
Only users with **administrator permissions** shall be allowed to register services, configure health checks, update incidents, and close incidents.

#### 4) Browser Compatibility - NFR-04
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

 The table below traces the commitments in the approved Team Charter and Executive Summary to the requirements currently written in this specification and then to the current user stories and acceptance criteria. A dash (—) indicates that the traceability exercise found no corresponding functional requirement in the team's current requirements section.

| Charter Commitment | Initial Requirement | Initial User Story / Acceptance Criteria | Traceability Finding |
| --- | --- | --- | --- |
| Service/component registry; administrators register services | **FR-01 — Service Registration** | **US-01 — Register a Service** | **Conflict:** FR-01 is titled Service Registration, but its statement describes configuring health checks rather than registering a service. |
| Administrators configure health checks | **FR-01 — Service Registration** | **US-02 — Configure Service Health Checks** | **Conflict:** Health-check configuration appears under FR-01 even though FR-01 is titled Service Registration. |
| Scheduled health checks | **FR-02 — Health Check Configuration** | **US-02** — scheduled-execution acceptance criterion | **Conflict:** FR-02 describes scheduled execution rather than health-check configuration. |
| On-demand health checks | — | **US-02** — manual-trigger acceptance criterion | **Gap:** Charter/story include on-demand checks, but no corresponding functional requirement exists. |
| Health-check monitoring / current service condition | — | **US-02** — result-recording acceptance criterion | **Supporting gap:** Result recording appears in the story but has no corresponding functional requirement. |
| Public status page showing service condition | **FR-03 — Service Status Display** | **US-03 — View Service Status** | Covered. |
| Service and incident history | — | **US-04 — View Service and Incident History** | **Gap:** Charter/story include history, but no corresponding functional requirement exists. |
| Automatic incident creation from failed checks | **FR-04 — Automatic Incident Creation** | **US-05 — Create an Incident** — automatic-creation acceptance criterion | Covered; story adds a configured incident-condition concept not stated in the current functional requirement. |
| Manual incident creation | — | **US-05 — Create an Incident** — manual-creation acceptance criterion | **Gap:** Charter/story include manual incident creation, but no corresponding functional requirement exists. |
| Incident updates | **FR-05 — Incident Updates** | **US-06 — Update an Incident** | Covered. |
| Incident closure | **FR-06 — Incident Closure** | **US-07 — Close an Incident** | Covered. |
| Incident post-mortem | — | **US-07** — post-mortem acceptance criterion | **Gap:** Charter/story include a post-mortem, but no corresponding functional requirement exists. |
| User subscriptions | — | **US-08 — Subscribe to a Service** | **Gap:** Charter/story include subscriptions, but no corresponding functional requirement exists. |
| Subscription removal | — | **US-08** — unsubscribe acceptance criterion | **Supporting item:** Present in the team story but not an explicit charter commitment/current functional requirement. |
| Email notifications | — | **US-09 — Receive Service Notifications** — email acceptance criterion | **Gap:** Charter/story include email notifications, but no functional requirement covers them. **NFR-02** supplies timing only. |
| Webhook notifications | — | **US-09** — webhook acceptance criterion | **Gap:** Charter/story include webhook notifications, but no functional requirement covers them. **NFR-02** supplies timing only. |
| Notification delivery-failure recording | — | **US-09** — delivery-failure acceptance criterion | **Supporting item:** Present in the team story but not an explicit charter commitment/current functional requirement. |
| AI-assisted incident summaries from logs/error traces | — | **US-10 — Generate an AI Incident Summary** | **Gap:** Charter/story include AI summarization, but no corresponding functional requirement exists. |
| Human review of AI-generated incident communication | — | **US-11 — Review an AI-Generated Summary** | **Gap:** Charter requires human review and story covers it, but no corresponding functional requirement exists. |
| Administrative management interface | — | **US-12 — Manage Services and Incidents** | **Gap:** In scope and represented by a story, but no current functional requirement covers it. |
| Web-based public status page quality | **NFR-01 — Page Load Time** | **US-03 — View Service Status** | **Needs clarification:** 3-second threshold is measurable, but “normal operating conditions” is undefined. |
| Timely email/webhook delivery | **NFR-02 — Notification Time** | **US-09 — Receive Service Notifications** | Covered by a measurable 60-second threshold. |
| Administrator-only management actions | **NFR-03 — Access Control** | **US-01, US-02, US-05–US-07, US-12** | **Partial:** Current wording does not cover all administrator-only actions, including AI-summary approval. |
| Web application browser compatibility | **NFR-04 — Browser Compatibility** | Applies across web-application stories | **Needs clarification:** Named browsers are specific, but “shall function” lacks a defined success condition. |

## 5.1 Gaps and Conflicts Identified Through Traceability

Each numbered finding below corresponds directly to the same-numbered resolution in Section 5.2.

### Finding 1 — Service Registration, Health-Check Configuration, and Scheduled Execution Are Misaligned
FR-01 is titled **Service Registration** but describes health-check configuration. FR-02 is titled **Health Check Configuration** but describes scheduled execution. Service registration itself is therefore not correctly specified, and three different behaviors are combined or mislabeled.

### Finding 2 — On-Demand Health Checks Are Missing
The charter and US-02 include manually triggered health checks, but the initial functional requirements do not.

### Finding 3 — Health-Check Result Recording Has No Initial Requirement or Explicit Charter Source
US-02 requires completed health-check results to be recorded. The behavior is not stated in the initial requirements or the charter, so it should be confirmed by the team before final submission.

### Finding 4 — Service and Incident History Is Missing
The charter and US-04 include service and incident history, but the initial functional requirements do not.

### Finding 5 — Automatic Incident-Creation Trigger Terminology Is Inconsistent
FR-04 states that an incident is created when a health check identifies a service problem. US-05 states that automatic creation occurs when configured incident conditions are met. The requirement and story therefore describe the trigger differently.

### Finding 6 — Manual Incident Creation Is Missing
The charter and US-05 include manual incident creation, but the initial functional requirements do not.

### Finding 7 — Incident Post-Mortem Is Missing
The charter and US-07 include a post-mortem associated with incident closure, but the initial functional requirements do not.

### Finding 8 — User Subscription Is Missing
The charter and US-08 include subscriptions, but the initial functional requirements do not.

### Finding 9 — Subscription Removal Has No Explicit Charter Source
US-08 includes unsubscribe behavior. This behavior is not stated in the charter or initial requirements, so it should be confirmed by the team before final submission.

### Finding 10 — Email Notification Is Missing
The charter and US-09 include email notification. NFR-02 provides a delivery-time constraint but does not define the required email-notification behavior.

### Finding 11 — Webhook Notification Is Missing
The charter and US-09 include webhook notification. NFR-02 provides a delivery-time constraint but does not define the required webhook-notification behavior.

### Finding 12 — Notification Delivery-Failure Recording Has No Explicit Charter Source
US-09 requires failed notification deliveries to be recorded for administrative review. This behavior is not stated in the charter or initial requirements, so it should be confirmed by the team before final submission.

### Finding 13 — AI-Assisted Incident Summary Is Missing
The charter and US-10 include AI-assisted incident summarization from incident information such as logs and error traces, but the initial functional requirements do not.

### Finding 14 — Human Review and Approval of AI-Generated Communication Is Missing
The charter requires human review before AI-generated content becomes official communication, and US-11 covers review, editing, approval, and rejection. The initial functional requirements do not.

### Finding 15 — Administrative Management Interface Is Missing
The charter includes an administrative management interface and US-12 defines a centralized administrative dashboard, but the initial functional requirements do not cover it.

### Finding 16 — Page-Load Test Condition Is Undefined
NFR-01 contains a measurable three-second threshold, but **“under normal operating conditions”** does not identify the acceptance-test condition.

### Finding 17 — Access-Control Coverage Is Incomplete
NFR-03 covers several administrator-only actions but not all administrator functions represented in the current stories, including manual incident creation, administrative management, and AI-summary review and approval.

### Finding 18 — Browser Compatibility Success Condition Is Undefined
NFR-04 names the supported browsers but does not specify which workflows must succeed or what constitutes a blocking compatibility failure.

## 5.2 Changes Made to Address Traceability Findings

The resolutions below correspond one-to-one with the findings in Section 5.1. Together, the requirements stated here form the **revised requirement set**. The FR/NFR identifiers in this subsection refer to the revised requirements, while the traceability table above refers to the initial requirements. Requirements marked with **•** are team-added supporting behaviors already present in acceptance criteria and should be confirmed by the team before final submission.

### Resolution 1 — Separate Service Registration, Health-Check Configuration, and Scheduled Execution
- **FR-01 — Service Registration [SH-03]:** The system shall allow administrators to register a service to be monitored.
- **FR-02 — Health Check Configuration [SH-03]:** The system shall allow administrators to configure a health check for a registered service.
- **FR-03 — Scheduled Health Checks [SH-03]:** The system shall automatically run configured health checks according to their configured schedule.

### Resolution 2 — Add On-Demand Health Checks
- **FR-04 — On-Demand Health Checks [SH-03]:** The system shall allow administrators to manually trigger a configured health check for a registered service.

### Resolution 3 — Make Result Recording Explicit
- **FR-05 — Health-Check Result Recording [SH-03]:** The system shall record the result of each completed health check.
### Resolution 4 — Add Service and Incident History
- **FR-07 — Service and Incident History [SH-04]:** The system shall allow users to view previous incidents associated with a monitored service.

### Resolution 5 — Reconcile the Automatic Incident-Creation Trigger
- **FR-08 — Automatic Incident Creation [SH-03]:** The system shall automatically create an incident when a failed health check satisfies the configured incident-creation condition.
- **Traceability note:** This wording aligns the requirement with US-05. The team should ensure the configured condition remains within the charter's basic status-determination scope rather than becoming an advanced SLA or business-rule engine.

### Resolution 6 — Add Manual Incident Creation
- **FR-09 — Manual Incident Creation [SH-03]:** The system shall allow administrators to manually create an incident for an affected service.

### Resolution 7 — Add Incident Post-Mortem
- **FR-12 — Incident Post-Mortem [SH-03]:** The system shall allow post-mortem information to be stored with a closed incident.

### Resolution 8 — Add Service Subscription
- **FR-13 — Service Subscription [SH-04]:** The system shall allow users to subscribe to a monitored service.

### Resolution 9 — Make Subscription Removal Explicit
- **FR-14 — Subscription Removal [SH-04]:** The system shall allow a subscribed user to remove or disable their subscription to a monitored service.
### Resolution 10 — Add Email Notifications
- **FR-15 — Email Notifications [SH-04]:** The system shall send email notifications to subscribed users when a relevant service status change occurs.

### Resolution 11 — Add Webhook Notifications
- **FR-16 — Webhook Notifications [SH-04]:** The system shall send webhook notifications for subscribed services when a relevant service status change occurs.

### Resolution 12 — Make Delivery-Failure Recording Explicit
- **FR-17 — Notification Delivery-Failure Recording [SH-04]:** The system shall record notification delivery failures for administrative review.
### Resolution 13 — Add AI-Assisted Incident Summary
- **FR-18 — AI-Assisted Incident Summary [SH-03]:** The system shall allow an administrator to generate a draft public-facing incident summary from incident information, including relevant log excerpts or error traces.

### Resolution 14 — Add Human Review and Approval of AI-Generated Communication
- **FR-19 — AI Summary Review and Editing [SH-03]:** The system shall allow an administrator to review and edit an AI-generated incident summary.
- **FR-20 — Human Approval of AI Summary [SH-03]:** The system shall prevent an AI-generated summary from being published as official incident communication before administrator approval.

### Resolution 15 — Add Administrative Management Interface
- **FR-21 — Administrative Management Interface [SH-03]:** The system shall provide an administrative interface for managing registered services and incidents.

### Resolution 16 — Define the Page-Load Test Condition
- **NFR-01 — Page Load Time [SH-04]:** The public status page shall load within **3 seconds** during the project's documented acceptance-test workload.
### Resolution 17 — Expand Access-Control Coverage
- **NFR-03 — Access Control [SH-03]:** Only users with administrator permissions shall be allowed to register services; configure or manually run health checks; manually create, update, or close incidents; manage services and incidents through the administrative interface; and review, edit, approve, or reject AI-generated incident summaries.
### Resolution 18 — Define Browser Compatibility Success
- **NFR-04 — Browser Compatibility [SH-03 / SH-04]:** On the most recent stable versions of **Google Chrome, Microsoft Edge, and Mozilla Firefox available at the start of acceptance testing**, the core workflows represented by US-01 through US-12 shall complete without a blocking browser-specific error.
### Revised Requirements Retained Without a Traceability Defect

The following initial requirements were already aligned and are retained in the revised set:

- **FR-06 — Service Status Display [SH-04]:** The system shall provide a central status page that displays the current status of monitored services as operating normally, experiencing problems, or unavailable.
- **FR-10 — Incident Updates [SH-03]:** The system shall allow administrators to add updates to an active incident throughout the resolution process.
- **FR-11 — Incident Closure [SH-03]:** The system shall allow administrators to close an incident after the issue has been resolved.
- **NFR-02 — Notification Time [SH-04]:** Email and webhook notifications shall be sent within **60 seconds** after a relevant service status change is recorded.

# 6. Authorship map: 

| Section | Author | Contributions |
|----------|---------|---------------|
| Stakeholder Analysis | Gabriel | Defined the stakeholder list and what their interests & Needs are |
| Functional requirements | Genesis | Entered functional requirements for site |
| Non-Functional Requirements | Genesis | Entered non-functional requirements for site |
| User stories and epics | Madison  | Defined user stories, epics, and acceptance criteria  |
| Traceability | James Lee | Built the charter-to-requirement-to-story traceability analysis, documented gaps/conflicts, and recorded the revised requirements resulting from the review.  |
| Authorship Map | Team | Provides insight into what the team did during the creation of this assignment |
| AI-Use Disclosure | Gabriel | Disclosed the use of AI and what will it be used for |


# 7. AI-use disclosure: 

1. The use of AI in the production of this application will be based on using it to help come up with general recommendations, serve as a secondary tool to help review code once the developers have reviewed and completed any programming they have been instructed to complete 

2. AI serves as a tool to ensure quality is at its highest rather than using it as a dependency and trying to complete every single part of a project without any human intervention 
