# NYC Food Inspections

### Description
This project develops a comprehensive data handling and analysis solution for the Department of Health and Mental Hygiene (DOHMH) New York City restaurant inspection results. Utilizing an end-to-end ETL (Extract, Transform, Load) pipeline, this initiative aims to process and analyze data related to the inspections of restaurants and college cafeterias across New York City.

### Architecture Diagram
![Architecture Diagram](https://github.com/shantanup7/NYC-Hospitality-Health-Analytics/blob/main/Architecture%20Diagram%20%26%20Images/Architecture%20Diagram.jpeg)

### [Dataset Used](https://data.cityofnewyork.us/Health/DOHMH-New-York-City-Restaurant-Inspection-Results/43nn-pn8j/data_preview)

![Data Preview](https://github.com/shantanup7/NYC-Hospitality-Health-Analytics/blob/main/Architecture%20Diagram%20%26%20Images/Data%20Preview%20in%20Alteryx.jpg)

The data encompasses a range of inspection outcomes, including both sustained and non-adjudicated violations, from the past three years. Special focus is given to establishments in active status at the time of the data pull, including those newly opened that have not yet been inspected. Each record in the dataset provides detailed information about the establishment, such as its unique identifier (CAMIS), location, cuisine type, and the specifics of each inspection outcome.

### Data Fields Overview:
The dataset includes 27 fields, each providing specific information about the food establishments and their inspection outcomes:

- **CAMIS:** Unique identifier for each establishment.
- **DBA (Doing Business As):** The public business name of the establishment.
- **BORO:** The borough in which the establishment is located, with potential discrepancies noted between mailing and physical addresses.
- **Cuisine Description:** Type of cuisine offered by the establishment, as reported by the owner.
- **Inspection Date:** The date on which the inspection took place, with special notation for establishments awaiting their first inspection.
- **Violation Codes and Descriptions:** Details of any violations found during inspections.
- **Critical Flag:** Indicates whether a violation is considered critical to public health.
- **Grade:** The grade assigned to the establishment post-inspection, based on its compliance with health regulations.

### Tools and Technologies
- **Alteryx Designer:** Used for data preparation and ETL processes.
- **MS SQL Server:** Hosts the dimensional data model.
- **PowerBI:** Generates interactive dashboards for data visualization.
- **Tableau:** Generates interactive dashboards for data visualization.
- **ER/Studio:** Utilized for designing and refining the dimensional data model.

### Project Execution Flow
The project is organized into distinct phases, each designed to address specific stages of the data lifecycle from acquisition to analysis:

**Data Acquistion and Staging:**
- **Retrieve the Dataset:** Collect the initial raw data from the Department of Health and Mental Hygiene (DOHMH) on New York City restaurant inspections.
Load Data into Staging Tables (stg_): Import the raw data into staging tables for preliminary processing and inspection.

![Staging](https://github.com/shantanup7/NYC-Hospitality-Health-Analytics/blob/main/Part%201%20%26%202%20Data%20Profiling%20and%20Staging/New%20York%20City%20(NYC)%20Food%20Inspections%20Part%201%20Staging%20Table.JPG)

**Data Profiling and Cleaning:**
- **Data Consistency and Accuracy Analysis:** Examine the dataset for uniformity, precision, and completeness to identify any inconsistencies or anomalies.
- **Address Data Quality Issues:** Resolve identified data issues and refine the dataset to ensure it is clean and ready for further modeling and analysis.

![Data Profiling](https://github.com/shantanup7/NYC-Hospitality-Health-Analytics/blob/main/Part%201%20%26%202%20Data%20Profiling%20and%20Staging/New%20York%20City%20(NYC)%20Food%20Inspections%20Part%201%20Data%20Profiling.JPG)
  
**Dimensional Modeling:**
- **Design the Dimensional Model:** Construct a dimensional data model that facilitates complex analytical queries, enhancing data retrieval and analysis efficiency.
  
- **Dimension Tables:**
  - 1. DimNYC_Food_Places: Contains details about the food establishments.
  - 2. DimNYC_Cuisine: Lists types of cuisines found in the establishments.
  - 3. DimNYC_Violation_Codes: Includes codes and descriptions for potential violations.
  - 4. DimNYC_Borough: Information about the boroughs where establishments are located.
  - 5. DimNYC_Addresses: Addresses of the food establishments.
  - 6. DimNYC_Critical_Flag: Indicates the severity of the violations.
  - 7. DimNYC_Inspection_Actions: Actions taken during inspections.
  - 8. DimNYC_Inspection_Types: Types of inspections conducted.
  - 9. DimNYC_Inspection_Grades: Grades assigned post-inspection.
    
- **Fact Tables:**
  - 1. FactNYC_Food_Inspections: Central table recording each inspection event.
  - 2. FactNYC_FoodInspection_Violations: Specific violations noted during the inspections.

![Dimensional Model](https://github.com/shantanup7/NYC-Hospitality-Health-Analytics/blob/main/Part%203%20Dimensional%20Model%20into%20Integration%20Tables/NYC_Food_inspections_DimensionalModel.jpg)

**Data Integration:**
- **Load Processed Data:** Migrate the cleansed and structured data into the dimensional model hosted on MS SQL Server.
- **Utilize Alteryx Workflows:** Implement Alteryx workflows to automate the data transformation and loading processes, ensuring data integrity and timeliness.

![Data Integration Dimensions](https://github.com/shantanup7/NYC-Hospitality-Health-Analytics/blob/main/Part%203%20Dimensional%20Model%20into%20Integration%20Tables/Dimensions.JPG)

![Data Integration Facts](https://github.com/shantanup7/NYC-Hospitality-Health-Analytics/blob/main/Part%203%20Dimensional%20Model%20into%20Integration%20Tables/Facts.JPG)

**Business Intelligence and Reporting:**

- **Develop BI Dashboards:** Create interactive dashboards in PowerBI to dynamically visualize and analyze food inspection data.
  
- **Insight Generation:**
  - Track inspection results over time to monitor trends and changes.
  - Identify the most inspected and problematic establishments.
  - Analyze inspection outcomes by various dimensions, such as borough and cuisine type, to provide targeted insights.

![Tableau](https://github.com/shantanup7/NYC-Hospitality-Health-Analytics/blob/main/Part%204%20BI%20Dashboards/Tableau%20Dashboard.jpg)

![Power BI](https://github.com/shantanup7/NYC-Hospitality-Health-Analytics/blob/main/Part%204%20BI%20Dashboards/Power%20BI%20Dashboard.jpg)
