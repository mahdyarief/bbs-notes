## 1. Academic Subject Configuration
### Description:
Setup for academic subjects that will be used for the BMT process.

### Tasks:
- Define subjects for academic purposes.
- Link subjects with appropriate paper types.

---

## 2. Paper Type Configuration
### Description:
Define the different types of papers used in the exam workflow.

### Tasks:
- **Marking Scheme**: Define marking criteria for each paper.
- **Question Paper**: Setup for question paper generation and management.
- **Other Files**: Define other supporting documents for the exam.
- **BMT Answer Sheet**: Define and manage the answer sheet used in BMT exams.

---

## 3. Workflow up to Vetter
### Description:
Define the BMT workflow with approval reaching the "Vetter" stage.

### Tasks:
- Develop workflow till vetter.
- **Final BluePrint for Vetter**: Setup for final blueprint for BMT vetter review.
- No expert requirement for BMT process.

---

## 4. Exam Type Field Addition
### Description:
Add a new field on paper type for defining the "Exam Type."

### Tasks:
- Add "Exam Type" as a field under paper type configuration.

---

## 5. Week Configuration in Academic Year
### Description:
Modify how weeks are handled in the academic year without using end dates as parameters.

### Tasks:
- Add week field in the academic year settings.
- Remove end date dependency for week configuration.

---

## 6. SVE Exam Date & BMT Week List
### Description:
Use a new field for SVE Exam date and ensure the BMT week list is used for scheduling.

### Tasks:
- Remove previous information used for SVE exam dates.
- Display the BMT week list on SVE exam date field.

---

## 7. Duplication of Weeks & Chapters from Previous Year
### Description:
Automatically duplicate weeks and chapters from the previous academic year for easy setup.

### Tasks:
- Implement duplication of week and chapter data from the previous year.

---

## 8. Approval Outside of System
### Description:
Implement approval processes outside the system, only updating once approved.

### Tasks:
- Set up an external approval workflow.
- Implement update mechanism after approval.

---

## 9. Sync BMT Using Y-1
### Description:
Sync BMT data from the previous year’s BMT week, including week and chapter/topic.

### Tasks:
- Create sync process for BMT data from Y-1.
- Ensure week and chapter/topic information are captured.

---

## 10. Teacher View of Files
### Description:
Teacher can see the files if the current date falls within the defined week and if the file status is FBP (Final BluePrint).

### Tasks:
- Implement file visibility logic based on date and file status (FBP).

---

## 11. Email Notification to Setter & Vetter
### Description:
Notify Setter and Vetter via email if the Question Paper’s status is not FBP, specifically on Friday of Week -2.

### Tasks:
- Develop email notification logic for Setter & Vetter based on paper status and timing.

---

## 12. File Visibility to Subject Teachers
### Description:
Subject teachers will be able to view files starting from BMT Week -1.

### Tasks:
- Implement file visibility for subject teachers from BMT Week -1.

---

## 13. Teacher View Interface
### Description:
Design the teacher interface for viewing BMT-related files and status.

### Tasks:
- Implement teacher’s view for managing BMT tasks.
- Display relevant files and status updates on teacher interface.

---

## 14. No Printing Request (SVE Submission Summary)
### Description:
Remove printing requests, and only include the BMT submission summary in the SVE.

### Tasks:
- Eliminate printing request functionality.
- Integrate BMT Submission Summary in the SVE.

---

## 15. BMT Weeklist Print
### Description:
Generate and allow printing of the BMT Weeklist.

### Tasks:
- Implement BMT Weeklist generation and printing functionality.

---

## WBS Outline

1. **Academic Subject Configuration**
   - Define subjects
   - Link paper types

2. **Paper Type Configuration**
   - Marking Scheme
   - Question Paper
   - Other Files
   - BMT Answer Sheet

3. **Workflow**
   - Define Vetter Process
   - Final Blueprint for Vetter
   - No expert process for BMT

4. **Exam Type Field**
   - Add field for Exam Type

5. **Academic Year Week Configuration**
   - Add week field
   - Remove end date parameter

6. **SVE Exam Date & BMT Week List**
   - Update SVE Exam Date
   - Use BMT Week List

7. **Duplication from Previous Year**
   - Week and Chapter duplication

8. **Approval Process**
   - Implement external approval
   - Update after approval

9. **Sync BMT Data**
   - Sync from previous year’s BMT

10. **Teacher File Visibility**
    - Visibility based on dates and status

11. **Email Notification**
    - Notify Setter/Vetter based on file status

12. **Teacher View of Files**
    - Teacher visibility from Week -1

13. **Teacher Interface**
    - Teacher’s view design

14. **Submission Summary (No Printing)**
    - Remove printing request
    - Add to Submission Summary

15. **BMT Weeklist Printing**
    - Implement print functionality
