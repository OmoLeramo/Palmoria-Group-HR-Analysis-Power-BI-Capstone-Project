# Palmoria-Group-HR-Analysis-Power-BI-Capstone-Project
## Project Overview
This repository contains my HR analytics project for Palmoria Group, a manufacturing company based in Nigeria, focused on analyzing gender distribution, salary structure, and bonus allocation to address potential gender inequality issues.
## Project Objectives
The analysis aims to provide management with actionable insights to:
- Understand the gender distribution across the company
- Identify potential gender pay gaps by region and department
- Evaluate compliance with the new $90,000 minimum salary regulation
- Recommend fair and transparent bonus allocation policies.
## Data Cleaning & Preparation
- Removed employees with missing salaries
- Removed records with department as NULL
- Assigned a generic gender label ("Undisclosed") where gender was missing
- Created a new ‘Region’ column via conditional logic
- Transformed ratings into a numeric scale using SWITCH() function
- Created salary bins in $1,000 intervals.
- created new dax coloumn for bonus amount and total compensation
- got the average salary by using the average function
## Tools Used
- Power BI (data modeling, visualization, DAX calculations)
- GitHub (version control & collaboration)
## Analytical Questions Answered
-  Gender Distribution;
Overall gender breakdown in the company, 
Gender distribution by region and department.
 - Employee Ratings Analysis; 
Distribution of employee performance ratings by gender
-  Salary Structure & Pay Gap; 
Average salary comparison by gender, 
Departmental and regional breakdown to identify possible pay gaps, 
Check compliance with the $90,000 minimum wage policy.
 -  Salary Band Distribution; 
Number of employees in salary bands ($10,000 increments), 
Visualization of salary distribution by region.
 -  Bonus Allocation;
Calculate bonus amount for each employee using provided performance-based rules, 
Compute total pay (salary + bonus) per employee, 
Summarize total payouts by region and company-wide.
  ## DAX Functions (SWITCH, AVERAGE, COUNT, calculated columns)
## Visuals: Pie Charts, Clustered Bar/Column Charts, Matrix, Tables, Slicers
    ## Dax Measures Used
   - Average Rating = AVERAGE('Palmoria Group emp-data'[Rating])
   - Average Salary = AVERAGE('Palmoria Group emp-data'[Salary])
   - Numeric Rating = SWITCH('Palmoria Group emp-data'[Rating],"Poor", 1,
    "Average", 2,
    "Good", 3,
    "Excellent", 4,
    0  -- default if no match
     - Employee above threshold = CALCULATE(COUNTROWS('Palmoria Group emp-data'), 'Palmoria Group emp-data'[Salary] > 90000)
     - Total Salary = 'Palmoria Group emp-data'[Salary] +'Palmoria Group emp-data'[Bonus Amount]
   - Bonus Amount = 'Palmoria Group emp-data'[Salary]*IF('Palmoria Group emp-data'[Rating]="Very Poor", RELATED('bonus mapping'[Very Poor]),IF('Palmoria Group emp-data'[Rating]="Poor",RELATED('bonus mapping'[Poor]),IF('Palmoria Group emp-data'[Rating]="Average",RELATED('bonus mapping'[Average]),IF('Palmoria Group emp-data'[Rating]="Good",RELATED('bonus mapping'[Good]),IF('Palmoria Group emp-data'[Rating]="Very Good",RELATED('bonus mapping'[Very Good]),BLANK())))))
     ## Insights & Interpretations
- Gender Distribution
   - Male employees represent 52.1% of the workforce, while females make up 43.2%, and 4.3% chose not to disclose.
   - This suggests potential gender imbalance, especially in certain departments and regions (e.g., North West).
- Salary Structure & Pay Gap
  - Average salary across the organization is $90,035.
  - shows a gender pay gap, particularly in Legal, Support, and Engineering departments, where male employees earn significantly more on average than female employees.
  - Approximately 105 employees earn below the $90,000 regulatory minimum, highlighting an immediate compliance risk.
- Salary Band Distribution
   - A large number of employees fall into lower salary bands ($20,000–$60,000), emphasizing the need for salary adjustments to retain talent and meet legal requirements.
-  Bonus Allocation
   - Total bonus payout is $2,199,279, with the highest allocations in the North Central and North West regions.
   - Aligning bonus distribution with fair and transparent performance reviews can help improve employee satisfaction and reduce perceived bias.
- Department & Region Focus
  -  Departments such as Legal, Support, and Engineering show significant male dominance and wider pay gaps, suggesting these areas should be prioritized for corrective actions.
  -   North West region exhibits the largest male workforce concentration.
   ## Overall Recommendations
- Address pay gaps by reviewing and adjusting salaries in targeted departments.
- Ensure regulatory compliance by immediately raising salaries below $90,000.
- Promote more balanced gender representation, especially in male-dominated areas.
- Improve transparency and fairness in performance appraisals and bonus policies to foster employee trust.
  ## Status
  - Completed


   ![Screenshot (85)](https://github.com/user-attachments/assets/4df974ba-3627-4b48-aee1-6549db19984f)
![Screenshot (78)](https://github.com/user-attachments/assets/b1d284f5-37f9-43f2-b6e6-56d1b7c14276)
