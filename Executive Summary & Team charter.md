# Team 4 - Team Charter and Executive Summary

**Team Members:** Gabriel Maya-Cruz, Genesis Rodriguez, Madison Galloway, James Lee

# 1. Executive Summary

Team 4 will develop a web-based Service Status and Incident Management Platform that helps organizations communicate the availability of software services. The platform will provide a central status page showing whether monitored services are operating normally, experiencing problems, or unavailable.

Administrators will be able to register services and configure health checks that run on a schedule or on demand. When a health check identifies a problem, the system can automatically create an incident. Administrators can document incident updates throughout the resolution process and close incidents with a post-mortem. Users can subscribe to services and receive notifications through email or webhooks when relevant status changes occur.

The platform will also include an AI-assisted incident summarizer. Given log excerpts and error traces, the summarizer will generate a concise, public-facing status update. AI-generated content will be reviewed by a team member before being used as official communication.

The project addresses a common communication problem during service disruptions: users may not know whether a service is experiencing an issue or whether the issue is being addressed, while administrators need an organized way to monitor services, manage incidents, and communicate with affected users.

# 2. Scope Statement

## In Scope

- Web-based public status page and dashboard
- Service/component registry
- Scheduled and on-demand health checks
- Automatic and manual incident creation from failed checks
- Incident updates, closure, and post-mortem documentation
- Service and incident history
- User subscriptions
- Email and webhook notifications
- AI-assisted incident summaries using logs and error traces
- Administrative management interface
- Testing and documentation of core functionality

## Out of Scope

To prevent scope creep, the project will not include:

- Native mobile or desktop applications
- SMS, phone-call, or push notifications
- Active Directory, SSO, or external identity-provider integration
- Enterprise-scale or geographically distributed deployment
- Monitoring of physical hardware or network infrastructure
- Predictive outage forecasting
- Custom AI/ML model training
- Development of a general-purpose AI assistant
- Multi-organization/multi-tenant support
- Advanced SLA/business-rule engines beyond basic status determination
- Automatic publication of AI-generated updates without human review

Out-of-scope features may only be considered after required functionality is complete and the team agrees that they will not jeopardize project deadlines.

# 3. Team Charter

## Mission

Team 4 will collaboratively design, develop, test, document, and deliver the Service Status and Incident Management Platform using effective software engineering practices.

## Team Expectations and Shared Responsibilities

Team members will communicate professionally, complete assigned work, report blockers promptly, participate in discussions, contribute to testing and documentation, and submit all code through GitHub for review before merging.

## Stakeholders

| Stakeholder | Interest |
|------------|----------|
| Project Team | Successfully delivering a functional product while meeting course requirements |
| Dr. Bartz | Ensuring/guiding the project team on the application of software engineering practices and project requirements |
| Service Administrators | Monitoring services, managing incidents, and communicating updates |
| End Users | Receiving accurate status information and notifications |

## Project Team - Roles & Responsibilities

| Team Member | Role | Interest | Responsibilities |
|------------|------|----------|------------------|
| Gabriel Maya-Cruz | Project Manager | Project organization and milestone completion | Schedule work, coordinate meetings, track progress, facilitate decisions, communicate with instructor, break tie votes |
| Genesis Rodriguez | Code Review Lead | Code quality and maintainability | Review pull requests, verify standards/testing, identify defects |
| Madison Galloway | Front-End Developer | Clear and accessible user experience | Develop UI, status page, dashboard, and front-end integration |
| James Lee | Back-End Developer | Reliable platform functionality | Develop APIs, business logic, health checks, incidents, notifications, and AI integration |

## Decision-Making

The team will first seek consensus. When multiple reasonable approaches exist, the team will compare them based on requirements, complexity, effort, maintainability, testing, schedule, and risk.

If consensus cannot be reached after discussion:

1. Each approach will be presented with its advantages and disadvantages.
2. The team will vote.
3. A simple majority determines the approach.
4. A tie is resolved by the Project Manager.
5. Significant decisions will be documented.

Once a decision is made, team members will support the selected approach unless new information demonstrates a significant project risk.

## Conflict Resolution

### Technical Disagreements

1. Each team member explains their proposed solution and reasoning.
2. The team evaluates the options against project requirements, complexity, maintainability, testing, and schedule.
3. The team attempts to reach consensus.
4. If unsuccessful, the team votes using the process above.
5. The decision is documented when it materially affects project scope or architecture.

### Interpersonal Conflicts

1. Involved team members initially attempt to resolve the issue directly and respectfully.
2. If unresolved, the Project Manager facilitates a discussion.
3. The discussion focuses on specific behaviors and project impacts.
4. If the conflict continues to affect project progress, the issue is documented and escalated to Dr. Bartz.

## Attendance, Availability, and Missed Work

The team will be expected to meet up to twice per week, generally for 30-60 minutes, with additional meetings scheduled around major milestones.

Team members are expected to contribute approximately 3-5 hours per week outside scheduled meetings and respond to project communications within 24 hours whenever reasonably possible.

Team members are expected to communicate scheduling conflicts in advance whenever possible.

If a team member misses one meeting, the Project Manager will provide meeting notes and assigned actions.

If a member misses two consecutive meetings without prior communication:

1. The Project Manager will schedule a one-on-one discussion within one week.
2. The team member will provide an update on assigned work.
3. Necessary tasks may be temporarily reassigned to protect project deadlines.
4. Continued attendance issues will be documented and escalated to the course instructor.

If a team member expects to miss a task deadline, they must notify the team as soon as possible. The team may adjust the deadline, reduce scope, provide assistance, temporarily reassign the work, or escalate the issue if a major milestone is threatened.

# 4. Success Criteria

At the end of the semester, the team will consider the project successful if it can demonstrate that:

1. Services can be registered and monitored.
2. Scheduled and on-demand health checks function correctly.
3. Manual and automatic incident management functions correctly.
4. The status page accurately reflects service conditions.
5. Users can subscribe and receive email/webhook notifications.
6. The AI summarizer generates understandable, human-reviewed status updates.
7. Core functionality is tested and documented.
8. Required deliverables are submitted on time and demonstrated successfully.

# 5. Appendix A - AI-Use Disclosure

Team 4 may use AI tools for brainstorming, research, documentation, debugging, testing support, and development of the incident summarizer. All AI-generated material will be reviewed and validated before use. Team members remain responsible for the accuracy and quality of all submitted work.

Because AI-generated summaries may vary between runs, the summarizer will be evaluated on relevance, factual consistency, clarity, and usefulness rather than exact output matching.
