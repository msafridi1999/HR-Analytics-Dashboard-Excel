# HR Analytics Dashboard (Microsoft Excel)

An interactive **HR Analytics Dashboard** built in **Microsoft Excel**.  
It uses PivotTables, PivotCharts, and slicers to explore workforce metrics like attrition, hiring year, department, job involvement, work–life balance, and more.

![Dashboard Overview](Dashboard..jpg)
![Pivot Overview](Screenshot 2025-08-15 204234.png)

> **Sheets:** `Dashboard`, `HR Data`, `pivot`  
> **Excel:** Office 365 / Excel 2019+

---

## 🔎 What’s inside the dashboard

**KPI Cards (from the screenshot):**
- **Total employees:** `2925`
- **Current employees (Attrition = No):** `2433`
- **Exit employees (Attrition = Yes):** `492`
- **Avg work–life balance:** `2.76`
- **Avg performance rating:** `3`

**Filters (Slicers):**
- **Attrition:** Yes / No  
- **Hiring Year:** 2020, 2021, 2022, 2023  
- **Department:** HR, R&D (…and any others present in data)

**Charts (per screenshot):**
- **Gender distribution** (Pie)  
- **Marital status distribution** (Column)  
- **Average Job Involvement by marital status** (Column)  
- **Education distribution by gender** (Clustered columns; Associates, Bachelor’s, Doctoral, High School, Master’s)  
- **Overtime count by marital status** (Yes/No columns)  
- **Travel distribution by marital status** (Non-Travel, Travel_Rarely, Travel_Frequently)

> Numbers update dynamically with slicers.

---

## 📁 Repository structure

hr-analytics-dashboard-excel/
├─ HR_Analytics_Dashboard.xlsx # Main workbook (Dashboard, HR Data, pivot)
├─ assets/
│ ├─ dashboard-overview.png # Screenshot of dashboard (rename yours to this)
│ └─ pivots-overview.png # Screenshot of pivot sheet (rename yours to this)
├─ data/ # (optional) place CSV/XLSX source files here
└─ README.md

## ▶️ How to use

1. **Clone or download** this repository.
2. Open **`HR_Analytics_Dashboard.xlsx`**.
3. Go to the **Dashboard** sheet.
4. Use the slicers (Attrition, Hiring Year, Department) to filter.
5. All KPI cards and charts will update automatically.
6. To refresh after data changes: **Data → Refresh All**.

---

## 🔧 Rebuild steps (if you want to recreate from scratch)

1. **Prepare the data**
   - Put your dataset on the **`HR Data`** sheet.
   - Convert it to an Excel Table (**Ctrl + T**) and name it `HR_Data`.

   **Common columns (as used in this dashboard):**
   - `emp no` (unique ID)  
   - `Gender`  
   - `MaritalStatus` (Single, Married, Divorced)  
   - `Attrition` (Yes/No)  
   - `Department` (HR, R&D, …)  
   - `Education` (High School, Associates Degree, Bachelor's Degree, Master's Degree, Doctoral Degree)  
   - `OverTime` (Yes/No)  
   - `BusinessTravel` (Non-Travel, Travel_Rarely, Travel_Frequently)  
   - `JobInvolvement` (numeric scale)  
   - `WorkLifeBalance` (numeric scale)  
   - `PerformanceRating` (numeric scale)  
   - `Hiring Year` (e.g., 2020–2023)

2. **Create PivotTables on the `pivot` sheet**
   - **Gender distribution:**  
     - Rows: `Gender`  
     - Values: `Count of emp no`
   - **Marital status distribution:**  
     - Rows: `MaritalStatus`  
     - Values: `Count of emp no`
   - **Avg Job Involvement by marital status:**  
     - Rows: `MaritalStatus`  
     - Values: `Average of JobInvolvement`
   - **Education distribution by gender:**  
     - Rows: `Gender`  
     - Columns: `Education`  
     - Values: `Count of emp no`
   - **Overtime by marital status:**  
     - Rows: `MaritalStatus`  
     - Columns: `OverTime` (Yes/No)  
     - Values: `Count of emp no`
   - **Travel distribution by marital status:**  
     - Rows: `MaritalStatus`  
     - Columns: `BusinessTravel`  
     - Values: `Count of emp no`
   - **KPI tables:**  
     - **Total Employees:** Values: `Count of emp no`  
     - **Current Employees:** Filter `Attrition = No`, Values: `Count of emp no`  
     - **Exit Employees:** Filter `Attrition = Yes`, Values: `Count of emp no`  
     - **Average WorkLifeBalance:** Values: `Average of WorkLifeBalance`  
     - **Average PerformanceRating:** Values: `Average of PerformanceRating`

3. **Insert PivotCharts**
   - Gender: Pie
   - Others: Clustered Column

4. **Add slicers & connect them**
   - Insert slicers for: `Attrition`, `Hiring Year`, `Department`.
   - Right-click each slicer → **Report Connections** → check all PivotTables/Charts.

5. **Build KPI cards**
   - Insert Shapes for each KPI and link text boxes to the cells holding the KPI values  
     (can use `=pivot!(...)` or direct pivot cells).

6. **Formatting**
   - Clean titles, labels, and number formatting

## 🧠 Interpreting the default (unfiltered) view

- **Gender:** Male `1754`, Female `1171`.  
- **Marital status:** Married `1340`, Single `934`, Divorced `651`.  
- **Avg Job Involvement:** ~`2.75` (Married & Divorced), `2.69` (Single).  
- **Overtime (counts):** Higher counts in Married and Single vs Divorced.  
- **Travel:** Most employees are **Travel_Rarely**, then **Travel_Frequently**, then **Non-Travel**.  
- **Education by gender:** All five levels are represented across Male/Female.




---

## 🖼️ Screenshots

Place your images here and use these names:
- `Screenshot 2025-08-15 204134.png`
- `Screenshot 2025-08-15 204234.png`


## 👤 Author

**Md Shahid Afridi**  
Data Analyst & BI Enthusiast
