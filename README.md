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

- Mark the two original datasets as Source and disable load  
- Create a new group and only reference the source data  

- Under the referenced tables:  
  - Identify and build the **Fact Table**  
  - Create separate **Dimension Tables**  
  - Clean duplicates and blanks
    
![Cleaned Data Model](./Showcase%20image/Cleaned%20data%20model.png)

- Merge the **Fact Table** with **Dimension Tables**  
  - Remove redundant descriptive columns from the fact table
  - Retain only keys to reduce data size and improve performance
   
![Star Schema Model](./Showcase%20image/Star%20schema%20model.png)

---
