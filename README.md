# QA Metrics Dashboard
A Power BI dashboard project for tracking and visualizing software quality assurance metrics.

## Overview
This project is an interactive **Power BI Dashboard** designed to track, visualize, and analyze key Software Quality Assurance (QA) metrics. It provides data-driven insights into the health and progress of testing efforts, helping teams make informed decisions. The data source is a MySQL database populated with results from automated test runs and bug tracking.

## Features
- **Key Metrics Visualization:** Track test execution results, bug density, open/closed bug status, and test coverage.
- **Interactive Filters:** Filter data by date range, project, component, and tester.
- **Trend Analysis:** View historical trends of pass/fail rates and bug counts over time.
- **Data Refresh:** The dashboard is connected to a live database (or can be refreshed manually) to always display the latest data.
- **Export Functionality:** Allows users to export visualizations and underlying data for further analysis.

## Tech Stack
- **Power BI:** For data visualization and dashboard creation.
- **MySQL:** Relational database used as the data source.
- **Python / GitHub Actions (Optional):** Scripts to periodically export test results from other projects (e.g., Newman XML results) and populate the MySQL database.

## Project Structure
qa-metrics-dashboard/
├── data/ # Data source files and scripts

│ ├── database/ # SQL scripts for database schema creation

│ │ └── qa_metrics_schema.sql

│ └── scripts/ # Data processing/ETL scripts (e.g., Python)

│ └── results_importer.py

├── exports/ # Sample data exports (e.g., .csv) for backup

├── dashboard/ # Power BI files

│ └── QA_Metrics_Dashboard.pbix

└── documentation/ # Additional docs

└── METRICS_DEFINITION.md # Definitions of the calculated metrics
## Dashboard Metrics
The dashboard visualizes the following key QA metrics:
- **Test Execution Summary:** Total tests run, passed, failed, skipped.
- **Pass Rate Trend:** A line chart showing the pass rate over a selected time period.
- **Bug Status:** A pie chart showing the distribution of bugs (e.g., Open, In Progress, Closed, Rejected).
- **Bug Density:** Number of bugs found per module/component.
- **Test Coverage:** The percentage of requirements/user stories covered by test cases.

## Getting Started

### Prerequisites
- **Power BI Desktop:** (Free) to open and modify the `.pbix` file.
- **MySQL Server** (Optional): If you want to run a local instance of the database.

### Viewing the Dashboard
1. Download the `QA_Metrics_Dashboard.pbix` file from the `dashboard/` directory.
2. Open it with **Power BI Desktop**.
3. If prompted, configure the database connection to point to your own MySQL instance or click "Cancel" to explore the dashboard with the sample data embedded in the file.

### Setting Up the Database (Optional)
1. Run the SQL script `data/database/qa_metrics_schema.sql` on your MySQL server to create the necessary tables.
2. Use the provided Python script in `data/scripts/` (or your own ETL process) to populate the tables with data from your test automation frameworks (e.g., JUnit XML, Newman JSON output).

### Refreshing Data
- **Manual Refresh:** Open the .pbix file in Power BI Desktop and click "Refresh".
- **Scheduled Refresh:** Publish the report to the **Power BI Service** and configure a scheduled refresh by setting up a gateway to your data source.

## Sample Data
The `.pbix` file includes sample data to demonstrate the dashboard's functionality without requiring a live database connection.
