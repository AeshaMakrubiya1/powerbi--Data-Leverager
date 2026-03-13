
# 🌟 PR.1 Data Leverager – Power BI Project  
An aesthetically designed and professionally documented **Power BI ETL + Data Modeling Project** demonstrating real‑world data cleaning, transformation, merging, automation, and refresh simulation.

---

## ✨ **Project Overview**
This project uses **Employee Data** and **Monthly Sales Files (Jan–Apr)** to build a fully dynamic, refresh-enabled Power BI model.  
The purpose is to showcase complete mastery of **Power Query**, including text cleaning, numeric processing, time intelligence, merging, appending, aggregation, parameters, and automated refresh behavior.

---

# 📁 **1. Data Sources**
### 🔹 Employee Dataset (500 rows)  
Contains: EmployeeID, Name, Department, Region, Birthdate, Hire Date, Salary, Grade, City, Email  

### 🔹 Monthly Sales Files (500 rows each)  
- Sales_January.xlsx  
- Sales_February.xlsx  
- Sales_March.xlsx  
- Sales_Apr.xlsx (for refresh simulation)  

All files were loaded using **Folder Connector** for automation.

---

# 🧹 **2. Data Cleaning & Basic Transformations**
- Removed blank rows & unnecessary columns  
- Renamed columns for clarity  
- Fixed data types (Date, Number, Text)  
- Sorted required columns  
- Removed duplicate entries  
- Normalized column names (Pascal Case)  

---

# 🔤 **3. Text Standardization Tools**
Used Power Query functions to clean & standardize:

| Function | Purpose |
|---------|----------|
| `UPPER()` | Convert text to uppercase |
| `LOWER()` | Convert text to lowercase |
| `TRIM()` | Remove extra spaces |
| `CLEAN()` | Remove hidden characters |
| `REPLACE()` | Replace part of text |
| **Split Column by Delimiter** | Split names, city-state, etc. |

This ensures consistent data formatting across all tables.

---

# 🔢 **4. Numeric Transformations**
- Rounded numeric columns to **2 decimal places**  
- Created **Total Sales**:
  ```
  Total = Quantity * Price
  ```
- Validated numeric errors using Column Profiling  

---

# 🗓️ **5. Date & Time Intelligence**
### Extracted components from OrderDate:
- Day  
- Month  
- Year  
- Quarter  

### Created a **Fiscal Month**:
```m
let m = Date.Month([OrderDate]) 
in if m >= 4 then m - 3 else m + 9
```

### Calculated **Age** from Birthdate:
```m
Age = Number.RoundDown(Duration.Days(DateTime.LocalNow() - [Birthdate]) / 365)
```

---

# 🧩 **6. Conditional Columns & Indexing**
### Sales Category created:
- **High** ≥ 10,000  
- **Medium** 5,000–9,999  
- **Low** < 5,000  

### Index Columns Added:
- 0‑based index  
- 1‑based index  

---

# 🔗 **7. Merging & Appending**
### 🔹 **Merge Queries**
Sales data merged with Employee data using:
- EmployeeID  
- Region (as optional relationship check)  

### 🔹 **Append Queries**
January + February + March sales combined using:
```
Append Queries as New
```
April added later to test refresh behavior.

---

# 📊 **8. Grouping & Aggregation**
Grouped by **Region** to calculate:
- Total Sales  
- Average Order Value  
- Number of Transactions  

This helps build powerful visuals & summaries.

---

# 🧪 **9. Data Profiling & Quality Validation**
Enabled:
- Column Quality  
- Column Distribution  
- Column Profile  

Used to:
- Detect missing values  
- Identify errors  
- Analyze unique/distinct values  

---

# ⚙️ **10. Folder Parameters & Source Settings**
- Created **Dynamic Folder Path Parameter**  
- Ensured model updates automatically when new files arrive  
- Updated credentials via **Data Source Settings**  

This enables professional-grade automation.

---

# 🔁 **11. Refresh Simulation (April File Test)**
### Steps performed:
1. Added new file → **Sales_Apr.xlsx** to the folder  
2. Clicked **Refresh** in Power BI  
3. Verified:
   - New file auto-loaded  
   - Append logic updated  
   - All transformations applied successfully  

✔ This confirms the model is fully **refresh-ready & scalable**.

---

# 📝 **12. Project Deliverables**
- ✔ 1- Data Leverager.pbix (Final Power BI Report)  
- ✔ Employee + Sales Data Model  
- ✔ All Transformations Applied  
- ✔ Dynamic Refresh Demonstration  
- ✔ README.md Documentation  

---

# 🎉 **Conclusion**
This project demonstrates complete expertise in:
- Power Query ETL  
- Data Cleaning & Shaping  
- Merging & Appending  
- Date/Time Intelligence  
- Automated Data Refresh  
- Professional BI Documentation  
---

