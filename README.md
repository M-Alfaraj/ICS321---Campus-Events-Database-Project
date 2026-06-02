# ICS321---Campus-Events-Database-Project
The Campus Events Database is a MySQL system for managing university events. It organizes sports, academic, social, and religious events, linking them to venues, departments, and organizers. It includes event approvals, sub-events, and automated notifications using triggers, ensuring structured and efficient event management.

Group Information
1. Mohammed Alfaraj – 202323090 – Section 1
2. Redha Alturaik – 202323010 – Section 3
- Group: Project M11

## Project Overview
This project implements a Campus Events Database System designed to manage and organize different types of university events such as sports, social, religious, and academic activities. The system supports event scheduling, approvals, sub-event management, and notifications to relevant departments.

Each event has a defined time range, venue, responsible department, and organizer. The system ensures structured handling of events with proper relationships between people, departments, venues, and event classifications.

## System Features
- Event Management
- Create and store events with start and end times
- Classify events into:
- Sports
- Social
- Religious
- Academic
- Assign each event to a specific venue and academic department
- Link a responsible person for each event
- Sub-Event Management
- Each event can contain multiple sub-events
- Each sub-event has:
- Start time
- Allocated duration
- Person in charge
- Event Approval System
- Events start in pending status

Events can be:
- Approved
- Rejected (with justification stored)
- Only approved events trigger system notifications
- Notification System
- When an event is approved, notifications are automatically generated for:
- Maintenance
- Office Services
- Security

## Database Design Overview

The system follows a relational database structure with proper normalization (BCNF). It includes strong and weak entity relationships and specialization for event and venue types.

### Main Entities:
- AcademicDepartment
- Person
- Venue
- Event
- EventApproval
- SubEvent
- NotificationLog
- Event Specialization
- SportsEvent
- SocialEvent
- ReligiousEvent
- AcademicEvent
- Venue Specialization
- SportsArea
- LectureHall
- ConferenceHall
- PublicSpace

### Key Business Rules & Constraints
- Events must last no more than 3 days (72 hours)
- Events must be scheduled between 8:00 AM and 12:00 AM
- End time must always be after start time
- Each person belongs to a defined role:
- Student, Staff, Faculty, or Dependent
- Each event must be linked to a department and venue
- Sub-events must stay within their parent event timeline

### Implementation Highlights
- Trigger System
- A trigger automatically logs notifications when an event is approved:

### Sends notifications to:
- Maintenance
- Office Services
- Security
- Stores notification records in NotificationLog
- View: Upcoming Events

### A database view was created to display upcoming events with:

- Event details
- Venue name
- Department
- Responsible person
- Stored Procedure

### A stored procedure was used to initialize and populate the database with test data, including:

- Departments
- People
- Venues
- Events
- Event classifications
- Approvals and sub-events

## Testing

The system was tested using multiple SQL queries to verify correctness:

- Example Queries Tested
- Listing all events with department, venue, and responsible person
- Retrieving sports events with venue and surface details
- Viewing upcoming events through a database view
- Counting events by department and category

All queries returned correct relational outputs confirming schema integrity and proper joins.

## Tools & Technologies Used
- MySQL Server & Workbench 8.0
- Draw.io (EER Diagram Design)
- SQL (DDL, DML, Triggers, Views, Procedures)
- ZyBooks
- MySQL Documentation
- W3Schools

## Assumptions
- Events are organized only by students, staff, faculty, or dependents
- Event duration is limited to 3 days maximum
- Events must occur between 8 AM and 12 AM
- Approval status defaults to “pending”
- Sub-events can have different organizers from the main event
- A person may exist without a department

## Work Distribution
### Mohammed Alfaraj
- Logical design
- BCNF conversion
- Table creation
- Insert statements

### Redha Alturaik
- EER diagram design
- Insert statements
- Stored procedures
- Trigger implementation
- Testing

##  Conclusion

This project successfully implements a structured Campus Events Management System using relational database principles. It demonstrates proper normalization, entity relationships, constraints, triggers, and views to ensure data integrity and automation of event workflows.
