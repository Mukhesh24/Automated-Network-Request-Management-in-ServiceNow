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

---

# Phase 3 — UI/UX Development & Customization

## Phase Overview

Phase 3 focuses on designing and customizing the ServiceNow user interface for the Automated Network Request Management solution.

The phase covers Service Catalog creation, catalog variables, variable sets, navigation flow, and Catalog UI Policies to provide a structured and user-friendly request experience.

---

## Interface Design

The ServiceNow interface is customized to provide a simple and user-friendly experience for network requesters.

The interface design includes:

- Service Catalog and Catalog Item configuration
- Network Request form
- Requester Information variable set
- Catalog variables
- Auto-populated requester information
- Conditional field visibility
- Catalog UI Policies
- Service Portal navigation
- Request submission and status visibility

---

## Activity 1 — Creation of Service Catalog

### Description

A dedicated **Network Request** catalog item is created in ServiceNow to allow users to submit network service requests through the Service Catalog.

### Configuration

| Field | Configuration |
|---|---|
| Catalog Item | Network Request |
| Catalog | Service Catalog |
| Category | Network |
| Short Description | Network Request Management |

### Procedure

1. Navigate to **Application Navigator**.
2. Search for **Service Catalog**.
3. Navigate to **Service Catalog → Maintain Items**.
4. Click **New**.
5. Enter the name as **Network Request**.
6. Select **Service Catalog** as the Catalog.
7. Select **Network** as the Category.
8. Enter **Network Request Management** as the Short Description.
9. Save the Catalog Item.

---

## Activity 2 — Variables Configuration

### Description

Catalog variables are configured to collect the information required to process a network request.

Variables can be configured using different types such as:

- Single Line Text
- Multi Line Text
- Reference
- Multiple Choice

Additional properties such as mandatory, read-only, tooltip, example text, and auto-population can also be configured based on the requirement.

### Configuration Procedure

1. Open the **Network Request** Catalog Item.
2. Navigate to the **Variables** related list.
3. Click **New**.
4. Select the required variable type.
5. Enter the Question and Name.
6. Configure the Order value.
7. Configure Tooltip and Example Text where required.
8. Configure Mandatory and Read Only properties as required.
9. Configure Auto-populate when a variable depends on another variable.
10. Save the variable.

---

## Activity 3 — Variables Creation

The following variables are configured for the **Network Request** Catalog Item.

| S.No | Variable Name | Type | Choices / Values |
|---:|---|---|---|
| 1 | Requested For | Single Line Text | — |
| 2 | Mobile Number | Single Line Text | — |
| 3 | Type of Connection | Multiple Choice | New / Existing |
| 4 | Enter your Existing ID | Single Line Text | — |
| 5 | Total Amount | Single Line Text | — |
| 6 | Mode of Payment | Multiple Choice | UPI / CARD |
| 7 | Address | Single Line Text | — |

---

## Activity 4 — Variable Set Configuration

### Description

A **Requester Information** variable set is configured to improve form usability and organize requester-related information.

The variable set is associated with the **Network Request** Catalog Item.

### Variable Set Configuration

| Field | Configuration |
|---|---|
| Title | Requester Information |
| Internal Name | requester_information |
| Type | Single Row |
| Order | 50 |
| Display Title | Enabled |
| Layout | 2 Columns Wide |

### Variables in Requester Information

| S.No | Variable Name | Type | Reference / Configuration |
|---:|---|---|---|
| 1 | Opened on behalf of | Reference | User [sys_user] |
| 2 | Email ID | Single Line Text | Auto-populated from Opened on behalf of |
| 3 | User Name | Single Line Text | Auto-populated from Opened on behalf of |
| 4 | Phone Number | Single Line Text | Auto-populated from Opened on behalf of |

### Auto-Population

The requester information variables use the selected **Opened on behalf of** user to automatically populate related information.

For example:

```text
Opened on behalf of
        |
        v
   User [sys_user]
        |
        +----> Email ID
        |
        +----> User Name
        |
        +----> Phone Number

This reduces duplicate data entry and improves the consistency of requester information.

Activity 5 — Navigation Flow

The Navigation Flow provides a path for users to access and submit the Network Request through the ServiceNow Service Portal.

Request Flow
ServiceNow PDI
      |
      v
Service Portal
      |
      v
Search for Network Request
      |
      v
Network Request Catalog Item
      |
      v
Fill Required Details
      |
      v
Submit Request
      |
      v
Request Number Generated
      |
      v
User Receives Notification
Navigation Procedure
Log in to the ServiceNow PDI.
Open the Service Portal.
Navigate to the Service Catalog.
Search for Network Request.
Open the Network Request Catalog Item.
Fill in the required details.
Submit the request.
A new request is generated with a request number.
The user receives the relevant notification.
Activity 6 — Catalog UI Policy
Description

Catalog UI Policies are used to dynamically control the visibility of fields based on user selections.

For the Network Request Catalog Item, conditional logic is configured so that additional fields can appear when specific options are selected.

Scenario

When the user selects:

Type of Connection = Existing

the Enter your Existing ID field becomes visible.

Configuration
Property	Configuration
Applies to	Catalog Item
Catalog Item	Network Request
Condition	Type of Connection is Existing
UI Policy Action	Enter your Existing ID
Visible	True
Procedure
Navigate to the Network Request Catalog Item.
Open the Catalog UI Policies related list.
Click New.
Select Catalog Item as the applicable type.
Select Network Request as the Catalog Item.
Enter a suitable Short Description.
Configure the condition:
Type of Connection is Existing
Save the Catalog UI Policy.
Open the UI Policy Actions related list.
Create a new UI Policy Action.
Select the variable:
enter_your_existing_id
Set Visible = True.
Update the UI Policy.
Test the behavior on the Catalog form.
UI Policy Flow
User selects Type of Connection
                |
                v
       Is it "Existing"?
          /          \
        Yes           No
         |             |
         v             v
Show Existing ID    Keep field
     field            hidden
Phase 3 — UI/UX Outcome

Phase 3 establishes the user-facing interface for the Automated Network Request Management solution.

The phase delivers:

Network Request Service Catalog Item
Network Request variables
Requester Information variable set
Auto-populated requester details
Service Portal navigation flow
Conditional field visibility
Catalog UI Policy configuration
Structured and user-friendly request submission experience

The completed UI configuration provides the foundation for users to submit network requests through a standardized ServiceNow interface.