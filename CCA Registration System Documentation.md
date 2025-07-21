## Overview
The CCA Registration System allows **admins** to set up and manage Co-Curricular Activities (CCAs) with specific registration quotas and enables **students** to register for those activities. The system ensures that registration is based on seat availability, with certain rules in place, such as the number of CCAs a student can register for. Once registered, the admin can **approve, reject**, or **move** student registrations to other CCAs based on availability and other factors. Notifications about registration status will be sent through **in-app notifications** or **email** to students.

Additionally, **CCA rules** can be configured **per campus**. If no specific rules are set for a campus, the system will have **no CCA rules** applied to students from that campus.

---

## Admin Journey

### 1. **Set Quota for Each CCA**
   - Admin logs into the system.
   - Navigate to the **Manage CCA** section.
   - Set the **quota** (number of available seats) for each individual CCA.
   - The **quota for a CCA** is independent of the number of CCAs a student registers for.
   - Admin can enable or disable registration for specific CCAs.

### 2. **Monitor CCA Registration**
   - Admin can view the list of students who have registered for each CCA.
   - Admin can see available seats and whether the quota for each CCA is full.
   - If a CCA is full, it will show as "**CCA Full**" and no more students can register for it.

### 3. **Approve, Reject, or Move Registrations**
   - Admin has the option to:
     - **Approve** a student's registration, making them an official CCA participant.
     - **Reject** a student's registration if they don't meet the required conditions or quota.
     - **Move** a student’s registration to another CCA if they are not accepted or if a space becomes available in a different CCA.

### 4. **Manage CCA Rules**
   - Admin can set **campus-based rules** for CCA registrations:
     - **Level 3 students** can register for **2 CCAs**.
     - **Level 4 - 6 students** can register for **3 CCAs**.
   - If no rules are configured for a campus, **no CCA registration rules** will apply to students at that campus.

### 5. **View Reports and Analytics**
   - Admin can generate reports on the number of students registered for each CCA.
   - Admin can view the list of confirmed CCA participants, pending registrations, and rejected registrations.

---

## Admin Dashboard - Student Registration Overview

### **Table: List of Student CCA Registrations**

Admins can view a table of students along with their registration details:

| Student Name  | Classroom  | Level | CCA(s) Registered |
|---------------|------------|-------|-------------------|
| John Doe      | 5A         | 3     | CCA 1, CCA 2      |
| Jane Smith    | 6B         | 4     | CCA 2, CCA 3      |
| Mark Johnson  | 4C         | 3     | CCA 1             |
| Emma Davis    | 5D         | 4     | CCA 2, CCA 3      |
| Liam Brown    | 6E         | 5     | CCA 1, CCA 2      |

In this table:
- **Student Name**: The name of the student.
- **Classroom**: The classroom the student belongs to.
- **Level**: The student’s academic level (e.g., Level 3, Level 4, etc.).
- **CCA(s) Registered**: The list of CCA(s) the student has registered for, separated by commas.

### 6. **Filter and Search**
   - Admin can filter or search the table by:
     - **Student Name**
     - **Classroom**
     - **Level**
     - **CCA(s) Registered**
   - Admin can also sort the table to organize by any column, making it easier to manage registrations and confirm or reject students for each CCA.

---

## Student Journey

### 1. **Browse and Select CCA**
   - Student logs into the system and navigates to the "CCAs" section.
   - They can view all available CCAs along with their quotas (number of available seats).
   - If a CCA is full, it will show as "**CCA Full**" and students cannot register for it.

### 2. **Register for CCA**
   - Student selects a CCA and registers for it if there are available seats.
   - Students can register for up to a maximum number of CCAs, depending on their **grade level**:
     - **Level 3 students** can register for up to **2 CCAs**.
     - **Level 4 to 6 students** can register for up to **3 CCAs**.
   - The system ensures that students cannot exceed the allowed number of CCAs.

### 3. **Confirm Registration**
   - After registration, students can view their current registration status for each CCA.
   - Students will receive **in-app notifications** and **emails** when their registration is confirmed, rejected, or moved to another CCA by the admin.

### 4. **View Confirmed Participation**
   - Students can view which CCA they have been officially registered in after admin approval.
   - Students can also see the list of other participants who are registered for the same CCA.

---

## Key Features

### 1. **Quota Management for Each CCA**
   - Each CCA has its own fixed quota, which determines how many students can register.
   - The quota is independent of the total number of CCAs a student has registered for.
   - Once the quota is full for a CCA, the system will display "**CCA Full**" and prevent further registrations.

### 2. **Student Registration Limits**
   - Students are limited to a specific number of CCAs they can register for based on their grade level or other criteria:
     - **Level 3 students** can register for up to **2 CCAs**.
     - **Level 4 - 6 students** can register for up to **3 CCAs**.
   - This rule does not affect the **individual quotas** for each CCA.

### 3. **Admin Approval, Rejection, or Moving of Registrations**
   - Admins can:
     - **Approve** a student's registration, making them an official CCA participant.
     - **Reject** a student's registration if they exceed the CCA limits, are not eligible, or do not meet other criteria.
     - **Move** a student’s registration to another CCA if there is availability, or if the original CCA was full.

### 4. **Campus-Based CCA Rules**
   - Admins can set CCA rules for each campus.
   - **Level 3 students** can register for **2 CCAs**.
   - **Level 4 - 6 students** can register for **3 CCAs**.
   - If **no rules are set for a campus**, students will not have any registration restrictions.

### 5. **Notifications and Alerts**
   - Students will receive **in-app notifications** and **emails**:
     - **When a CCA is full** or has available seats.
     - **After successful registration**.
     - **When their registration is confirmed**, rejected, or moved to another CCA by the admin.
   - Admins will receive notifications when a CCA is nearing full capacity or when any action (approve, reject, or move) is taken on a student’s registration.

---

## Work Breakdown Structure (WBS)

### 1. **Admin CCA Management**
   - **1.1.** Create and manage CCA (name, description, etc.)
   - **1.2.** Set independent quota for each CCA (available seats)
   - **1.3.** Enable/Disable registration for each CCA
   - **1.4.** View available seats and registration status for each CCA
   - **1.5.** Approve, Reject, or Move student registrations
   - **1.6.** Generate reports for student registrations, confirmed participants, and rejected registrations
   - **1.7.** Set campus-specific CCA rules (e.g., maximum number of CCAs for each student level)

### 2. **Student Registration**
   - **2.1.** Browse and view available CCA activities and their quotas
   - **2.2.** Register for a CCA (if seats are available)
   - **2.3.** Check registration status for each CCA
   - **2.4.** Receive notifications about registration status and participation approval, rejection, or moving to another CCA
   - **2.5.** Observe CCA participation rules based on their grade level (Level 3: max 2 CCAs, Level 4-6: max 3 CCAs)

### 3. **System Configuration and Rules**
   - **3.1.** Set rules for the maximum number of CCAs a student can register for (e.g., Level 3 students: 2 CCAs, Level 4-6 students: 3 CCAs)
   - **3.2.** Enable campus-specific CCA rules (e.g., no rules, Level 3 only 2 CCAs, Level 4-6 max 3 CCAs)
   - **3.3.** Ensure that the CCA quota is independent of the student's total number of CCA registrations
   - **3.4.** Display "CCA Full" status when quota is reached for an activity

### 4. **Notifications and Alerts**
   - **4.1.** Notify students if a CCA is full or has available seats
   - **4.2.** Notify students when their registration is confirmed, rejected, or moved to another CCA
   - **4.3.** Notify admins when a CCA is nearing its quota limit or when a student's registration is changed

### 5. **Admin Dashboard**
   - **5.1.** View student registrations for each CCA
   - **5.2.** View available seats and registration status for all CCAs
   - **5.3.** Approve, reject, or move students' registrations and update their status
   - **5.4.** Set campus-specific CCA rules
   - **5.5.** View and filter student registration table (Student Name, Classroom, Level, CCA List)

### 6. **Student Dashboard**
   - **6.1.** View available CCA options and their quotas
   - **6.2.** Register for up to the allowed number of CCAs based on grade-level restrictions
   - **6.3.** View current registration status and participation confirmations (approved, rejected, or moved)

---

## Summary
This CCA Registration System ensures that students can easily register for Co-Curricular Activities within available quotas while adhering to registration rules (e.g., maximum number of CCAs per student). Admins have full control over the quota setup and the ability to approve, reject, or move student registrations to other CCAs. Notifications via **in-app notifications** and **email** keep both students and admins informed throughout the process, ensuring a smooth and organized CCA registration experience.
