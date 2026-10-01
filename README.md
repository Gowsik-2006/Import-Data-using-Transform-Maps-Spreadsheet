# Import Data using Transform Maps (Spreadsheet)

A ServiceNow micro project demonstrating how employee data from a spreadsheet can be imported, transformed, validated, and visualized using ServiceNow Import Sets, Transform Maps, Coalesce, Reports, and Dashboards.

## 📌 Project Overview

This project demonstrates an end-to-end employee data import workflow in ServiceNow.

The workflow starts with employee information maintained in a spreadsheet. The spreadsheet is loaded into a ServiceNow Import Set staging table, mapped to a custom target table using a Transform Map, and transformed into employee records.

The project also demonstrates Coalesce for handling existing records during subsequent imports. Finally, reports and a dashboard are created to provide different views of the imported employee information.

## 🎯 Objectives

- Prepare structured employee data in spreadsheet format.
- Create a custom ServiceNow table for employee records.
- Create an Import Set table for staging spreadsheet data.
- Configure a Transform Map between source and target tables.
- Map source fields to the appropriate target fields.
- Transform and validate imported records.
- Configure Coalesce for matching existing records.
- Demonstrate insert, update, and ignore behavior.
- Create reports based on department and location.
- Create an employee list report.
- Combine the reports in an Employee Analytics Dashboards dashboard.

## 🛠️ Technology & ServiceNow Components

**Platform:** ServiceNow

**Data Source:**
- Google Spreadsheet
- Microsoft Excel (`.xlsx`)

**ServiceNow Components:**
- Custom Tables
- Import Sets
- Load Data
- Transform Maps
- Field Maps
- Mapping Assist
- Auto Map Matching Fields
- Coalesce
- Transform History
- Reports
- Dashboards

## 🗃️ Data Structure

### Target Table

| Property | Value |
|---|---|
| Label | Employee Test |
| Name | `u_employee_test` |

### Fields

| Field | Type |
|---|---|
| Employee ID | String |
| Employee Name | String |
| Email | String |
| Department | String |
| Location | String |

## 📥 Import Set

The spreadsheet is first loaded into an Import Set staging table.

| Property | Value |
|---|---|
| Label | Employee Import |
| Name | `u_employee_import` |

The Import Set acts as the staging area between the spreadsheet and the target ServiceNow table.

## 🔄 Transform Map

### Transform Map Configuration

| Property | Value |
|---|---|
| Transform Map | Sample Spreadsheet Import |
| Source Table | Employee Import |
| Target Table | Employee Test |

The Transform Map controls how fields from the Import Set are transferred into the Employee Test table.

The project uses:
- Auto Map Matching Fields
- Mapping Assist
- Field Maps
- Transform

## 🔑 Coalesce

Coalesce is configured on a selected field mapping within the Transform Map.

The documented configuration changes the selected field from:

`False → True`

This allows the selected field to be used for matching incoming data against existing records.

### Documented Test Results

For one test:

| Result | Count |
|---|---:|
| Rows Uploaded | 4 |
| Inserted | 2 |
| Updated | 2 |

When the same spreadsheet is imported again:

| Result | Count |
|---|---:|
| Rows Uploaded | 4 |
| Inserted | 0 |
| Updated | 0 |
| Ignored | 4 |

These results demonstrate the documented repeated-import behavior.

## 📊 Reports

Three reports are created from the **Employee Test** table.

### 1. Employees by Department

- Type: Pie Chart
- Group By: Department
- Aggregation: Count

### 2. Employees by Location

- Type: Bar Chart
- Group By: Location
- Aggregation: Count

### 3. Employee List Report

- Type: List

Columns:
- Employee ID
- Employee Name
- Email
- Department
- Location

## 📈 Dashboard

### Employee Analytics Dashboards

The following reports are added to the dashboard:

- Employees by Department
- Employees by Location
- Employee List Report

The dashboard provides a consolidated view of the employee information.

## 🔄 Project Workflow

```text
Spreadsheet
     │
     ▼
Employee Import
     │
     ▼
Sample Spreadsheet Import
     │
     ▼
Employee Test
     │
     ├───────────────┐
     ▼               ▼
 Reports         Dashboard
     │               │
     └───────► Employee Analytics Dashboards
```

## 🧩 Project Phases

### Phase 1 — Prepare the Spreadsheet

- Create the sample Google Spreadsheet.
- Enter employee data.
- Download the spreadsheet as an Excel file.

### Phase 2 — Create Custom Table

- Create Employee Test.
- Configure the target table fields.
- Verify the table form.

### Phase 3 — Import Set Table

- Open Load Data.
- Create Employee Import.
- Upload the spreadsheet.
- Create the Transform Map.

### Phase 4 — Create Transform Map

- Configure Sample Spreadsheet Import.
- Select source and target tables.
- Use Auto Map Matching Fields.
- Use Mapping Assist.
- Save the mappings.
- Execute the transformation.

### Phase 5 — Transform Data & Validate

- Open Employee Test.
- Verify imported records.
- Configure the displayed columns.
- Confirm the transformed data.

### Phase 6 — Enable Coalesce

- Open the Transform Map.
- Open Field Maps.
- Enable Coalesce on the selected field.
- Save the configuration.

### Phase 7 — Insert New Data

- Load updated Excel data.
- Use the existing Employee Import table.
- Run the Transform.
- Review Transform History.
- Verify inserted and updated records.
- Repeat the import and verify ignored records.

### Phase 8 — Create Reports

Create:
1. Employees by Department
2. Employees by Location
3. Employee List Report

### Phase 9 — Add Reports to Dashboard

- Create Employee Analytics Dashboards.
- Add the three reports.
- Verify the completed dashboard.

## 🧪 Validation

The project validates:

- Spreadsheet loading
- Import Set creation
- Transform Map configuration
- Source-to-target field mapping
- Successful transformation
- Employee records in Employee Test
- Coalesce behavior
- Inserted records
- Updated records
- Ignored records during repeated imports
- Report creation
- Dashboard configuration

## 📸 Screenshot Evidence

The project includes screenshot evidence organized into four milestones:

```text
Screenshots/
├── Milestone 1/
├── Milestone 2/
├── Milestone 3/
└── Milestone 4/
```

The complete step-by-step documentation contains all **40 supplied screenshots**, with each documented step accompanied by its corresponding screenshot evidence.

## 📚 Documentation

The project documentation includes the detailed implementation steps and screenshot evidence.

Recommended repository structure:

```text
ServiceNow_Project/
│
├── README.md
│
├── Documentation/
│   ├── Import Data using Transform Maps.docx
│   └── ServiceNow_Import_Data_using_Transform_Maps_Complete_Steps_and_All_Screenshots.docx
│
├── Screenshots/
│   ├── Milestone 1/
│   ├── Milestone 2/
│   ├── Milestone 3/
│   └── Milestone 4/
│
└── Project Files/
```

## 👥 Team

| Role | Name |
|---|---|
| Team Leader | Gowsik Raja S |
| Team Member | Shrija M |
| Team Member | Swetha M |
| Team Member | Sivaram A |

### Team ID

`6ab7f27c8c7c66e7067292d1`

## 📋 Project Outcome

The project demonstrates an end-to-end employee data import workflow in ServiceNow:

```text
External Spreadsheet
        ↓
Import Set
        ↓
Transform Map
        ↓
Field Mapping
        ↓
Employee Test
        ↓
Coalesce
        ↓
Validation
        ↓
Reports
        ↓
Dashboard
```

It demonstrates how spreadsheet data can be staged, transformed, validated, and presented through ServiceNow reports and dashboards.

## 📝 Notes

This README is based on the supplied ServiceNow project guide and screenshot evidence.

The project documentation does not specify formal deployment dates, external APIs, custom application code, separate external databases, or formal performance benchmarks. Such information has therefore not been added to this README.

## 📄 License

This repository contains academic/project work. Add an appropriate license if the project is intended for public reuse.
