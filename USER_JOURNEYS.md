# User Journeys

This document maps critical user paths for the Task Management App based on core features: **user authentication, project boards, and real-time collaboration**.

---

## Journey 1: New User Onboarding

### Description
A new team member joins and needs to get set up with the task management system.

### Trigger
New team member is added to the project

### Steps
1. **Receive invitation** - User receives email invitation with signup link
2. **Create account** - User clicks link, enters name, creates password
3. **Email verification** - User verifies email address
4. **First login** - User logs in with credentials
5. **View dashboard** - User sees personal task dashboard with assigned tasks
6. **Complete profile** - User adds avatar and preferences

### Success Criteria
- [ ] User can create account and log in
- [ ] User can view their assigned tasks
- [ ] User receives proper role-based permissions

---

## Journey 2: Create and Manage Project Board

### Description
A Project Manager creates a new project board with columns and templates.

### Trigger
New project requires task tracking setup

### Steps
1. **Navigate to projects** - Project Manager clicks "New Project"
2. **Define project** - Enter project name, description, and team members
3. **Create columns** - Set up board columns (To Do, In Progress, Review, Done)
4. **Configure templates** - Add task templates for common task types
5. **Invite team** - Add team members to the project
6. **Set permissions** - Configure access levels for each member

### Success Criteria
- [ ] Project board is created with custom columns
- [ ] All team members can access the board
- [ ] Permissions are correctly applied

---

## Journey 3: Task Creation and Assignment

### Description
A Project Manager creates tasks and assigns them to team members.

### Trigger
Work needs to be planned and distributed

### Steps
1. **Open project board** - Navigate to the relevant project
2. **Create task** - Click "Add Task" and enter task details
3. **Add description** - Include requirements, links, and context
4. **Set priority** - Mark as Low, Medium, High, or Urgent
5. **Assign to member** - Select team member from dropdown
6. **Set deadline** - Add due date and time
7. **Add to column** - Task appears in appropriate column

### Success Criteria
- [ ] Task is created with all details
- [ ] Assignee receives notification
- [ ] Task appears in correct column

---

## Journey 4: Real-Time Task Updates

### Description
Team members collaborate on tasks with real-time updates.

### Trigger
Team is working on tasks simultaneously

### Steps
1. **View board** - Team members see the project board
2. **Update task status** - Member drags task to new column
3. **Real-time sync** - All team members see the change instantly
4. **Add comment** - Member adds comment or question
5. **Receive notification** - Other members get notified
6. **Mention teammate** - Member @mentions another user
7. **Thread discussion** - Team discusses in comment thread

### Success Criteria
- [ ] Status changes appear in real-time for all users
- [ ] Comments sync instantly
- [ ] Notifications are delivered

---

## Journey 5: Stakeholder Review

### Description
An external stakeholder views project progress and provides feedback.

### Trigger
Stakeholder needs to review deliverables or progress

### Steps
1. **Receive access** - Admin grants stakeholder read-only access
2. **View dashboard** - Stakeholder sees project overview
3. **Review tasks** - Views tasks and their status
4. **Add comment** - Stakeholder leaves feedback on tasks
5. **View reports** - Access progress charts and summaries

### Success Criteria
- [ ] Stakeholder can view project progress
- [ ] Stakeholder can leave comments
- [ ] Stakeholder cannot modify tasks

---

## Journey 6: User Administration

### Description
An Administrator manages users and system settings.

### Trigger
System needs user management or configuration

### Steps
1. **Access admin panel** - Navigate to admin settings
2. **View users** - See all registered users
3. **Manage roles** - Assign or change user roles
4. **Configure settings** - Set system-wide preferences
5. **View audit logs** - Review user activity
6. **Handle security** - Manage authentication settings

### Success Criteria
- [ ] Admin can view and manage all users
- [ ] Role changes take effect immediately
- [ ] Audit logs capture all actions

---

## Critical Path Summary

| Journey | Frequency | Complexity | Priority |
|---------|-----------|------------|----------|
| New User Onboarding | Low | Medium | High |
| Create Project Board | Low | High | High |
| Task Creation | High | Medium | Critical |
| Real-Time Updates | High | High | Critical |
| Stakeholder Review | Medium | Low | Medium |
| User Administration | Low | Medium | Medium |
