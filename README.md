# Leave Management System – ServiceNow

A ServiceNow-based Leave Management System designed to automate employee leave requests, approvals, notifications, and leave tracking.

## 📌 Project Overview

The Leave Management System provides a centralized platform for employees to apply for leave and allows managers/HR to review, approve, or reject requests.

The application is designed using **ServiceNow App Engine Studio** and uses tables, roles, business rules, notifications, workflows/flows, and reports to automate the leave management process.

## 🎯 Objectives

- Allow employees to submit leave applications.
- Allow managers/HR to approve or reject leave requests.
- Maintain employee and department information.
- Track leave balances and leave history.
- Prevent invalid leave applications.
- Send notifications when leave requests are submitted or updated.
- Provide dashboards and reports for HR and management.
- Implement role-based access control.

## 🛠️ Technology Stack

- **Platform:** ServiceNow
- **Application:** Leave Management System
- **Development:** App Engine Studio
- **Server-side scripting:** JavaScript
- **Automation:** Flow Designer / Workflows
- **Database:** ServiceNow Tables
- **Security:** Roles and ACLs
- **Reporting:** ServiceNow Reports and Dashboards

## 🗂️ Main Tables

### 1. Employee

Stores employee information.

Important fields:

- Employee ID – `LMS + 7-digit number`
- Employee Name
- Department – Reference
- Designation
- Email
- Phone Number
- Manager – Reference to Employee
- Date of Joining
- Status – Active / Inactive / On Leave

### 2. Department

Stores department details such as department name, department head, and description.

### 3. Holiday Calendar

Stores organization holidays that are considered when calculating leave duration.

### 4. Leave Application

Stores employee leave requests.

Typical fields:

- Leave Number
- Employee
- Leave Type
- Start Date
- End Date
- Number of Days
- Reason
- Status
- Manager Comments
- HR Comments
- Approved/Rejected Date

## 🔄 Leave Approval Process

```text
Employee
   │
   ▼
Submit Leave Application
   │
   ▼
Validate Leave Request
   │
   ├── Invalid ──► Reject / Ask for Correction
   │
   ▼
Manager Review
   │
   ├── Reject ──► Employee Notified
   │
   ▼
Approve
   │
   ▼
Update Leave Balance
   │
   ▼
Employee Notified
```

## 👥 Roles

| Role | Responsibility |
|---|---|
| Admin | Full application administration |
| HR | Manage employees, leave records, and reports |
| Manager | Review and approve/reject team leave |
| Employee | Apply for leave and view own requests |

## 🔐 Access Control

The application uses ServiceNow roles and ACLs to control access.

### Employee

- Create leave requests
- View own leave requests
- Update eligible requests
- Cannot delete approved/rejected records

### Manager

- View team leave requests
- Approve/reject leave requests
- Add approval comments

### HR

- Manage employee and leave records
- View organization-wide leave information
- Manage reports

### Admin

- Full CRUD access
- Configure application components
- Manage roles and security

## ⚙️ Automation

The system can use ServiceNow Flow Designer/Business Rules for:

- Leave request validation
- Manager approval
- Leave balance updates
- Approval/rejection notifications
- Status updates
- Preventing overlapping leave
- Calculating leave duration

## 📊 Reports & Dashboard

Suggested reports include:

- Total Leave Requests
- Pending Approvals
- Approved Leaves
- Rejected Leaves
- Leave by Department
- Leave by Leave Type
- Employee Leave History
- Monthly Leave Trends

## 📁 Suggested GitHub Structure

```text
Leave-Management-ServiceNow/
│
├── README.md
│
├── scripts/
│   └── LeaveManagementUtils.js
│
├── docs/
│   ├── application-overview.md
│   └── database-design.md
│
└── screenshots/
    └── README.md
```

> Note: ServiceNow application records are normally stored inside a ServiceNow instance. The JavaScript file in this repository contains representative server-side logic that can be adapted into Script Includes/Business Rules in the instance.

## 🚀 How to Use

1. Open your ServiceNow developer instance.
2. Create/open the Leave Management application in App Engine Studio.
3. Create the required tables and fields.
4. Configure roles and ACLs.
5. Create the required flows/business rules.
6. Configure notifications.
7. Create reports and dashboards.
8. Test the application using Employee, Manager, HR, and Admin roles.

## 🧪 Testing Scenarios

- Employee submits a valid leave request.
- Employee submits a request with an invalid date range.
- Employee submits overlapping leave.
- Manager approves a request.
- Manager rejects a request.
- Employee receives approval/rejection notification.
- Leave balance is updated after approval.
- Employee cannot access another employee's private leave information.
- HR can view organization-wide leave data.

## 📌 Future Enhancements

- Automatic leave balance allocation.
- Mobile-friendly leave application.
- Holiday-aware working-day calculation.
- Multi-level approval.
- Advanced HR analytics.
- Integration with email/calendar systems.
- Employee self-service dashboard.

## 👨‍💻 Project

**Project:** Leave Management System  
**Platform:** ServiceNow  
**Purpose:** Automating employee leave application and approval processes
