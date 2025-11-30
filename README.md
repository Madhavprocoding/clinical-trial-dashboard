Project Title: Clinical Trial Enrollment & Patient Compliance Dashboard

Objective:
The goal of this project is to analyze site-wise enrollment performance and patient visit compliance in an ongoing clinical trial. The dashboard helps track how many patients were enrolled, how they were distributed across different clinical sites, and how well they followed their visit schedules.

Data Used:
The project uses 5 tables:

Dim_Site

Dim_Patient

Dim_Date

Fact_Patient_Enrollment

Fact_Patient_Visits

Data Model:
A star schema was created with Fact tables in the center and Dimension tables linked using key fields like Site_ID, Patient_ID, and Date. This model helps to create accurate measures and visuals.

Key Calculations (DAX Measures):
The following measures were created:

Total Enrolled Patients – Count of patients marked as “Enrolled”

Recruitment Target % – Percentage of target reached by each site

Patient Compliance Rate – Completed visits vs. missed visits

Dropout Rate – Patients who withdrew from the study

Dashboard Visuals:
The main report page contains:

Three KPI Cards

Total Enrolled Patients

Recruitment Target %

Patient Compliance Rate

Bar Chart: Shows site-wise enrollment numbers

Slicer: Allows filtering dashboard by individual clinical sites

Insights:

Shows how many patients were enrolled at each site

Helps identify which sites are performing well or slow

Displays patient visit compliance (how many patients follow their schedule)

Helps clinical teams track recruitment progress and take action if targets are not met

Conclusion:
This dashboard provides a clear and simple view of clinical trial progress. It helps decision-makers monitor enrollment, track patient behavior, and improve site performance.
