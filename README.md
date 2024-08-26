# Healthcare-Dashboard-Power-BI :
Objective: 

Create a comprehensive dashboard in Power BI to monitor and analyze key healthcare metrics such as patient admissions, average length of stay, and other relevant healthcare KPIs.



**Steps to Build the Healthcare Dashboard:**

1.Data Collection and Preparation



- Data Cleaning: Clean and transform the data to ensure consistency. Remove duplicates, handle missing values, and ensure data types are correct.



2. Data Modeling



- Relationships: Create relationships between tables. For example:

- Patient Info → Admissions (one-to-many)

- Admissions → Discharges (one-to-many)



3. **DAX Measures



DAX (Data Analysis Expressions) is a powerful formula language used in Power BI for calculations and data analysis. Here are some common DAX measures



- Total Admissions:



DAX

Total Admissions = COUNTROWS(Admissions)



- Total Discharges:



DAX

Total Discharges = COUNTROWS(Discharges)



-Average Length of Stay:

To calculate the average length of stay, you first need to create a measure for length of stay:



DAX

Length of Stay = DATEDIFF(Admissions[AdmissionDate], Discharges[DischargeDate], DAY)



Then, calculate the average:



DAX

Average Length of Stay = AVERAGEX(Admissions, [Length of Stay])



-Monthly Admission Trend:



  To visualize admissions trends over time, create a measure:



  DAX

  Monthly Admissions = CALCULATE(

    [Total Admissions],

    FILTER(

      ALL('Date'[Month]),

      'Date'[Month] = MAX('Date'[Month])

    )

  )

4. Creating Visualizations



-Key Performance Indicators (KPIs): Use KPI visuals to display metrics like Total Admissions, Average Length of Stay, etc.

- Charts and Graphs:

 - Line charts for trends over time (e.g., monthly admissions).

 - Bar charts for comparisons (e.g., admissions by department).

 - Pie charts for distribution (e.g., patient demographics).



- **Tables and Matrix Views:** For detailed data views, such as patient lists or detailed admission records.



5. Dashboard Design



**Conclusion**



A Healthcare Dashboard in Power BI can provide valuable insights by visualizing and analyzing healthcare data. Using DAX queries enhances ability to perform complex calculations and create meaningful metrics.
