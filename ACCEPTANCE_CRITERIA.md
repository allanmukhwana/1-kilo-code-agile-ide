# Acceptance Criteria

This document defines success conditions for each user story based on code behavior and expected functionality.

---

## Epic 1: User Authentication

### US-001: User Registration with Email Verification

**Given** a new user wants to create an account
**When** they submit the registration form with valid email
**Then** a verification email is sent to their address
**And** their account is created in "pending verification" state

**Verification:**
- [ ] User receives verification email within 30 seconds
- [ ] Email contains working verification link
- [ ] Account cannot be accessed until verified
- [ ] Duplicate email shows error message

---

### US-002: User Login with Email/Password

**Given** a registered user with verified email
**When** they enter correct email and password
**Then** they are granted access to the application
**And** a session token is created

**Verification:**
- [ ] Valid credentials redirect to dashboard
- [ ] Invalid credentials show error message
- [ ] Session persists across page refreshes
- [ ] Failed attempts are rate-limited

---

### US-003: Password Reset Functionality

**Given** a user who forgot their password
**When** they request password reset
**Then** they receive a reset email with time-limited link

**Verification:**
- [ ] Reset email arrives within 60 seconds
- [ ] Link expires after 1 hour
- [ ] Password can be changed via link
- [ ] Old password no longer works after reset

---

### US-004: Role-Based Access Control

**Given** users with different roles
**When** they attempt various actions
**Then** permissions are enforced based on role

**Verification:**
- [ ] Admin can access all features
- [ ] Project Manager can manage projects
- [ ] Team Member can view and edit assigned tasks
- [ ] Stakeholder has read-only access

---

## Epic 2: Project Boards

### US-006: Create New Project

**Given** a Project Manager
**When** they create a new project with name and description
**Then** the project appears in their project list
**And** they can configure board settings

**Verification:**
- [ ] Project is saved to database
- [ ] Project appears in project list
- [ ] Owner can add team members
- [ ] Default columns are created

---

### US-007: Board Column Management

**Given** a project owner
**When** they add/edit/delete columns
**Then** the changes reflect immediately on the board

**Verification:**
- [ ] New column appears instantly
- [ ] Column can be renamed
- [ ] Column can be deleted (tasks move or archive)
- [ ] Column order is customizable

---

### US-008: Create Tasks

**Given** a team member
**When** they create a task with title
**Then** task appears in the selected column

**Verification:**
- [ ] Task is saved to database
- [ ] Task title displays on card
- [ ] Task can include description (rich text)
- [ ] Task gets unique ID

---

### US-009: Drag-and-Drop Tasks

**Given** a user viewing the board
**When** they drag a task to a different column
**Then** task moves to new column
**And** status updates automatically

**Verification:**
- [ ] Drag operation is smooth (no jank)
- [ ] Drop zone is clearly indicated
- [ ] Status updates in database
- [ ] Change syncs to other users

---

### US-010: Assign Tasks

**Given** a task creator
**When** they assign a team member
**Then** assignee is displayed on the task card
**And** assignee receives notification

**Verification:**
- [ ] Assignee name shows on card
- [ ] Assignee can see task in their dashboard
- [ ] Assignment is saved to database
- [ ] Notification is sent to assignee

---

### US-011: Set Task Priority

**Given** a task with assignee
**When** priority is set to High or Urgent
**Then** task is visually highlighted
**And** sorted higher in column

**Verification:**
- [ ] Priority badge displays correctly
- [ ] Color coding is visible
- [ ] Sort by priority works
- [ ] Urgent tasks have special indicator

---

### US-012: Due Dates and Reminders

**Given** a task with due date
**When** the due date approaches
**Then** reminders are sent to assignee

**Verification:**
- [ ] Date picker works correctly
- [ ] Due date displays on card
- [ ] Reminder sent 24h before
- [ ] Overdue tasks are visually marked

---

## Epic 3: Real-Time Collaboration

### US-016: Real-Time Board Updates

**Given** multiple users viewing the same board
**When** one user makes a change
**Then** all other users see the update instantly

**Verification:**
- [ ] Update appears within 500ms for other users
- [ ] No page refresh required
- [ ] Works across different browsers
- [ ] Handles disconnection gracefully

---

### US-017: Live Task Status Changes

**Given** a user moving a task
**When** the task status changes
**Then** all connected clients update immediately

**Verification:**
- [ ] Status change syncs in real-time
- [ ] Animation shows the move
- [ ] Timestamp is recorded
- [ ] Activity log is updated

---

### US-018: Comments and @Mentions

**Given** a task with comments enabled
**When** user adds comment with @mention
**Then** mentioned user receives notification

**Verification:**
- [ ] Comment saves successfully
- [ ] @mention triggers notification
- [ ] Comments display in thread
- [ ] Markdown formatting works

---

### US-019: Real-Time Notifications

**Given** a user with notifications enabled
**When** relevant activity occurs
**Then** notification appears in real-time

**Verification:**
- [ ] Notification appears in notification center
- [ ] Unread count updates
- [ ] Click navigates to relevant item
- [ ] Notifications are persistent

---

### US-020: Online Presence Indicators

**Given** users on the application
**When** they are active
**Then** their online status is visible to others

**Verification:**
- [ ] Green dot shows for online users
- [ ] Status updates when user goes away
- [ ] "Last seen" shows for offline users
- [ ] Accurate across all clients

---

## Epic 4: User & Team Management

### US-022: Invite Users to Projects

**Given** a Project Manager
**When** they invite a user to a project
**Then** user receives invitation
**And** can accept to join

**Verification:**
- [ ] Invitation email sent
- [ ] User appears in pending list
- [ ] Accept/decline works
- [ ] Permissions applied on accept

---

### US-023: Manage User Roles

**Given** an Administrator
**When** they change a user's role
**Then** new permissions take effect immediately

**Verification:**
- [ ] Role change saves to database
- [ ] UI updates immediately
- [ ] User can access new features
- [ ] Previous permissions revoked

---

## Epic 5: Notifications

### US-027: In-App Notification Center

**Given** a user with notifications
**When** they click the notification bell
**Then** they see a list of recent notifications

**Verification:**
- [ ] Notification panel opens
- [ ] All relevant notifications show
- [ ] Click marks as read
- [ ] Clear all works

---

### US-028: Email Notifications

**Given** a user with email notifications enabled
**When** relevant activity occurs
**Then** they receive an email

**Verification:**
- [ ] Email delivered to correct address
- [ ] Email content is readable
- [ ] Unsubscribe link works
- [ ] Correct frequency (not too many)

---

## Epic 6: Dashboard & Reporting

### US-032: Personal Task Dashboard

**Given** a logged-in user
**When** they view their dashboard
**Then** they see all their assigned tasks

**Verification:**
- [ ] Dashboard loads in < 2 seconds
- [ ] Shows tasks from all projects
- [ ] Tasks grouped by status
- [ ] Quick filters work

---

### US-033: Project Progress Overview

**Given** a Project Manager
**When** they view project progress
**Then** they see completion percentage and trends

**Verification:**
- [ ] Progress chart displays correctly
- [ ] Percentage is accurate
- [ ] Updates in real-time
- [ ] Export to PDF works

---

## Common Acceptance Criteria

### Performance
- Page load time < 2 seconds
- API response time < 500ms
- Real-time sync < 500ms

### Security
- All endpoints require authentication
- Passwords are hashed
- CSRF protection enabled
- XSS prevention in place

### Accessibility
- WCAG 2.1 AA compliant
- Keyboard navigation works
- Screen reader compatible

### Browser Support
- Chrome (latest 2 versions)
- Firefox (latest 2 versions)
- Safari (latest 2 versions)
- Edge (latest 2 versions)
