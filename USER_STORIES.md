# User Stories

This document breaks down epics into actionable, testable user stories with clear value propositions.

---

## Epic 1: User Authentication & Authorization

### US-001: User Registration with Email Verification

**As a** new user  
**I want to** register with my email and verify my account  
**So that** I can access the platform securely

**Story Points:** 5

**Then:** User can register, receive verification email, and verify account to log in

---

### US-002: User Login with Email/Password

**As a** registered user  
**I want to** log in with my email and password  
**So that** I can access my account

**Story Points:** 3

**Then:** User can log in with valid credentials and see dashboard

---

### US-003: Password Reset Functionality

**As a** user who forgot my password  
**I want to** reset my password via email  
**So that** I can regain access to my account

**Story Points:** 3

**Then:** User can request password reset and set new password

---

### US-004: Role-Based Access Control

**As an** administrator  
**I want to** assign roles to users  
**So that** users have appropriate access levels

**Story Points:** 8

**Then:** Admin can assign roles (Admin, PM, Member, Viewer) and access is enforced

---

### US-005: Session Management and Logout

**As a** user  
**I want to** log out and have my session terminated  
**So that** my account is secure when I leave

**Story Points:** 2

**Then:** User can log out and is redirected to login page

---

## Epic 2: Project Boards

### US-006: Create New Project

**As a** project manager  
**I want to** create a new project with name and description  
**So that** I can start organizing tasks

**Story Points:** 3

**Then:** Project is created and appears in project list

---

### US-007: Manage Board Columns

**As a** project manager  
**I want to** add, edit, and delete board columns  
**So that** I can customize the workflow

**Story Points:** 5

**Then:** Columns can be added/edited/deleted and persist after refresh

---

### US-008: Create Tasks

**As a** team member  
**I want to** create tasks with title and description  
**So that** work can be documented and tracked

**Story Points:** 3

**Then:** Task is created with title, description, and appears in correct column

---

### US-009: Drag-and-Drop Tasks

**As a** team member  
**I want to** drag tasks between columns  
**So that** I can update task status visually

**Story Points:** 5

**Then:** Tasks can be dragged to different columns and status updates

---

### US-010: Assign Tasks to Members

**As a** project manager  
**I want to** assign tasks to team members  
**So that** work is distributed properly

**Story Points:** 3

**Then:** Task shows assignee and assignee receives notification

---

### US-011: Set Task Priority

**As a** project manager  
**I want to** set task priority levels  
**So that** important tasks are highlighted

**Story Points:** 2

**Then:** Priority is displayed on task card with visual indicator

---

### US-012: Add Due Dates

**As a** team member  
**I want to** add due dates to tasks  
**So that** deadlines are clear

**Story Points:** 3

**Then:** Due date is displayed and stored with task

---

### US-013: Task Templates

**As a** project manager  
**I want to** create task templates  
**So that** common tasks can be created quickly

**Story Points:** 5

**Then:** Templates can be created and used to pre-fill new tasks

---

### US-014: Filter and Search Tasks

**As a** team member  
**I want to** filter and search tasks  
**So that** I can find specific tasks quickly

**Story Points:** 5

**Then:** Tasks can be filtered by assignee, priority, status, and searched by text

---

### US-015: Archive Completed Tasks

**As a** project manager  
**I want to** archive completed tasks  
**So that** the board stays clean

**Story Points:** 3

**Then:** Tasks can be archived and restored if needed

---

## Epic 3: Real-Time Collaboration

### US-016: Real-Time Board Updates

**As a** team member  
**I want to** see board updates in real-time  
**So that** I always see current state

**Story Points:** 8

**Then:** Changes made by one user appear instantly for all users

---

### US-017: Live Task Status Changes

**As a** team member  
**I want to** see task status changes immediately  
**So that** I know the latest progress

**Story Points:** 5

**Then:** Status changes propagate to all connected clients in < 1 second

---

### US-018: Comments with @Mentions

**As a** team member  
**I want to** comment on tasks and mention teammates  
**So that** I can have discussions and notify people

**Story Points:** 5

**Then:** Comments can be added with @mentions and notifications sent

---

### US-019: Real-Time Notifications

