# HR-Data-PowerBI-Project📊
<br>
This is an HR data 👥 Power BI project that showcases the end-to-end creation of a headcount report. 
<br>
It includes data modeling with a star schema in Power Query, DAX measures for headcount, retention, and turnover, interactive features like a slicer panel, and a custom-designed report layout with a polished cover page.

---

## Datasets
Datasets are xxxxx

---

## 1.Data Modeling
  
### Objective
Organize two raw HR datasets in Power Query by structuring them into a **Fact Table** and **Dimension Tables**, reducing the size of the fact table and building a **star schema**.

### Specifications

- Create a new group and only reference the source data  
- Under the referenced tables:  
  - Identify and build the **Fact Table**
  - Create separate **Dimension Tables**, removing duplicates and blank values
    
- Merge the **Fact Table** with **Dimension Tables**   
  - Remove redundant descriptive columns from the fact table
  - Retain only keys to reduce data size and improve performance
   
![Star Schema Model](./Showcase%20image/Star%20schema%20model.png)

---

## 2.Calculating measures with Dax

### Objective
Calculate key HR metrics (Headcount, Retention Rate, Turnover Rate) over time.

Avoid ambiguity caused by linking the Date table to both `hire_date` and `term_date`,  
by not creating relationships and instead referencing the Date table directly in DAX.

### Specifications

- **Headcount**  
  = employees hired before or on the selected date  
  AND (not exited OR exited after the selected date)

- **Retention Rate**  
  = number of employees remaining during the period  
  / number of employees at the start of the period  

- **Turnover Rate**  
  = number of employees who left during the period  
  / ((start headcount + end headcount) / 2)

---
