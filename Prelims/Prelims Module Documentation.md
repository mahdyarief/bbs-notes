
## Overview
The **Prelims Module** is designed to manage, assign, grade, and calculate prelim exams across various levels including A Level, AS Level, and IGCSE. The system will integrate with the Cambridge curriculum and provide automated grading calculations, as well as threshold management for grades.

### Levels Supported
- **A Level (JC 2)**
- **AS Level (JC 2)**
- **IGCSE (JC 1 → English)**
- **IGCSE (Sec 4 → Selected Subjects)**

---

## Features

### 1. Subject Setup Using Cambridge
- Enable configuration of subjects for various levels: A Level, AS Level, and IGCSE (JC 1 & JC 2).
- Integrate Cambridge curriculum specifications for each subject level.

### 2. Prelim Assignment by Year and Flagging
- Automatically assign prelim exams to subjects based on year level (JC 1, JC 2, etc.).
- Add a flag (`Prelim`) to each subject to track and differentiate prelim exams.

### 3. Grading System Based on Components
- Implement grading for various components (e.g., TT1, others) using a weighted average approach.
- Components are linked to their respective subjects to calculate final grades.

### 4. Threshold Definition for AS Prelim Grades
- Define threshold grades for AS Prelims based on Cambridge standards.
- Support differentiation between grades for AS, A Level, and IGCSE levels.

### 5. Special Consideration for a* Grade
- For IGCSE, compute the threshold for the a* grade.
- The `a*` grade is calculated as the difference between Grade A and Grade B.

### 6. Yearly Average Calculation
- Implement a formula to calculate the Yearly Average based on multiple years' data.
- Utilize this Yearly Average to calculate final grades and thresholds.

### 7. Teacher Grade Calculation
- Use provided formulas to calculate grades based on the weighted average of components.
- Implement rounding logic for final grade calculations.

### 8. AS Grade Average Calculation
- Implement calculation of the AS grade average using a weighted formula.
- Ensure that this grade is rounded according to the specified rules.

### 9. Predicted Grades Calculation
- Implement logic for predicting grades based on the AS Average and compare them with the defined thresholds.
- Ensure the final predicted grades are calculated and rounded as per the rounding logic.

### 10. Prelims Predicted Grade Setting
- Enable functionality to set predicted grades for Prelims with configurable thresholds.
- Allow campus administrators to configure these threshold settings (default disabled).

---

## Work Breakdown Structure (WBS)

### 1. Prelims Module
#### 1.1 Subject Setup (A Level, AS Level, IGCSE)
- **1.1.1** Configure Cambridge subjects for JC1 & JC2
- **1.1.2** Define subjects for IGCSE (Sec 4)
- **1.1.3** Link subjects to the respective year levels

#### 1.2 Prelim Assignment System
- **1.2.1** Assign Prelim flag to subjects
- **1.2.2** Map Prelims to subjects based on year level

#### 1.3 Grading System Setup
- **1.3.1** Implement Component-based paper grading 
- **1.3.2** Link grading components to subjects
- **1.3.3** Define weightage for components

#### 1.4 Grade Thresholds
- **1.4.1** Define Prelim Grade Threshold for AS Level
- **1.4.2** Implement threshold logic for AS, A Level, and IGCSE

#### 1.5 a* Grade Calculation Logic
- **1.5.1** Set rules for calculating a* (Grade A - Grade B)
- **1.5.2** Implement a* logic for IGCSE and AS/A Level

#### 1.6 Yearly Average Calculation
- **1.6.1** Create formula to calculate yearly average
- **1.6.2** Ensure yearly average impacts final grade

#### 1.7 Teacher Grade Calculation Setup
- **1.7.1** Define and implement formulas for grade calculations
- **1.7.2** Implement rounding logic for final grades

#### 1.8 AS Average Grade Calculation
- **1.8.1** Implement AS Average formula
- **1.8.2** Integrate with threshold comparisons and grade prediction

#### 1.9 Predicted Grade Logic
- **1.9.1** Develop rules for AS Predicted Grade
- **1.9.2** Compare AS Average against thresholds
- **1.9.3** Implement grade rounding after calculation

#### 1.10 Prelims Predicted Grade Configuration
- **1.10.1** Implement predicted grade setting functionality
- **1.10.2** Allow campus admin to configure threshold settings
- **1.10.3** Set default disabled state for predicted grade feature

---

## AS PUM 

1. **Check Nilai AS Avg (AS Average) → Compare to AS Threshold**
   - Compare the AS Average grade to the threshold and select the appropriate threshold grade.
   - Formula to compare and calculate:
     - Formula:
       ```
       ((62 - 62) / (100 - 62)) * 20
       ```
     - The result will be used during the comparison process.

---

## Formula Breakdown

### a* Grade Calculation
The **a*** grade is calculated using the following formula:
```
a* = (Grade A - Grade B) + Grade A
```

### Yearly Average Calculation
The **Yearly Average** can be calculated by averaging the scores over multiple years, taking into account the weighted components:
```
Yearly Average = (Total Score from Year 1 + Total Score from Year 2 + ... + Total Score from Year n) / n
```

### AS Grade Average Calculation
For AS grades, the formula used to calculate the average for a specific paper component is:
```
AS Average = (25 / Total Mark (Highest Year) * 100) * (weighted / 100)
```

### Final Predicted Grade Calculation
Predicted grades are calculated based on the formula below:

- **Grade A***: 
  ```
  (((68 - 62) / (100 - Threshold)) * 20) + 90
  ```
- **Grade A**: 
  ```
  (((68 - 62) / (100 - Threshold)) * 20) + 80
  ```
- **Grade B**: 
  ```
  (((57 - 54) / (Threshold A - Threshold B)) * 10) + 70
  ```
- **Grade C**: 
  ```
  (((AS AVG - Threshold C) / (Threshold B - Threshold C)) * 10) + 60
  ```
- **Grade U**: 
  ```
  (((AS AVG - 0) / (Threshold E - 0)) * 39)
  ```

The final result is rounded according to the specified rounding rules.

---

## Prelims Predicted Grade Settings
Campus administrators can set up thresholds for predicted grades. These thresholds are used to compare against the student's average and calculate their predicted grade. 

Default configuration of predicted grades is disabled but can be enabled by the campus admin.

---

## Conclusion
This **Prelims Module** documentation provides a comprehensive overview of the system, features, and formulas used for grade calculation. It allows schools to set up, manage, and track Prelim grades across various subject levels, ensuring consistent grading and threshold application in line with Cambridge's standards.
