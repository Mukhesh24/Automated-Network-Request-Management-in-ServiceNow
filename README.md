# Automated-Network-Request-Management-in-ServiceNow
Automating network request management in ServiceNow enhances operational efficiency by streamlining workflows, reducing manual interventions, and ensuring real-time updates.

## Project Overview

Automated Network Request Management in ServiceNow is a ServiceNow-based solution designed to streamline the management of network-related service requests.

The project focuses on reducing manual effort, standardizing request handling, automating approvals and fulfilment activities, and improving visibility for requesters and fulfilment teams.

---

# Phase 1 — Ideation

## Business Objectives

The objective of this project is to streamline the end-to-end lifecycle of network-related service requests using ServiceNow.

The solution aims to:

- Reduce manual effort and human error
- Accelerate request fulfilment times
- Standardize workflows and approval processes
- Improve visibility and request tracking
- Enhance the end-user experience
- Ensure compliance with IT and security policies

---

## Functional Scope

Phase 1 identifies the functional areas required for the proposed solution:

- Service Catalog creation
- Network request form design
- Approval routing
- Flow Designer automation
- Email notifications
- Request status tracking
- Fulfilment task generation

---

## Stakeholders

| Stakeholder | Role | Needs / Expectations |
|---|---|---|
| End Users (Requesters) | Employees or teams requesting network services | Simple request submission, fast turnaround, status visibility |
| IT Admins | Manage ServiceNow configurations, integrations and workflows | Reliable automation, minimal manual intervention, easy maintenance |
| Network Fulfilment Team | Executes network changes and ensures infrastructure reliability | Complete request data, standardized processes, reduced manual tasks |
| Approvers | Managers or compliance officers approving requests | Policy enforcement, quick and informed approval workflows |

---

## Problem Statement

Network service requests can involve manual submission, incomplete information, manual routing, approval delays and limited visibility into request progress.

The proposed solution addresses this problem by providing a standardized ServiceNow-based process for submitting, approving, routing, fulfilling and tracking network requests.

---

## Brainstormed Ideas

### Request Intake

- Network service catalog
- Standard request categories
- Mandatory request variables
- Dynamic form fields

### Workflow Automation

- Flow Designer routing
- Automatic fulfilment task creation
- Assignment to network fulfilment team
- Automated request status updates

### Approval & Compliance

- Manager approval
- Network/security approval
- Policy validation
- Approval audit trail

### Communication & Visibility

- Email notifications
- Approval and rejection notifications
- Service Portal status tracking
- Fulfilment dashboard

---

## Idea Prioritization

The ideas were considered based on their impact and feasibility.

### High Priority

- Service Catalog with mandatory fields
- Flow Designer request routing
- Automated approval workflow

### Medium Priority

- Dynamic request forms
- Automated notifications
- Request status tracking

### Future Enhancement

- Advanced integrations with external network systems
- Automated network-device configuration

---

## Empathy Map

### Primary Persona

**End User / Network Requester**

| Area | Key Findings |
|---|---|
| Think & Feel | Wants a simple request process, worries about delays, values predictable fulfilment |
| See | Service Portal form, network categories, request status, notifications |
| Hear | IT requirements, manager policies, approval updates, network team requests |
| Say & Do | Selects service, enters details, submits request, checks status |
| Pain | Unclear request channels, missing information, slow approvals, repeated follow-ups |
| Gain | Standardized forms, automated approvals, automatic task assignment, status visibility, faster fulfilment |

---
## Proposed Solution

A ServiceNow-based automated network request management process that provides:

```text
End User
    |
    v
Service Portal
    |
    v
Network Request Catalog
    |
    v
Request Form
    |
    v
Approval Workflow
    |
    v
Fulfilment Task
    |
    v
Network Fulfilment Team
    |
    v
Request Completion
    |
    v
User Notification
```

---

# Phase 2 — Backend Development & Configurations

## Phase Overview

Phase 2 focuses on defining the backend structure, data architecture, technical architecture, functional requirements, non-functional requirements, and workflow design for the **Automated Network Request Management** solution in ServiceNow.

The phase establishes the foundation required for implementing the network request lifecycle in ServiceNow.

---

## Data Flow Diagram

The system flow covers:

```text
End User / Requester
        |
        v
Submit & Validate Request
        |
        v
Route Approval
        |
        v
Create Fulfilment Task
        |
        v
Network Fulfilment Team
        |
        v
Update Request Status
        |
        v
Request Completion
```

Supporting data is maintained through ServiceNow request, approval, task, and configuration records.

---

## User Stories

| User Type | User Story | Priority |
|---|---|---|
| End User / Requester | Submit a network service request through the Service Portal | High |
| End User / Requester | View the current status of a network request | High |
| Approver | Approve or reject a network request | High |
| Network Fulfilment Team | Receive automatically generated fulfilment tasks | High |
| IT Administrator | Maintain request fields, routing and workflow configuration | Medium |
| End User / Requester | Receive notifications during the request lifecycle | Medium |

---

## Functional Requirements

The Phase 2 solution defines the following functional requirements:

- Network request submission through Service Catalog
- Mandatory request variables
- Dynamic request forms
- Request validation
- Approval routing
- Flow Designer automation
- Automatic fulfilment task creation
- Assignment to the network fulfilment team
- Request status tracking
- Email notifications
- Network configuration and CI information

---

## Non-functional Requirements

The solution considers the following non-functional requirements:

- **Usability** — Simple and intuitive Service Portal request forms
- **Security** — Controlled access to request and approval information
- **Reliability** — Consistent recording of requests, approvals and fulfilment tasks
- **Performance** — Efficient form and workflow processing
- **Availability** — Accessible request management for authorized users
- **Scalability** — Ability to add new network request types and approval rules

---

## Technical Architecture

The proposed architecture uses ServiceNow as the central platform.

```text
                    SERVICENOW CLOUD

Service Portal
      |
      v
Service Catalog
      |
      v
Catalog Variables & Validation
      |
      v
Flow Designer
      |
      +-----------> Approval & Notifications
      |
      v
Fulfilment Task
      |
      v
Network Fulfilment Team
      |
      v
ServiceNow Request / Task / Audit Data
```

---

## Technology Stack

| Component | Technology / Configuration |
|---|---|
| User Interface | ServiceNow Service Portal / Service Catalog |
| Request Configuration | Catalog Items and Variables |
| Form Logic | UI Policies / Dynamic Form Behaviour |
| Workflow Automation | ServiceNow Flow Designer |
| Approval | ServiceNow Approval mechanisms |
| Notifications | ServiceNow Notifications |
| Database | ServiceNow platform tables / custom Network Request table |
| Data Storage | ServiceNow platform data storage |
| Infrastructure | ServiceNow Cloud Platform |

---

## Data Architecture

The Phase 2 data architecture defines a dedicated network request data structure.

### Network Request Table

| Property | Value |
|---|---|
| Label | Network Request |
| Name | `u_network_request` |

### Network Request Fields

| Field | Type | Purpose |
|---|---|---|
| Request Number | Auto Number | Unique request identifier |
| Requested For | Reference | Requesting user |
| Request Type | Choice | Type of network service |
| Access Level | Choice | Requested access level |
| Business Justification | String / HTML | Reason for the request |
| Related Configuration Item | Reference | Related network CI |
| Assignment Group | Reference | Network fulfilment group |
| Assigned To | Reference | Fulfilment team member |
| Approval Status | Choice | Approval state |
| Request Status | Choice | Current request state |
| Priority | Choice | Request priority |
| Created | Date/Time | Request creation timestamp |

---

## Backend Configuration

Phase 2 backend configuration includes:

- Network Request table creation
- Network request field configuration
- Request number generation
- Reference fields for users and fulfilment groups
- Choice fields for request and approval status
- Mandatory field configuration
- Dynamic form behaviour
- Request and task data management
- Approval and fulfilment workflow design

---

## Phase 2 Outcome

Phase 2 establishes the technical and backend foundation for implementing the **Automated Network Request Management** solution in ServiceNow.

The phase defines:

- Data flow
- User stories
- Functional requirements
- Non-functional requirements
- Technical architecture
- Technology stack
- Data architecture
- Network Request table
- Network Request fields
- Backend workflow and automation structure
