# Test Suite — Inner Haven Counseling Platform

**Last Updated:** 2026-06-03
**Total Test Cases:** 72 across 7 requirements

---

## REQ-001: Appointment Management

Students can book, update, and cancel appointments. Counselors can approve, decline, cancel, complete, and reschedule. The system enforces role-based access, prevents double-booking, rejects past dates, and generates Google Meet links for online sessions on approval.

### Booking (Create)
- [SCHD-0001](REQ-001-Appointment-Management/SCHD-0001.md) — Student creates a new appointment (online — happy path)
- [SCHD-0002](REQ-001-Appointment-Management/SCHD-0002.md) — Student creates a new appointment (in-person — happy path)
- [SCHD-0003](REQ-001-Appointment-Management/SCHD-0003.md) — Student attempts to book with missing required fields
- [SCHD-0004](REQ-001-Appointment-Management/SCHD-0004.md) — Student attempts to book a past date
- [SCHD-0005](REQ-001-Appointment-Management/SCHD-0005.md) — Student attempts to book an already-taken timeslot
- [SCHD-0006](REQ-001-Appointment-Management/SCHD-0006.md) — Unauthenticated user attempts to access the booking page

### Listing & Viewing
- [SCHD-0007](REQ-001-Appointment-Management/SCHD-0007.md) — Student views their appointments list
- [SCHD-0008](REQ-001-Appointment-Management/SCHD-0008.md) — Counselor views their appointments list
- [SCHD-0009](REQ-001-Appointment-Management/SCHD-0009.md) — Student views appointment detail and meeting link

### Editing (Student)
- [SCHD-0010](REQ-001-Appointment-Management/SCHD-0010.md) — Student edits a pending appointment (change reason)
- [SCHD-0011](REQ-001-Appointment-Management/SCHD-0011.md) — Student edits a pending appointment (change date and time)
- [SCHD-0012](REQ-001-Appointment-Management/SCHD-0012.md) — Student edits a pending appointment (change session mode)
- [SCHD-0013](REQ-001-Appointment-Management/SCHD-0013.md) — Student attempts to edit with a taken timeslot

### Cancelling
- [SCHD-0014](REQ-001-Appointment-Management/SCHD-0014.md) — Student cancels a pending appointment
- [SCHD-0015](REQ-001-Appointment-Management/SCHD-0015.md) — Student cancels an approved appointment
- [SCHD-0016](REQ-001-Appointment-Management/SCHD-0016.md) — Counselor cancels an appointment

### Status Management (Counselor)
- [SCHD-0017](REQ-001-Appointment-Management/SCHD-0017.md) — Counselor approves a pending online appointment
- [SCHD-0018](REQ-001-Appointment-Management/SCHD-0018.md) — Counselor approves a pending in-person appointment
- [SCHD-0019](REQ-001-Appointment-Management/SCHD-0019.md) — Counselor approves online appointment without Google connection
- [SCHD-0020](REQ-001-Appointment-Management/SCHD-0020.md) — Counselor completes a past approved appointment
- [SCHD-0021](REQ-001-Appointment-Management/SCHD-0021.md) — Counselor reschedules a pending appointment
- [SCHD-0024](REQ-001-Appointment-Management/SCHD-0024.md) — Counselor declines a pending appointment

### UI & Edge Cases
- [SCHD-0022](REQ-001-Appointment-Management/SCHD-0022.md) — Empty appointments list
- [SCHD-0023](REQ-001-Appointment-Management/SCHD-0023.md) — Availability slots grid — empty states
- [SCHD-0025](REQ-001-Appointment-Management/SCHD-0025.md) — Student cannot edit an approved or completed appointment

---

## REQ-002: Notifications

Users receive notifications for booking events (request, approval, decline, reschedule, session notes). Notifications appear in a bell dropdown and a dedicated page. Opening the dropdown or page automatically marks all as read. The unread badge updates in real time.

### Bell & Badge
- [NOTI-0001](REQ-002-Notifications/NOTI-0001.md) — Student views the notification bell with unread count
- [NOTI-0002](REQ-002-Notifications/NOTI-0002.md) — Student opens the notification bell dropdown
- [NOTI-0003](REQ-002-Notifications/NOTI-0003.md) — Marks all notifications as read via bell dropdown
- [NOTI-0011](REQ-002-Notifications/NOTI-0011.md) — Notification badge shows 99+ for large unread counts

### Notifications Page
- [NOTI-0004](REQ-002-Notifications/NOTI-0004.md) — Student views the full notifications page
- [NOTI-0010](REQ-002-Notifications/NOTI-0010.md) — Notifications page shows empty state

### Notification Navigation
- [NOTI-0005](REQ-002-Notifications/NOTI-0005.md) — Student clicks a booking notification and navigates to appointment
- [NOTI-0006](REQ-002-Notifications/NOTI-0006.md) — Student clicks a session notes notification and navigates to messaging
- [NOTI-0007](REQ-002-Notifications/NOTI-0007.md) — Student sees an approved notification with Google Meet link

### Role-Based
- [NOTI-0008](REQ-002-Notifications/NOTI-0008.md) — Counselor receives a booking request notification

### Notification Triggers
- [NOTI-0012](REQ-002-Notifications/NOTI-0012.md) — Student receives a booking rescheduled notification
- [NOTI-0013](REQ-002-Notifications/NOTI-0013.md) — Notifications update in real time without page refresh

---

## REQ-003: Counselor Directory & Availability

Students can browse the counselor directory to view profiles and check availability across dates (up to 42 days ahead). The system handles empty states gracefully. Counselors can view and update their own schedule but cannot access other counselors' data.

### Directory Browsing
- [CNSL-0001](REQ-003-Counselor-Directory/CNSL-0001.md) — Student browses the counselor directory (happy path)

### Availability & Booking Calendar
- [CNSL-0002](REQ-003-Counselor-Directory/CNSL-0002.md) — Student views available time slots for a selected date
- [CNSL-0003](REQ-003-Counselor-Directory/CNSL-0003.md) — Student browses the booking calendar across multiple weeks

### Empty States
- [CNSL-0004](REQ-003-Counselor-Directory/CNSL-0004.md) — Empty counselor directory
- [CNSL-0005](REQ-003-Counselor-Directory/CNSL-0005.md) — No time slots available — counselor's off-day

### Counselor View
- [CNSL-0006](REQ-003-Counselor-Directory/CNSL-0006.md) — Counselor views their own schedule and upcoming appointments
- [CNSL-0007](REQ-003-Counselor-Directory/CNSL-0007.md) — Counselor updates their weekly availability schedule

---

## REQ-004: Google Meet Integration

Counselors can connect their Google account to enable Google Meet link generation. When a counselor approves an online appointment, a Meet space is automatically created. In-person appointments do not generate Meet links. The system detects expired connections and prompts reconnection.

### OAuth Connection Lifecycle
- [GMET-0001](REQ-004-Google-Meet/GMET-0001.md) — Counselor connects Google account (happy path)
- [GMET-0009](REQ-004-Google-Meet/GMET-0009.md) — Counselor denies Google OAuth consent
- [GMET-0006](REQ-004-Google-Meet/GMET-0006.md) — Counselor disconnects Google account

### Meet Link Generation
- [GMET-0002](REQ-004-Google-Meet/GMET-0002.md) — Google Meet link appears when counselor approves online appointment
- [GMET-0003](REQ-004-Google-Meet/GMET-0003.md) — No Meet link generated for in-person appointment approval
- [GMET-0008](REQ-004-Google-Meet/GMET-0008.md) — Student views Meet link on approved online appointment

### Error Handling
- [GMET-0004](REQ-004-Google-Meet/GMET-0004.md) — Counselor prompted to reconnect Google when connection expires
- [GMET-0005](REQ-004-Google-Meet/GMET-0005.md) — Temporary Meet creation failure — counselor can retry

---

## REQ-005: Anonymous Help Request

Students can start anonymous conversations with counselors without revealing their identity. Messages are private. Both parties can exchange messages and close the conversation when done. Counselors see only a pseudonymous label. Only one active conversation per student-counselor pair.

### Starting Conversations
- [ANON-0001](REQ-005-Anonymous-Help/ANON-0001.md) — Student starts an anonymous conversation with a counselor
- [ANON-0005](REQ-005-Anonymous-Help/ANON-0005.md) — Student cannot start a duplicate conversation with the same counselor

### Messaging
- [ANON-0002](REQ-005-Anonymous-Help/ANON-0002.md) — Student and counselor exchange messages in an active conversation

### Closing Conversations
- [ANON-0003](REQ-005-Anonymous-Help/ANON-0003.md) — Student closes their anonymous conversation

### Viewing & Managing
- [ANON-0006](REQ-005-Anonymous-Help/ANON-0006.md) — Counselor views their queue of active anonymous conversations
- [ANON-0007](REQ-005-Anonymous-Help/ANON-0007.md) — Student views their list of anonymous conversations

---

## REQ-006: Authentication

Users can sign up with email/password or Google, log in, reset forgotten passwords, and log out. Email verification is required after sign-up. Unauthenticated users are redirected to the login page when accessing protected routes.

### Registration & Verification
- [AUTH-0001](REQ-006-Authentication/AUTH-0001.md) — New user signs up with email and password
- [AUTH-0007](REQ-006-Authentication/AUTH-0007.md) — Sign-up fails with an already-registered email

### Login & Logout
- [AUTH-0002](REQ-006-Authentication/AUTH-0002.md) — User logs in with email and password
- [AUTH-0006](REQ-006-Authentication/AUTH-0006.md) — Login fails with incorrect password
- [AUTH-0004](REQ-006-Authentication/AUTH-0004.md) — User logs out and is redirected to login

### Password Recovery
- [AUTH-0003](REQ-006-Authentication/AUTH-0003.md) — User resets forgotten password

### Access Control
- [AUTH-0005](REQ-006-Authentication/AUTH-0005.md) — Unauthenticated user is redirected to login

---

## REQ-007: Counselor Notes

Counselors can create and edit private session notes for each appointment, including general notes, recommendations, and follow-up plans. Students can view the notes but cannot edit them. A notification is sent to the student when notes are first created.

### Creating & Editing
- [NOTE-0001](REQ-007-Counselor-Notes/NOTE-0001.md) — Counselor creates a session note for an appointment
- [NOTE-0002](REQ-007-Counselor-Notes/NOTE-0002.md) — Counselor edits an existing session note

### Student Access
- [NOTE-0003](REQ-007-Counselor-Notes/NOTE-0003.md) — Student views session notes from their counselor
- [NOTE-0004](REQ-007-Counselor-Notes/NOTE-0004.md) — Student cannot create or edit session notes

### Multi-Appointment & Notifications
- [NOTE-0005](REQ-007-Counselor-Notes/NOTE-0005.md) — Counselor views notes across multiple appointments
- [NOTE-0006](REQ-007-Counselor-Notes/NOTE-0006.md) — Student receives notification when counselor creates a note
