📊 Clinical Trial Enrollment & Patient Compliance Dashboard

A Power BI dashboard that analyzes patient enrollment, site performance, and visit compliance trends in a clinical trial setting.

🚀 Project Overview

This project provides a clear and interactive view of clinical trial progress by tracking:

Patient enrollment across trial sites

Site-wise recruitment performance

Patient visit compliance (completed vs missed visits)

Dropout details and overall progress

The dashboard helps trial managers monitor performance in real-time and take corrective actions where needed.

📁 Project Structure

clinical-trial-dashboard/
│
├── Clinical_Trial_Dashboard.pbix        # Power BI Dashboard File
├── README.md                             # Project Documentation (This file)
└── /screenshots                          # Optional screenshots for clarity


📐 Data Model

The project uses a Star Schema that includes:

Dimension Tables

Dim_Site

Dim_Patient

Dim_Date

Fact Tables

Fact_Patient_Enrollment

Fact_Patient_Visits

Relationships are created using keys like:
Site_ID, Patient_ID, and date fields.

🧮 DAX Measures Used
Enrollment Metrics
Total Enrolled Patients =
CALCULATE (
    COUNTROWS ( Fact_Patient_Enrollment ),
    Fact_Patient_Enrollment[Status] = "Enrolled"
)

Recruitment Target % =
DIVIDE (
    [Total Enrolled Patients],
    SUM ( Dim_Site[Enrollment_Target] )
)

Compliance Metrics
Patient Compliance Rate :=
VAR CompletedVisits =
    COUNTROWS (
        FILTER (
            Fact_Patient_Visits,
            Fact_Patient_Visits[Visit_Statu] = "Completed"
        )
    )
VAR MissedVisits =
    COUNTROWS (
        FILTER (
            Fact_Patient_Visits,
            Fact_Patient_Visits[Visit_Statu] = "Missed"
        )
    )
RETURN
DIVIDE ( CompletedVisits, CompletedVisits + MissedVisits )

Dropout Metrics
Dropout Rate :=
VAR WithdrawnPatients =
    CALCULATE (
        COUNTROWS ( Fact_Patient_Enrollment ),
        Fact_Patient_Enrollment[Status] = "Withdrew"
    )
RETURN
DIVIDE ( WithdrawnPatients, [Total Enrolled Patients] + WithdrawnPatients )

📊 Dashboard Features
1️⃣ KPI Summary Cards

Total Enrolled Patients

Recruitment Target %

Patient Compliance Rate

2️⃣ Site-Wise Enrollment Chart

A bar chart showing enrollment distribution across trial sites.

3️⃣ Interactive Slicer

Filter all visuals by site to compare performance instantly.

Example:

<img width="1920" height="1080" alt="Screenshot 2025-11-30 220352" src="https://github.com/user-attachments/assets/749a5d55-4dcd-4626-8872-e01fbf0f73dd" />


📝 Insights From Dashboard

Shows overall patient enrollment and progress against recruitment targets

Highlights top and low-performing sites

Helps understand patient adherence and missed visits

Supports decision-making to improve site performance and compliance

🛠 Tech Used

Power BI Desktop

DAX (Data Analysis Expressions)

Star Schema Modeling

Excel Data Source (Mock Data)

📥 How to Use this Project

Download the .pbix file

Open it in Power BI Desktop

Interact with slicers, visuals, and metrics

Customize if needed

👨‍💻 Author

Your Madhav Ramesh Kanchewad
Aspiring Data Analyst | Power BI Developer

⭐ Support

If you like this project, consider giving the repository a star ⭐ on GitHub.
