# About the project

This project was developed as part of the *Data Warehousing* course in the *Business Analytics* master’s program at the Faculty of Organizational Sciences, University of Belgrade. The project focuses on constructing a **star schema** data warehouse and implementing an **ETL** (Extract, Transform, Load) pipeline to address key research questions using data from an **OLTP** (Online Transaction Processing) database — **University Student Administration**.

The data used in this project is not real but consists of mixed and anonymized records, serving as a simulation for educational purposes. The ETL process was implemented using **SQL Server Management Studio** (SSMS) and SQL **Server Integration Services** (SSIS).

## Scope of the project - Research questions

This project tracks two main business processes: monitoring student success and analyzing course exam performance. Each of these processes includes two key research questions, as outlined here:
- Do demographic characteristics of students affect their academic success?
- Are high school performance and entrance exam results good predictors of student success in university?
- Are there specific exams that students tend to postpone until the October exam period?
- Does a student’s study program affect their grades in specific subjects?

The first two research questions focus on tracking student success in exams, while the last two questions focus on analyzing subjects and comparing difficulty levels across study modules.

## Project Components

### 1. OLTP Data Source - University Student Administration Database

- The OLTP database is the primary data source, holding detailed transactional data about students, including enrollment, course performance, exam results, and demographic data, provided by the course professor.
- For the full-size picture of the OLTP database, as an ER diagram, [click here](https://raw.githubusercontent.com/NovakMastilovic/SSIS_ETL_University_DB/refs/heads/main/University_OLTP_Database.png).
   
### 2. Identifying Key Tables from the OLTP Database

To build a data warehouse that could effectively address the research questions, a thorough selection process was applied to the OLTP **University Student Administration Database**. This process ensured that only the most relevant tables were included in the star schema to optimize data storage, retrieval, and analysis.

#### Table Selection Process

- **OLTP Database Review**: Initially, the entire OLTP schema was reviewed to understand the data structure and identify tables that could contribute meaningful insights.
- **BI Model Canvas**: A BI (Business Intelligence) Model Canvas was used to identify which tables were essential for the analysis. This model helped define:
  - **End Users**: Faculty administration and student advisors.
  - **Data Attributes**: Demographic details, exam scores, enrollment periods, and course-specific performance metrics.
  - **Analytical Needs**: Insights into student demographics, course performance, exam retake patterns, and program-specific success rates.

#### Selected Tables

The following tables were chosen based on their relevance to the research questions and their potential contribution to the data warehouse structure:
- **Student**: Captures demographic details, high school background, and entrance exam scores, allowing for demographic and academic performance analysis.
- **Course**: Contains information on courses, linking each student to subjects taken and enabling course-level performance analysis.
- **Enrollment**: Details the enrollment periods and student status, allowing for time-based analyses.
- **Exam Results**: Tracks individual exam attempts, scores, and pass/fail status, forming the basis for the fact table in the data warehouse.

By focusing on these tables, the data warehouse is optimized to provide answers to the research questions while avoiding unnecessary data complexity and storage.


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
