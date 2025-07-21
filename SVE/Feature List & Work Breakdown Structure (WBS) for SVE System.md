## 1. Application Overview

**SVE (Setter, Vetter & Expert)** is an exam management system for Primary and Secondary schools that allows management of exam components, assignment of teachers to various roles (Setter, Vetter, Expert), creation of timetables, and much more.

---

## 🎯 Core Features

### 1. Component Management
- **Objective:** Manage exam components for various subjects and configure additional paper types.
- **Key Features:**
  - **Create Components for Each Active Subject:** Allow exam components to be created and associated with subjects.
  - **Flexible Component Naming:** Enable naming of components (e.g., Paper 1, Paper 2).
  - **Link Components to Subjects:** Set up associations between subjects and their respective components.
  - **Additional Paper Types:** Configure different types of paper for exams:
    - Insert Cover Page (ICP)
    - Insert / Booklet (INS)
    - Answer Sheet (AS)
    - Erratum Answer Sheet (EAS)
    - Teacher Paper (TP)
    - Multiple Choice Question (MCQ)
    - MF19 (MF19)
    - Audio File (AUD)

### 2. SVE Assignment System
- **Objective:** Assign teachers to various roles (Setter, Vetter, Expert) for different exam components.
- **Key Features:**
  - **Create SVE List:** Maintain a list of all SVE assignments.
  - **Bind Subject and Component to Assign Teachers:** Match subjects and components to the relevant teachers.
  - **Assign Roles:** Assign teachers to their respective roles (Setter, Vetter, Expert).
  - **Bind Exam Types:** Link specific exam types (AS Prelim, IGCSE/A2 Prelim, MYE, FYE, BMT 1, BMT 2).
  - **Download SVE Data:** Export data in PDF and Excel formats.

### 3. SVE Exam Timetable
- **Objective:** Schedule exams, track timings, and handle timetable comments and modifications. Special handling for **BMT exam types**.
- **Key Features:**
  - **Set Exam Day, Date, Time, and Duration:** Create detailed exam schedules.
  - **Group Timetable by Exam Type:** Organize the timetable based on exam categories.
  - **Comment System for Timetable:** Allow comments to be added for modifications or clarifications.
  - **Approve Comments for Timetable Changes:** Enable workflow to approve changes to the timetable.
  - **Timetable Modification:** Implement changes based on approved comments.
  - **Handle BMT Exam Type Special Cases:** For **BMT exams**, **no timetable** is required. Instead of scheduling exams by date and time, principals can select the **academic week** for the exam.
  - **Special File Upload for BMT Exams:** Files for **BMT exams** are handled differently from other exam types. Principals or relevant teachers can upload specific files for **BMT** exams using the special file upload option tied to BMT papers.

### 4. **SVE Deadline Management**
- **Objective:** Set and manage deadlines for different tasks across various aspects of the exam process. Custom deadlines for each academic year, school level (Primary/Secondary), and exam type.
- **Key Features:**
  - **Set Deadlines for Teacher Assignment:** Specify deadlines for assigning teachers to various roles (Setter, Vetter, Expert).
  - **Set Deadlines for File Uploads:** Define the deadline for uploading exam components, answer sheets, and other related files.
  - **Set Deadlines for Timetable Creation:** Allow users to set deadlines for creating and finalizing the exam timetable.
  - **Set Deadlines for Printing Requests:** Establish deadlines for printing exam papers, answer sheets, and other related materials.
  - **Differentiated Deadlines by Academic Year:** Set different deadlines for each academic year.
  - **Differentiated Deadlines by School Level:** Set unique deadlines for Primary and Secondary schools.
  - **Differentiated Deadlines by Exam Type:** Provide flexibility to set different deadlines based on exam types (e.g., Prelims, MYE, IGCSE).

### 5. **Cover Page Management & Template Insertion**
- **Objective:** Manage cover page templates and insert them into exam components. Teachers can edit cover pages as needed. Cover pages are generated based on the exam period.
- **Key Features:**
  - **Manage Cover Page Templates:** Create and store different cover page templates for various exam types.
  - **Insert Cover Page for Exams:** Insert the cover page template at the start of each exam paper.
  - **Custom Cover Pages Based on Exam Type:** Enable different cover pages to be inserted based on the exam type (e.g., Prelims, IGCSE, MYE).
  - **Custom Cover Pages for Primary and Secondary:** Provide different cover pages for Primary and Secondary school exams.
  - **Insert Cover Page at the Start of Each Paper:** Automatically insert the selected cover page at the beginning of each exam paper.
  - **Allow Teachers to Edit Cover Pages:** Once the default template is inserted, teachers can edit the cover page content as needed before finalizing the exam paper.
  - **Create Cover Page for All Subjects and Papers:** Generate a default cover page template for every subject and paper setup, automatically linked with the subject and exam paper.
  - **Generate Cover Pages Based on Exam Period:** Cover pages are generated based on the specific exam period (e.g., Prelims, IGCSE, MYE). This ensures that the cover page is relevant to the specific exam being conducted.
  - **Allow Teachers to Edit Generated Cover Pages:** Teachers can modify the generated cover pages to suit the specific requirements or preferences of the exam period.

### 6. **SVE File Upload**
- **Objective:** Enable teachers to upload exam-related files, with file management and review capabilities. Special handling for **BMT exam types**.
- **Key Features:**
  - **Upload Files Based on Access Rules:** Teachers can upload files based on their assigned roles and permissions. For example, only teachers with specific access levels can upload certain types of files (e.g., answer sheets, exam papers).
  - **Automatic File Renaming:** The system automatically renames the uploaded files to ensure consistency and organization. The renaming can be based on preset rules, such as adding the exam type, subject, and a timestamp to the filename.
  - **File Annotation for Review:** Teachers or admins can annotate uploaded files, providing feedback or comments directly on the document (e.g., marking errors or suggesting improvements).
  - **Approve or Reject File Status:** Each uploaded file can be marked with a status of **approved** or **rejected** based on the review and annotation process. This status helps track whether the file is ready for use or needs further adjustments.
  - **Access to Reviewed Files:** Teachers can view annotated files and the review status, helping them make necessary revisions before final submission.
  - **File Versioning:** The system can keep track of file versions, ensuring that any updates or modifications to uploaded files are logged for review.
  - **Special Handling for BMT File Uploads:** For **BMT exams**, files related to the exam are uploaded separately and handled according to special rules tied to the BMT exam type.

### 7. **SVE List**
- **Objective:** Manage and monitor the status of uploaded files, replace files if needed, and compile files into a downloadable zip.
- **Key Features:**
  - **View Upload Status:** Allow users to view the status of all uploaded files (approved, rejected, pending review) in a list view.
  - **File Access and Replacement:** Users can access any uploaded file and replace the file if necessary.
  - **Compile Files into Zip:** The system can compile all files for a particular subject, paper, and exam type into a single zip file for easy downloading.
  - **Folder Organization by Naming Convention:** Files will be organized in folders named according to the following format:
    - `subject_paper_examType_academicYear_primary/secondary`
    - Example: `Math_Paper1_IGCSE_2025_secondary/`
  - **Download Zip File:** Allow users to download the compiled zip file containing all the relevant exam files in an organized folder structure.

### 8. **SVE Printing Request**
- **Objective:** Enable principals to request the number of papers to be printed based on paper type and handle late printing requests.
- **Key Features:**
  - **Submit Printing Request:** Principals at each campus can specify the number of copies to print for each paper, based on paper types.
  - **Late Printing Request:** Introduce the option for **late printing requests** to handle last-minute orders after the regular deadline has passed.
  - **Separate Regular and Late Printing in Reports:** Printing requests for **regular** and **late** orders will be tracked separately in the **SVE report** under the **printing details**.
  - **No Timetable for BMT Exam Type:** For **BMT (Basic Military Training)** exam types, there is no need to set up an exam timetable. Instead, principals can select the **academic week** during which the exam occurs.
  - **Special File Upload for BMT:** For **BMT** exams, there is a special file upload option that links directly to the **BMT paper**. The files uploaded for BMT exams will be handled differently from other exam types.

### 9. **SVE Errata List**
- **Objective:** Handle exam revisions or erratum. Allow teachers to upload erratum files, notify the subject teacher, and enable admin monitoring of the errata files.
- **Key Features:**
  - **Erratum File Upload:** Teachers can upload files in the erratum section to provide revisions to the exam papers.
  - **Notify Subject Teachers via Email:** When a file is uploaded in the erratum section, the system will automatically send an email to the relevant subject teacher to inform them of the revision or erratum.
  - **Erratum Monitoring by Admin:** Admins can access the list of all erratum files uploaded and monitor the changes or revisions made.
  - **Erratum Status:** Each erratum file can be tracked for its review status, with the option to approve or reject the revisions.

### 10. **SVE Past Paper**
- **Objective:** View and download exam files from past academic years for teachers based on their subject assignments in the current academic year.
- **Key Features:**
  - **View Past Papers for Past Academic Years:** Allow subject teachers to view past papers and exam files from previous academic years.
  - **Download Past Exam Files:** Provide download options for past papers and related exam files in **PDF** format.
  - **Display Files Based on Current Academic Year and Subject Teacher Role:** The system will show past papers based on the subject teacher's assignment for the **current academic year**, ensuring the teacher only has access to relevant past papers for the subject they teach.

### 11. **SVE Labels**
- **Objective:** Generate and print labels for exam paper envelopes to be used for labeling purposes.
- **Key Features:**
  - **Auto-Generate Labels for Specific Types:** Automatically generate labels for various categories, including:
    - **General Labels**
    - **Expert Labels**
    - **Miscellaneous Labels**
    - **HOD Labels**
  - **Support for Tom and Jerry Paper:** Labels can be printed for **Tom and Jerry** paper to be affixed to the exam paper envelopes.

### 12. **SVE Dispatches Box**
- **Objective:** Manage the grouping of exam papers into boxes for dispatch, based on academic year, campus, and exam type.
- **Key Features:**
  - **Grouping by Academic Year, Campus, and Exam Type:** Automatically group exam papers into boxes based on these criteria.
  - **Monitor Papers in Dispatch Box:** Allow the admin to monitor which exam papers are placed in each box.
  - **Print Grouping Box Label:** Generate labels for each box containing the grouped exam papers.
  - **Track Envelope Numbers:** Specify and track the number of paper envelopes in each box.
  - **Monitor Box Status:** Check if the exam paper for a specific exam type is already placed in the selected box and whether the printing request has been fulfilled.

---

## 🔨 Work Breakdown Structure (WBS)

### Phase 1: Component System

- **Task 1: Create Component Creation Module**  
  Design and develop the component creation interface.  
  Implement input validation for component names.

- **Task 2: Link Components to Subjects**  
  Implement functionality to bind components to relevant subjects.

- **Task 3: Component Naming System**  
  Enable flexible naming for components (e.g., Paper 1, Paper 2, etc.).

- **Task 4: Additional Paper Setup**  
  Configure the additional paper types:  
    - Insert Cover Page (ICP)  
    - Insert / Booklet (INS)  
    - Answer Sheet (AS)  
    - Erratum Answer Sheet (EAS)  
    - Teacher Paper (TP)  
    - Multiple Choice Question (MCQ)  
    - MF19 (MF19)  
    - Audio File (AUD)

---

### Phase 2: SVE Assignment

- **Task 1: Build SVE List Interface**  
  Create an interface for managing the list of teachers, subjects, and components.

- **Task 2: Bind Subject-Component Functionality**  
  Enable the feature to bind specific subjects to their corresponding components.

- **Task 3: Teacher Role Assignment**  
  Assign teachers to the Setter, Vetter, or Expert roles for each component.

- **Task 4: Bind Exam Types**  
  Implement functionality to assign exam types (e.g., AS Prelim, IGCSE/A2 Prelim, etc.).

- **Task 5: PDF Export Functionality**  
  Allow users to download SVE data as a PDF.

- **Task 6: Excel Export Functionality**  
  Enable data download in Excel format.

- **Task 7: Assignment Tracking**  
  Implement a system for tracking assignment statuses and changes.

---

### Phase 3: SVE Exam Timetable

- **Task 1: Create Exam Schedule (Day, Date, Time, Duration)**  
  Implement the interface for scheduling exams with detailed information.

- **Task 2: Group Timetable by Exam Type**  
  Organize the timetable into groups based on exam types.

- **Task 3: Comment System for Timetable**  
  Implement a feature that allows users to leave comments on the exam timetable.

- **Task 4: Comment Approval Workflow**  
  Develop a workflow for approving timetable changes based on user comments.

- **Task 5: Modify Timetable Based on Approved Comments**  
  Enable automatic modification of the timetable after comments are approved.

- **Task 6: Handle BMT Exam Type Special Cases**  
  Allow **BMT exams** to skip the timetable setup, and enable selection of the **academic week** for the exam.

- **Task 7: Special File Upload for BMT Exams**  
  Enable special file upload functionality for **BMT exam papers**, distinct from other exam types.

---

### Phase 4: **SVE Deadline Management**

- **Task 1: Set Deadlines for Teacher Assignment**  
  Define deadlines for assigning teachers to various roles (Setter, Vetter, Expert).

- **Task 2: Set Deadlines for File Uploads**  
  Specify the deadline for uploading exam components, answer sheets, and other related files.

- **Task 3: Set Deadlines for Timetable Creation**  
  Set deadlines for creating and finalizing the exam timetable.

- **Task 4: Set Deadlines for Printing Requests**  
  Establish deadlines for printing exam papers, answer sheets, and other related materials.

- **Task 5: Differentiated Deadlines by Academic Year**  
  Allow different deadlines for each academic year.

- **Task 6: Differentiated Deadlines by School Level**  
  Provide unique deadlines for Primary and Secondary schools.

- **Task 7: Differentiated Deadlines by Exam Type**  
  Set different deadlines based on exam types (e.g., Prelims, MYE, IGCSE).

---

### Phase 5: **Cover Page Management & Template Insertion**

- **Task 1: Manage Cover Page Templates**  
  Design and manage cover page templates for different exam types.

- **Task 2: Insert Cover Page for Exams**  
  Allow automatic insertion of cover pages based on exam type and school level.

- **Task 3: Custom Cover Pages for Exam Types**  
  Customize cover pages based on exam types (Prelims, MYE, IGCSE).

- **Task 4: Custom Cover Pages for Primary and Secondary Schools**  
  Provide separate cover pages for Primary and Secondary school exams.

- **Task 5: Automate Cover Page Insertion at the Start of Each Paper**  
  Automatically insert the selected cover page at the beginning of each exam paper.

- **Task 6: Create Cover Page for All Subjects and Papers**  
  Automatically generate cover pages for all subjects and papers that have been set up, linking them to the appropriate exam papers.

- **Task 7: Generate Cover Pages Based on Exam Period**  
  Enable cover page generation to be based on the exam period (e.g., Prelims, IGCSE, MYE), ensuring relevance to the current exam.

- **Task 8: Allow Teachers to Edit Generated Cover Pages**  
  Enable teachers to modify the generated cover pages for the specific exam period or school level.

---

### Phase 6: **SVE File Upload**

- **Task 1: Enable File Upload Based on Access Rules**  
  Allow teachers to upload files based on their specific role permissions and access rights.

- **Task 2: Automatic File Renaming**  
  Implement automatic renaming of uploaded files according to predefined naming conventions.

- **Task 3: File Annotation for Review**  
  Implement file annotation capabilities to review and provide feedback on uploaded documents.

- **Task 4: Approve/Reject File Status**  
  Introduce file approval/rejection status to track reviewed documents.

- **Task 5: Version Control for Files**  
  Maintain versioning to keep track of changes to uploaded files.

- **Task 6: Special Handling for BMT File Uploads**  
  For **BMT exams**, special file handling and upload rules will be applied to ensure the unique requirements for BMT papers are met.

---

### Phase 7: **SVE Labels**

- **Task 1: Auto-Generate Labels for Various Types**  
  Generate labels automatically for **General**, **Expert**, **Miscellaneous**, and **HOD** types.

- **Task 2: Support for Tom and Jerry Paper**  
  Ensure that labels are printed on **Tom and Jerry paper** for use with exam paper envelopes.

---

### Phase 8: **SVE Dispatches Box**

- **Task 1: Grouping of Exam Papers**  
  Automatically group exam papers into boxes based on academic year, campus, and exam type.

- **Task 2: Monitor and Label Dispatch Boxes**  
  Track the papers in each box, generate labels, and monitor the envelopes inside.

- **Task 3: Monitor Printing Requests for Exam Types**  
  Ensure that each box contains the appropriate exam papers according to the printing request and monitor whether the request has been fulfilled.

---

### Phase 9: **SVE Past Paper**

- **Task 1: Display Past Exam Papers for Teachers**  
  Enable subject teachers to view and download past exam papers and files from previous academic years.
  
- **Task 2: Filter by Current Academic Year and Subject**  
  Display past papers based on the current academic year and the subject taught by the teacher.

- **Task 3: Download Past Exam Papers as PDF**  
  Provide download functionality for past papers in **PDF** format.

---

### Phase 10: Testing & Deployment

- **Task 1: System Testing**  
  Conduct thorough testing of all features to ensure they meet requirements.

- **Task 2: Go-Live**  
  Deploy the system for use by all stakeholders.

---

## 🚀 Next Steps
- **Task 1:** Develop the component creation system.
- **Task 2:** Implement the SVE assignment functionality.
- **Task 3:** Implement deadline management feature across all tasks (teacher assignment, file uploads, timetable creation, printing requests).
- **Task 4:** Implement **SVE Past Paper** functionality to view and download past exam papers.
- **Task 5:** Implement **SVE Labels** and **SVE Dispatches Box** functionality.

