
# Ticket Management System

## Project Overview

This project simulates an end-to-end Healthcare Communication and Ticket Management System using n8n and Google Gemini AI.

The workflow automatically:

- Receives client communications
- Classifies communication using AI
- Creates support tickets
- Assigns tickets to specialized agents
- Tracks SLA deadlines
- Generates agent responses
- Supports ticket reassignment
- Resolves tickets
- Maintains audit history
- Updates management dashboards
- Generates executive summaries

The project demonstrates how intelligent workflow automation can streamline healthcare operations and reduce manual effort.

---

# Problem Statement

Healthcare organizations receive hundreds of emails and requests related to:

- Claim Status
- Denial Management
- Prior Authorization
- Eligibility Verification
- Patient Balance
- Technical Support

Manual processing creates:

- Delayed responses
- Incorrect routing
- SLA violations
- Poor visibility for managers

This workflow automates the complete ticket lifecycle from communication intake to resolution.

---

# Workflow Architecture

```text
Client Communication
        |
        v
Communication Intake
        |
        v
AI Classification (Gemini)
        |
        v
Classification Parser
        |
        v
Ticket Creation
        |
        v
Agent Repository
        |
        v
Auto Assignment Engine
        |
        v
Agent Response
        |
        v
SLA Engine
        |
        v
Manager Dashboard
        |
        v
Ticket Reassignment
        |
        v
Ticket Resolution
        |
        v
Audit Trail
        |
        v
Dashboard Refresh
        |
        v
Executive Summary Generator
```

---

# Technologies Used

- n8n
- Google Gemini AI
- JavaScript
- Workflow Automation
- Healthcare Operations Concepts

---

# Workflow Modules

## 1. Communication Intake

Captures incoming client communications.

Example:

```json
{
  "messageId": "email-001",
  "from": "manager@abcpediatrics.com",
  "subject": "Claim Denied",
  "body": "Claim CLM123 denied"
}
```

---

## 2. AI Classification

Google Gemini classifies the communication.

Output:

```json
{
  "category": "Claim Status",
  "priority": "High",
  "confidence": 0.9,
  "reason": "The subject explicitly states Claim Denied."
}
```

---

## 3. Ticket Creation

Creates a structured work item.

Example:

```json
{
  "ticketId": "TKT-1782070721366",
  "status": {
    "currentStatus": "Open"
  }
}
```

---

## 4. Agent Repository

Maintains available support agents.

Example:

```json
{
  "agentId": "AG005",
  "name": "Mark",
  "specialization": "Claim Status",
  "activeTickets": 3
}
```

---

## 5. Auto Assignment Engine

Assigns tickets to the most suitable available agent.

Assignment Logic:

- Match specialization
- Check availability
- Select lowest workload

Output:

```json
{
  "assignedTo": "AG005",
  "assignedAgent": "Mark"
}
```

---

## 6. Agent Response

Automatically records the first agent response.

Example:

```json
{
  "eventType": "AGENT_RESPONSE",
  "author": "Mark",
  "message": "We are reviewing the denied claim."
}
```

---

## 7. SLA Engine

Calculates response and resolution deadlines.

Example:

```json
{
  "responseDueAt": "2026-06-21T21:49:33.501Z",
  "resolutionDueAt": "2026-06-22T03:49:33.501Z"
}
```

---

## 8. Manager Dashboard

Creates a management view.

Example:

```json
{
  "ticketId": "TKT-1782070721366",
  "priority": "High",
  "assignedAgent": "Mark",
  "currentStatus": "Open"
}
```

---

## 9. Ticket Reassignment

Allows managers to transfer tickets.

Example:

```json
{
  "previousAgent": "Mark",
  "assignedAgent": "Emily",
  "reassignedBy": "Manager"
}
```

---

## 10. Ticket Resolution

Marks the ticket as completed.

Example:

```json
{
  "currentStatus": "Resolved",
  "resolvedAt": "2026-06-21T20:05:42.611Z"
}
```

---

## 11. Audit Trail

Records every major ticket activity.

Example:

```json
[
  {
    "action": "TICKET_CREATED"
  },
  {
    "action": "AUTO_ASSIGNED"
  },
  {
    "action": "REASSIGNED"
  },
  {
    "action": "RESOLVED"
  }
]
```

---

## 12. Dashboard Refresh

Updates operational dashboards after workflow completion.

Provides:

- Current ticket state
- SLA information
- Agent assignments
- Resolution metrics

---

## 13. Executive Summary Generator

Creates a concise management report.

Example:

```json
{
  "ticketId": "TKT-1782070721366",
  "client": "ABC Pediatrics",
  "category": "Claim Status",
  "priority": "High",
  "assignedAgent": "Emily",
  "status": "Resolved"
}
```

---

# Business Benefits

- Automated ticket classification
- Intelligent agent assignment
- SLA tracking
- Reduced manual effort
- Better visibility for managers
- Improved response times
- Complete audit history
- Executive reporting

---

# Future Enhancements

### Database Integration

- PostgreSQL
- Ticket persistence
- Agent persistence
- Client management

### Backend APIs

- Spring Boot
- REST APIs
- Authentication
- RBAC

### Notifications

- Email notifications
- SMS notifications
- Escalation alerts

### Dashboard

- React Frontend
- Real-time ticket tracking
- Analytics

---

# Project Status

Current Version: Prototype Workflow

Completed Features:

- Communication Intake
- AI Classification
- Ticket Creation
- Agent Repository
- Auto Assignment
- SLA Tracking
- Ticket Reassignment
- Ticket Resolution
- Audit Trail
- Dashboard Refresh
- Executive Summary

---

# Author

Vijayalakshmi Gogineni

B.Tech Computer Science and Engineering

