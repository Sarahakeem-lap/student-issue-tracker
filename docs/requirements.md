# Requirements: Student Affairs AI Support System
Project board: https://github.com/users/Sarahakeem-lap/projects/4/views/1

## 1. Roles
- Student: asks questions, submits issues, and tracks their tickets.
- Affairs Staff: views, filters, and resolves student tickets.
- Admin: manages staff accounts and updates the college regulations knowledge base.

## 2. User stories
US-01 As a student, I want to ask questions about college regulations so that I can get instant answers without waiting in line. [Must]
US-02 As a student, I want to describe my specific problem so that the AI can extract my details and generate a support ticket. [Must]
US-03 As an affairs staff, I want incoming complaints classified into categories automatically so that tickets reach the right department. [Must]
US-04 As an affairs staff, I want to view a dashboard of all tickets and filter them by category so that I can focus on my department's issues. [Must]
US-05 As an affairs staff, I want to update the status of a ticket and add a resolution comment so that the student knows their problem is being handled. [Must]
US-06 As a student, I want to track my ticket resolution status using a tracking code so that I can know if my problem has been solved. [Should]
US-07 As a student, I want to upload a payment receipt attachment to my ticket so that the affairs staff can verify my financial issue. [Should]
US-08 As an affairs staff, I want to verify the payment transaction ID against the financial database so that I can ensure the uploaded receipt is authentic. [Should]
US-09 As an admin, I want to add, update, or delete college regulations in the knowledge base so that the AI assistant always provides accurate answers. [Should]
US-10 As an admin, I want to manage staff accounts and permissions so that only authorized personnel can access student tickets. [Should]
US-11 As a student, I want to receive an email notification when my ticket is resolved so that I don't have to manually check the tracking status. [Could]
US-12 As an admin, I want to generate a performance report of all tickets so that I can monitor how efficiently issues are being resolved. [Could]

## 3. Acceptance criteria
### US-01 AI answers FAQ
```gherkin
Feature: AI answers FAQ
Scenario: Student asks a clear regulation question
  Given the student asks "What is the minimum GPA to pass?"
  When the AI processes the question
  Then the AI replies with "The minimum GPA is 2.0"

Scenario: Student asks a vague or off-topic question
  Given the student asks "What is the best movie?"
  When the AI processes the question
  Then the AI politely declines and asks the student to stick to college affairs

### US-02 Extract details and generate ticket
### US-01 AI answers FAQ

Feature: Generate ticket
Scenario: Student provides full details
  Given the student says "My ID is 2023145 and my physics grade is missing"
  When the AI extracts the data
  Then a ticket is generated with ID "2023145" and issue "physics grade missing"

Scenario: Student provides incomplete details
  Given the student says "My grade is missing"
  When the AI extracts the data
  Then the AI asks "Please provide your student ID to proceed"

Feature: Auto-classify issue
Scenario: Payment issue classified correctly
  Given a student submits "I paid fees but enrollment is locked"
  When the AI processes the message
  Then the ticket category is set to "Financial"

Scenario: Technical issue classified correctly
  Given a student submits "The system is hanging and not opening"
  When the AI processes the message
  Then the ticket category is set to "Technical Support"

Feature: View and filter tickets
Scenario: Staff filters tickets by category
  Given there are 2 "Financial" tickets and 3 "Academic" tickets
  When the affairs staff selects the "Financial" filter
  Then only the 2 "Financial" tickets are displayed

Scenario: Staff filters a category with no tickets
  Given there are no tickets in the "Technical Support" category
  When the affairs staff selects the "Technical Support" filter
  Then the system displays "No tickets found in this category"

Feature: Update ticket status
Scenario: Staff resolves a ticket with a comment
  Given a ticket is in the "In Progress" status
  When the affairs staff changes the status to "Resolved" and adds comment "Course added"
  Then the ticket status becomes "Resolved"

Scenario: Staff tries to resolve without a comment
  Given a ticket is in the "In Progress" status
  When the affairs staff tries to change the status to "Resolved" without a comment
  Then the system rejects the update with "A resolution comment is required"

4. Non-functional requirements
NFR-01 (Performance) The AI Agent must respond to queries in < 3 seconds. [Must]
NFR-02 (Security) Passwords for staff accounts are stored hashed (bcrypt, cost >= 12). [Must]
NFR-03 (Storage) Uploaded files must be restricted to safe formats (JPG, PNG, PDF) and max 5MB. [Should]
NFR-04 (Availability) The system is available 99.9% of the time, measured monthly. [Could]

5. MVP scope
Must stories in the MVP: US-01, US-02, US-03, US-04, US-05.
Must NFRs in the MVP: NFR-01, NFR-02.
Reason: Together, they allow a student to interact with the AI, get instant answers, and create a ticket. They also allow the AI to classify the ticket, and the staff to view, filter, and resolve it securely. All Should and Could stories stay in the backlog.



