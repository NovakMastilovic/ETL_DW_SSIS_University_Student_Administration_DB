# About the project

This project was developed as part of the *Data Warehousing* course in the *Business Analytics* master’s program at the Faculty of Organizational Sciences, University of Belgrade. The project focuses on constructing a star schema data warehouse and implementing an ETL (Extract, Transform, Load) pipeline to analyze student success data from an OLTP (Online Transaction Processing) database using SQL Server Management Studio (SSMS) and SQL Server Integration Services (SSIS). 

## Project Overview

The primary goal of this project was to design and implement a data warehouse that captures detailed information about student performance, enabling efficient reporting and insights for academic administration. This project covers the full data warehousing process, from data extraction in an OLTP database to the ETL pipeline, schema design, and visualization, with a strong focus on technical implementations.

## Key Components

### 1. OLTP Data Source

- The OLTP database is the primary data source, holding detailed transactional data about students, including enrollment, course performance, exam results, and demographic data, provided by the course professor.
- For the full-size picture of the OLTP database, as an ER diagram, [click here](https://raw.githubusercontent.com/NovakMastilovic/SSIS_ETL_University_DB/refs/heads/main/University_OLTP_Database.png).
   
### 2. ETL Process

- **ETL Tools**: Implemented in SSMS and SSIS.
- **Data Extraction**: Extracted data from tables in the OLTP database, including `Student`, `Enrollment`, `Exam`, and `Course`.
- **Data Transformation**: Applied transformations such as data cleansing, dimension creation, and surrogate key generation. Ensured referential integrity by managing foreign key relationships.
- **Data Loading**: Loaded the transformed data into the data warehouse in a star schema structure for optimized query performance.

### 3. Data Warehouse Schema Design

- **Star Schema Structure**: Designed a star schema consisting of a central fact table (`Fact_ExamResults`) and associated dimension tables (`Dim_Student`, `Dim_Course`, `Dim_Date`, `Dim_Enrollment`).
  - **Fact Table**: Captures each exam attempt with associated student and course information, including score, date, and pass/fail status.
  - **Dimensions**: Contains details like student demographics, course details, exam dates, and enrollment information, with surrogate keys to simplify joins.
- **Surrogate Keys**: Used surrogate keys to ensure efficient joins and maintain referential integrity across the schema.

### 4. Data Transformation and Automation

- **SSIS Packages**: Developed multiple SSIS packages to automate each stage of the ETL process:
  - **Execute Package**: Manages sequential execution of ETL packages, enforcing order dependencies.
  - **DimStudent, DimCourse, DimDate Packages**: Create dimensions with attributes sourced from normalized OLTP tables.
  - **FactExamResults Package**: Builds the central fact table, connecting with all dimension tables.
- **Data Quality Checks**: Implemented SQL scripts to verify data consistency and ensure accurate transformation results.

### 5. Business Intelligence and Reporting

- **BI Tool**: Utilized Tableau for visualizing key insights.
- **Analysis Goals**: Answered research questions to analyze:
  - Impact of student demographics on academic success.
  - Correlation between high school performance and university success.
  - Course-specific trends in exam retakes and performance by program.
- **Dashboards**: Created interactive dashboards to provide actionable insights for academic administration.

## Project Outcomes

This project demonstrates key skills in data warehousing, ETL process design, and business intelligence, aligning well with both Data Analyst and Data Engineer roles. By working with complex data architectures, automation tools, and visualization techniques, I have developed a comprehensive understanding of the data pipeline lifecycle, from raw data extraction to actionable insights.

## Skills and Technologies

- **Data Warehousing**: Star schema design, fact and dimension modeling, surrogate keys, denormalization.
- **ETL**: SSMS, SSIS packages, data transformation, and automation.
- **SQL**: SQL Server for data querying, schema creation, and ETL automation.
- **Data Quality**: Data validation, referential integrity, and quality control measures.
- **Business Intelligence**: Tableau for dashboard creation and data visualization.
- **Data Pipeline Management**: End-to-end management of data from OLTP to OLAP for analytics and reporting.

---

**Project developed as part of the Data Warehousing course, Faculty of Organizational Sciences, University of Belgrade.**
