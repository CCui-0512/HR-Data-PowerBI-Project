# HR-Data-PowerBI-Project📊
<br>
This is an HR data 👥 Power BI project that showcases the end-to-end creation of a headcount report. 
<br>
It includes data modeling with a star schema in Power Query, DAX measures for headcount, interactive features like a slicer panel, and a custom-designed report layout.

---

## Final Report
![Final Report](./Showcase%20image/Final%20Report.png)

---

## Dataset

The dataset is synthetically generated and consists of two tables, 

each containing 4,138 records, covering employee demographics and employment status.

`/Datasets/people_data.csv` `/Datasets/people_employment_history.csv`

---

## 1.Data Modeling
  
### Objective
Organize two raw HR datasets in Power Query by structuring them into a **Fact Table** and **Dimension Tables**, reducing the size of the fact table and building a **star schema**.

### Specifications

- Identify and build the **fact table** using `employee ID`,`name`,`hire date`,`termination date`, and `active status`.  
- Create **dimension tables** by separating`demographics`,`education`,`department`,`location`,`job level`, and `manager`, while removing duplicates and blank values.  
- Join the fact and dimension tables, removing redundant columns and retaining only keys to reduce the size of the fact table.
   
![Star Schema Model](./Showcase%20image/Star%20schema%20model.png)

---

## 2.Calculating measures with Dax

### Objective
Calculate key HR metrics Headcount over time.

Avoid ambiguity caused by linking the Date table to both `hire_date` and `term_date`,  
by not creating relationships and instead referencing the Date table directly in DAX.

### Specifications

- **Headcount**  
  = employees hired before or on the selected date  
  AND (not exited OR exited after the selected date)

```
Headcount = CALCULATE(
    [All employees],
    FILTER(people_fact,people_fact[hire_date] <= LASTDATE('Date'[Date]) &&
        (people_fact[term_date] > LASTDATE('Date'[Date]) ||ISBLANK(people_fact[term_date]))))
```

---

## 3. Visualizing the Dashboard

### Objective
Visualize a headcount dashboard comparing key metrics with all possible dimensions within a selected timeframe.

### Specifications
- Build a customized background in PowerPoint and upload to PowerBI.  
- Design the layout step by step by drawing containers and filling them with visuals.  
- Choose an appropriate color scheme and the right visuals.

---
