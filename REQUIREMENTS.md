System Requirements Specification (SRS)

College Student Affairs Management System

1. Introduction

1.1 Purpose

The purpose of the AI-Powered College Student Affairs Management System is to provide a centralized digital platform that facilitates communication and request management between college students and the Student Affairs Department.

The system aims to replace inefficient manual processes with an organized ticket-based workflow, enabling students to submit service requests, upload supporting documents, receive updates, and track the progress of their requests.

It also provides Student Affairs staff with tools to manage, categorize, process, and resolve student requests, while administrators can manage system resources and monitor overall performance.

An integrated AI Agent supports students by answering questions using the Knowledge Base, assisting with ticket classification and student information extraction, and extracting relevant information from uploaded payment receipts.

1.2 Project Scope

The system provides three main user roles:

- Student: Submits requests, uploads documents and payment receipts, and tracks submitted tickets.
- Student Affairs Staff: Reviews and processes tickets, updates their statuses, responds to students, and verifies payment receipts.
- Administrator: Manages staff accounts, permissions, Knowledge Base articles, and performance reports.

The system also includes AI-assisted services and email notifications to improve the efficiency of student support operations.

1.3 Objectives

The main objectives of the system are:

1. Digitize student service requests and inquiries.
2. Provide a centralized ticket management process.
3. Improve communication between students and Student Affairs staff.
4. Enable students to track requests through unique tracking codes.
5. Reduce manual work through AI-assisted operations.
6. Support payment receipt information extraction and verification.
7. Maintain organized records of ticket updates and interactions.
8. Provide administrators with tools for managing staff and monitoring system performance.

---

2. User Roles and Responsibilities

2.1 Student

Students are the primary users of the platform. They can:

- Access the system through their accounts.
- Submit service requests and create tickets.
- Provide ticket titles and descriptions.
- Upload supporting documents and payment receipts.
- Receive a unique tracking code for submitted tickets.
- Track ticket details and current status.
- View responses and resolution comments.
- Receive email notifications about relevant ticket updates.
- Interact with the AI Agent to ask questions and receive information based on the Knowledge Base.

2.2 Student Affairs Staff

Student Affairs staff are responsible for processing student requests. They can:

- Log in using their staff accounts.
- View submitted tickets.
- Filter tickets according to their categories.
- Review ticket descriptions and attached documents.
- Update ticket statuses.
- Add comments and responses to tickets.
- Resolve student requests.
- Review payment receipt information.
- Perform payment verification and record verification results.

2.3 Administrator

The Administrator is responsible for managing system resources and supervising administrative operations. The Administrator can:

- Manage Knowledge Base articles.
- Add, edit, and delete articles and regulations.
- Create and manage staff accounts.
- Activate and deactivate staff accounts.
- Manage staff permissions.
- Generate performance reports.
- Review ticket statistics and status distributions.
- Export reports in CSV format.

---

3. Functional Requirements

3.1 User Authentication and Account Management

- FR-01: The system shall allow users to log in using their registered credentials.
- FR-02: The system shall support three user roles: Student, Student Affairs Staff, and Administrator.
- FR-03: The system shall maintain user account information, including user ID, name, email, and password hash.
- FR-04: The system shall support account activation status to distinguish active and inactive accounts.
- FR-05: The system shall provide logout functionality.
- FR-06: The system shall restrict system operations according to the user's role and assigned permissions.

3.2 Student Ticket Management

- FR-07: The system shall allow students to create service tickets.
- FR-08: Each ticket shall contain a unique ticket ID, title, description, creation date, category, and status.
- FR-09: The system shall generate a unique tracking code for each submitted ticket.
- FR-10: The system shall allow students to track their tickets using the tracking code.
- FR-11: The system shall display ticket details and the current ticket status to the student.
- FR-12: The system shall allow students to attach supporting files to their tickets.
- FR-13: The system shall support payment receipt attachments.
- FR-14: The system shall maintain comments and interaction history associated with each ticket.

3.3 Ticket Processing and Management

- FR-15: The system shall allow Student Affairs staff to view submitted tickets.
- FR-16: The system shall allow staff to filter tickets by category.
- FR-17: The system shall allow authorized staff to update ticket statuses.
- FR-18: The system shall support the following ticket statuses:
  - Open
  - In Progress
  - Resolved
  - Rejected
- FR-19: The system shall allow staff to add comments and responses to tickets.
- FR-20: The system shall record ticket status changes, including the previous status, new status, and date of change.
- FR-21: The system shall maintain a history of ticket updates for tracking and accountability.
- FR-22: The system shall associate handled tickets with the responsible Student Affairs staff member.

3.4 AI Agent Requirements

- FR-23: The system shall provide an AI Agent to assist students with inquiries and system interactions.
- FR-24: The AI Agent shall answer student questions using information available in the Knowledge Base.
- FR-25: The AI Agent shall assist in extracting relevant student information.
- FR-26: The AI Agent shall assist in classifying submitted tickets according to their content and category.
- FR-27: The AI Agent shall support scanning uploaded payment receipts.
- FR-28: The AI Agent shall extract transaction IDs and other relevant information from payment receipts.
- FR-29: The extracted receipt information shall support the subsequent payment verification process.

3.5 Payment Receipt and Verification Management

- FR-30: The system shall allow students to upload payment receipts as ticket attachments.
- FR-31: The system shall store payment receipt information, including the transaction ID when available.
- FR-32: The system shall allow authorized Student Affairs staff to perform payment verification.
- FR-33: The system shall record payment verification attempts and their results.
- FR-34: The system shall support the following payment verification results:
  - Verified
  - Not Found
  - Already Used
- FR-35: The system shall associate each payment verification record with the relevant payment receipt and staff member.
- FR-36: The system shall record the date and time of each verification attempt.

3.6 Email Notification Management

- FR-37: The system shall support email notifications related to student tickets.
- FR-38: The system shall notify students about relevant ticket updates and responses.
- FR-39: The system shall support including resolution comments in relevant email notifications.
- FR-40: The system shall maintain notification records, including the recipient email address, message, sending date, and notification status.

3.7 Knowledge Base Management

- FR-41: The system shall provide a Knowledge Base containing articles, information, and college regulations.
- FR-42: The Administrator shall be able to add new Knowledge Base articles.
- FR-43: The Administrator shall be able to edit existing articles.
- FR-44: The Administrator shall be able to delete articles.
- FR-45: The system shall maintain article information, including article ID, title, content, and last updated date.
- FR-46: The AI Agent shall use Knowledge Base content as a source when answering student inquiries.

3.8 Staff and Permission Management

- FR-47: The Administrator shall be able to create staff accounts.
- FR-48: The Administrator shall be able to view and manage existing staff accounts.
- FR-49: The Administrator shall be able to activate or deactivate staff accounts.
- FR-50: The Administrator shall be able to manage staff permissions.
- FR-51: The system shall ensure that staff operations are limited according to their assigned permissions.

3.9 Performance Reports and Analytics

- FR-52: The Administrator shall be able to generate performance reports.
- FR-53: The system shall provide ticket statistics based on ticket statuses.
- FR-54: The system shall support reporting on ticket counts, including Open, In Progress, Resolved, and Rejected tickets.
- FR-55: The system shall support generating reports for a selected month or reporting period.
- FR-56: The Administrator shall be able to export generated reports in CSV format.
- FR-57: The system shall maintain report information, including report ID, reporting month, and generation date.

---

4. Non-Functional Requirements

4.1 Security

- NFR-01: The system shall protect user accounts through authentication.
- NFR-02: User passwords shall be stored as secure password hashes rather than plain text.
- NFR-03: The system shall enforce role-based access control.
- NFR-04: Users shall only access operations and information permitted by their roles and permissions.
- NFR-05: The system shall protect student information and uploaded documents against unauthorized access.

4.2 Performance

- NFR-06: The system should provide responsive interactions when users submit requests, view tickets, and navigate between pages.
- NFR-07: Ticket filtering and retrieval should operate efficiently as the number of submitted tickets increases.
- NFR-08: AI-assisted operations should provide results within a reasonable processing time.

4.3 Reliability and Data Integrity

- NFR-09: The system shall maintain consistent ticket records and associated information.
- NFR-10: Ticket status changes and verification attempts shall be recorded accurately.
- NFR-11: Each ticket shall have a unique tracking code to support reliable tracking.
- NFR-12: The system should handle invalid or incomplete user input without corrupting stored data.

4.4 Usability

- NFR-13: The user interface shall be clear, consistent, and easy to navigate.
- NFR-14: The system shall provide interfaces appropriate to the responsibilities of each user role.
- NFR-15: Students should be able to submit and track requests without requiring advanced technical knowledge.

4.5 Maintainability and Scalability

- NFR-16: The system should be organized into modular components to simplify maintenance and future development.
- NFR-17: The system should support future enhancements and additional features.
- NFR-18: The system architecture should allow changes to the database technology and AI services without requiring a complete redesign.

---

5. Ticket and Verification Data Requirements

5.1 Ticket Status Values

Each ticket shall have one of the following statuses:

Status| Description
Open| The ticket has been submitted and is awaiting processing.
In Progress| The ticket is currently being handled by Student Affairs staff.
Resolved| The student's request has been resolved.
Rejected| The request has been rejected.

5.2 Payment Verification Results

Payment verification records shall support the following results:

Result| Description
Verified| The payment transaction has been successfully verified.
Not Found| The transaction could not be found during verification.
Already Used| The transaction has already been used in another verification.

---

6. System Constraints and Assumptions

- The primary programming language selected for system development is Python.
- The system will include an AI Agent for intelligent assistance and receipt information extraction.
- The database management system has not yet been finalized by the project team.
- The system will use role-based access to separate Student, Student Affairs Staff, and Administrator operations.
- Payment receipt extraction and payment verification are separate operations: the AI Agent extracts receipt information, while authorized staff perform the verification process.
- The availability and accuracy of AI-generated information may depend on the quality of the provided data and uploaded receipt images.
- Email notification functionality requires an appropriate email delivery service.
- The exact frameworks, database technology, AI service, and deployment environment will be finalized during implementation.

---

7. Expected Outcomes

The expected outcome is a centralized, AI-powered Student Affairs Management System that:

- Simplifies the process of submitting and tracking student requests.
- Improves the organization and handling of student tickets.
- Supports faster access to college information through the AI Agent and Knowledge Base.
- Reduces manual receipt data entry through AI-assisted extraction.
- Improves payment verification tracking and accountability.
- Enhances communication through email notifications.
- Provides administrators with structured management tools and performance reports.
