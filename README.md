# EduSupport — Student Support & Ticket Management

## Assignment
Edumerge Solutions — Pre-Drive Product Engineering Assignment 4.

## Problem understanding
Students need a single place to raise administrative requests. Staff need ownership, prioritisation, processing, SLA awareness and resolution history. Management needs visibility into workload, overdue requests and resolution performance.

## Prototype scope
- Student support ticket creation
- Categories: Fees, Attendance, ID Card, Documents, Certificates, Other
- Priority: Low, Medium, High, Critical
- Status workflow: Open → In Progress → Pending → Resolved
- Staff ownership and reassignment
- SLA targets and ageing
- SLA breach detection and escalation logging
- Activity history / audit-style timeline
- Search and filters
- Management dashboard with workload and resolution metrics
- Local persistence using browser localStorage

## Assumptions
1. A student has a unique student ID.
2. Every ticket has one current owner; it can be reassigned.
3. SLA starts when the ticket is created.
4. Pending means work is waiting on an external/student action; ageing continues so management can see total elapsed time.
5. A resolved ticket is considered closed for SLA breach calculations.
6. This is an assessment prototype, so authentication and a production database are intentionally outside the MVP.

## Architecture / engineering decisions
This version is a zero-dependency browser prototype (HTML/CSS/JavaScript) so it can run immediately on a fresh laptop without database/server setup. Data is persisted to localStorage to demonstrate state changes across refreshes. The data model is structured so the local persistence layer can later be replaced by REST APIs and a relational database without changing the product workflow.

## Important edge cases considered
- Unassigned tickets remain visible in management metrics.
- Critical/high tickets are visually distinguishable.
- Tickets can be reassigned without losing history.
- Status/priority changes are recorded in activity history.
- SLA breaches are surfaced and can be escalated.
- Resolved tickets stop being counted as breached.
- Search/filter combinations return only matching records.
- Empty search results show a clear state.

## Validation performed
- Created a new ticket and verified it appears in the ticket list.
- Changed owner, priority and status and verified the activity history records changes.
- Tested search and category/status/priority filters.
- Tested overdue ticket display using seeded data.
- Resolved a ticket and verified it is no longer counted as SLA-breached.
- Refreshed the browser and verified data persisted through localStorage.

## Future production design
For production, use a backend API, role-based authentication, PostgreSQL/MySQL, server-side SLA calculations, notifications, scheduled escalation jobs, file attachments, and immutable audit logs.

## Run
Open `index.html` in a modern browser. No npm install or database is required.

## Workflow details added for the assessment
- Pending reason: Waiting for student, faculty, finance, document, or other action.
- Resolution notes: staff can record what was done to resolve a request.
- Changes to pending reason and resolution notes are added to the activity history.
