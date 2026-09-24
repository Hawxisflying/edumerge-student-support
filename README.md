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

```text
Open
  ↓
In Progress
  ↓
Pending ──────→ In Progress
  ↓
Resolved
