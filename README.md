# EduSupport — Student Support & Ticket Management

A lightweight prototype for managing student administrative support requests.

## 1. Problem Understanding

Students may raise requests related to fees, attendance, ID cards, documents, certificates, and other administrative matters.

EduSupport provides a centralized workflow for staff to receive, prioritize, assign, process, monitor, escalate, and resolve these requests.

## 2. Key Features

- Ticket creation
- Ticket status management
- Priority management
- Staff assignment and ownership
- SLA targets
- Ticket ageing
- SLA breach detection
- Pending-action workflow
- Escalation
- Resolution tracking
- Activity history
- Search and filtering
- Management dashboard
- Local browser persistence

## 3. User Roles

### Student

Raises a support request with relevant details.

### Support Staff

Owns tickets, updates status and priority, works on requests, adds activity updates, and resolves tickets.

### Manager

Monitors workload, SLA breaches, priorities, unresolved requests, and escalated tickets.

## 4. Ticket Workflow

The main ticket lifecycle is:

```text
Open
  ↓
In Progress
  ↓
Pending
  ↓
In Progress
  ↓
Resolved
````

A ticket may also move directly from In Progress to Resolved when the issue is completed without requiring a pending action.

A ticket can be moved to Pending when staff are waiting for information or an action from a student, faculty member, finance team, or another department.

## 5. SLA and Ageing

Each ticket has an SLA target such as 8, 24, or 48 hours.

The system calculates ticket ageing based on the time since the ticket was created.

If an unresolved ticket exceeds its SLA target, it is identified as SLA breached.

SLA breach is treated as an SLA condition rather than a separate ticket status.

## 6. Pending-Action Workflow

Pending status is used when staff cannot continue processing until an external action or information is received.

Examples include:

* Waiting for student
* Waiting for faculty
* Waiting for finance
* Waiting for a required document
* Other external action

The pending reason provides context for why the ticket is currently waiting.

## 7. Escalation

Tickets that require higher-level attention can be escalated.

Examples include:

* SLA-breached tickets
* Critical requests
* Requests that require management intervention
* Issues that cannot be resolved by the current owner

Escalation is recorded in the ticket activity history for traceability.

## 8. Resolution Tracking

When a ticket is resolved, the system records the resolution activity and allows staff to provide resolution notes describing the outcome.

Example:

> Payment was verified and the student's fee status was updated.

This provides a record of how the request was completed.

## 9. Activity History

Important ticket actions are recorded in the activity history, including:

* Status changes
* Priority changes
* Owner changes
* Escalation
* Pending actions
* Resolution updates

This provides traceability throughout the ticket lifecycle.

## 10. Management Visibility

The dashboard provides management visibility into:

* Total tickets
* Open tickets
* Pending tickets
* SLA-breached tickets
* Resolution rate
* High and Critical priority tickets
* Unassigned tickets
* Requests by category
* Recent activity

This allows management to identify workload, unresolved requests, urgent tickets, and SLA issues.

## 11. Search and Filtering

Staff can search tickets and filter them by:

* Status
* Priority
* Category

Search and filtering help staff locate relevant requests quickly.

## 12. Architecture

The current prototype uses a simple browser-based architecture:

```text
Browser UI
    ↓
HTML / CSS
    ↓
JavaScript Application Logic
    ↓
Browser localStorage
```

The application currently runs as a client-side prototype without a backend server or external database.

## 13. Technology

* HTML
* CSS
* JavaScript
* Browser localStorage

No external database or backend server is required to run the prototype.

## 14. Assumptions

* Each student request is represented as one ticket.
* Every ticket should have an assigned owner where possible.
* Priority indicates the urgency of the request.
* SLA represents the target handling time for a ticket.
* Ticket ageing represents the elapsed time since ticket creation.
* Pending means the ticket is waiting for an external action or information.
* Critical or SLA-breached tickets can be escalated.
* Resolved tickets are considered completed.
* Activity history is used to maintain traceability of important ticket actions.

## 15. Trade-offs

Browser localStorage was selected because this is an assessment prototype and it allows the complete ticket workflow to run without requiring backend or database setup.

### Advantages

* No server setup required
* Easy to run locally
* Fast prototype development
* Data persists across browser refreshes
* Simple demonstration of the complete workflow

### Limitations

* Data is limited to the local browser
* No multi-user synchronization
* No authentication
* No centralized production database
* Not suitable for production-scale institutional data

A production implementation would use a backend API, authentication, role-based access control, and a persistent database.

## 16. Validation

The following workflows were manually tested:

* Creating a new ticket
* Viewing tickets
* Searching for tickets
* Filtering tickets by status
* Filtering tickets by priority
* Filtering tickets by category
* Assigning ticket ownership
* Changing ticket priority
* Changing ticket status
* Moving a ticket to Pending
* Recording a pending reason
* Detecting SLA breaches
* Escalating a ticket
* Resolving a ticket
* Adding resolution notes
* Recording activity history
* Refreshing the browser and verifying locally stored ticket data

## 17. Important Edge Cases

The prototype considers the following cases:

* Unassigned tickets
* High-priority tickets
* Critical-priority tickets
* SLA-breached tickets
* Tickets waiting for external action
* Tickets resolved after being pending
* Ownership changes
* Status changes
* Tickets requiring escalation
* Resolution actions requiring a resolution note

## 18. Running the Prototype

No installation or database setup is required.

1. Clone or download the repository.
2. Open `index.html` in a modern web browser.
3. Use the dashboard and ticket screens to create and manage support tickets.

## 19. AI-Assisted Development

AI-assisted development was used during the creation of this prototype.

ChatGPT was used to help:

* Analyze the assignment requirements
* Break the problem into product workflows
* Design the ticket lifecycle
* Identify relevant features and edge cases
* Generate and refine parts of the HTML, CSS, and JavaScript implementation
* Review the implementation against the assignment requirements

AI-generated output was reviewed and manually tested before being included in the prototype.

A separate `AI_USAGE_REPORT.md` file contains the detailed AI usage report.

## 20. Future Production Improvements

A production implementation could add:

* Backend REST APIs
* MySQL or PostgreSQL database
* Authentication
* Role-based access control
* Multi-user access
* Department-based ticket routing
* Email or SMS notifications
* Automated SLA monitoring
* Advanced reporting
* File attachments
* Detailed audit logs
* Centralized data storage
* Automated escalation rules

## 21. Project Structure

```text
edumerge-ticket-system/
│
├── index.html
├── styles.css
├── app.js
├── README.md
└── AI_USAGE_REPORT.md
```

## 22. Project Purpose

This project was developed as a working prototype for the Edumerge Solutions Pre-Drive Product Engineering Assignment — Assignment 4: Student Support & Ticket Management.

````

### Then save it and run:

```bash
git add README.md
git commit -m "Complete project documentation"
git push
````

