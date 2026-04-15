# HR Employee Attrition Analysis

## 📌 Project Overview

Employee attrition is a major challenge in organizations. This project analyzes employee data using SQL, Excel, and Power BI to identify key factors influencing attrition and provide actionable business insights.

---

## 🎯 Objective

* Analyze employee attrition patterns
* Identify key factors causing employee turnover
* Provide data-driven recommendations

---

## 🛠️ Tools Used

* SQL
* Excel
* Power BI

---

## 📊 Dataset

This project uses the IBM HR Analytics dataset.

* **Source**: IBM HR Analytics Dataset (Kaggle)
* **File**: `hr_employee_attrition.csv`
* **Records**: 1470 employees
* **Features**: 35 columns
* **Target Variable**: Attrition (Yes/No)

📥 [Download Dataset](hr_employee_attrition.csv)

---

# 🧠 SQL Analysis with Output & Insights

---

## 🔹 1. Overall Attrition Rate

### SQL Query

```sql
SELECT attrition,
COUNT(*) AS employee_count,
ROUND(COUNT(*) * 100.0 / (SELECT COUNT(*) FROM hr_employee_attrition1), 2) AS percentage
FROM hr_employee_attrition1
GROUP BY attrition;
```

### Output

![Attrition Rate](attrition_rate.png)

### Insight

The overall attrition rate shows the percentage of employees leaving the organization. A higher percentage indicates a need for strong retention strategies.

---

## 🔹 2. Attrition by Department

### SQL Query

```sql
WITH dept_attrition AS (
    SELECT department,
    COUNT(*) AS total_employees,
    SUM(CASE WHEN attrition = 'Yes' THEN 1 ELSE 0 END) AS attrition_count
    FROM hr_employee_attrition1
    GROUP BY department
)
SELECT department, total_employees, attrition_count,
ROUND(attrition_count * 100.0 / total_employees, 2) AS attrition_rate
FROM dept_attrition
ORDER BY attrition_rate DESC;
```

### Output

![Department Attrition](department_attrition.png)

### Insight

Departments with higher attrition rates may indicate workload issues, lack of growth opportunities, or management challenges.

---

## 🔹 3. Attrition by Age Group

### SQL Query

```sql
WITH age_group AS (
    SELECT 
    CASE 
        WHEN age < 25 THEN 'Below 25'
        WHEN age BETWEEN 25 AND 34 THEN '25-34'
        WHEN age BETWEEN 35 AND 44 THEN '35-44'
        WHEN age BETWEEN 45 AND 54 THEN '45-54'
        ELSE '55+'
    END AS age_group,
    attrition
    FROM hr_employee_attrition1
)
SELECT age_group,
COUNT(*) AS total_employees,
SUM(CASE WHEN attrition = 'Yes' THEN 1 ELSE 0 END) AS attrition_count,
ROUND(SUM(CASE WHEN attrition = 'Yes' THEN 1 ELSE 0 END) * 100.0 / COUNT(*), 2) AS attrition_rate
FROM age_group
GROUP BY age_group
ORDER BY attrition_rate DESC;
```

### Output

![Age Group](age_group_attrition.png)

### Insight

Younger employees tend to have higher attrition, possibly due to career growth opportunities and job switching behavior.

---

## 🔹 4. Attrition by Salary

### Salary Group Definition

* Low: Below 3000
* Medium: 3000 – 6000
* High: 6000 – 10000
* Very High: Above 10000

### SQL Query

```sql
WITH salary_grouping AS (
    SELECT 
    CASE 
        WHEN monthlyincome < 3000 THEN 'Low'
        WHEN monthlyincome BETWEEN 3000 AND 6000 THEN 'Medium'
        WHEN monthlyincome BETWEEN 6000 AND 10000 THEN 'High'
        ELSE 'Very High'
    END AS salary_group,
    attrition
    FROM hr_employee_attrition1
)
SELECT salary_group,
COUNT(*) AS total_employees,
SUM(CASE WHEN attrition = 'Yes' THEN 1 ELSE 0 END) AS attrition_count,
ROUND(SUM(CASE WHEN attrition = 'Yes' THEN 1 ELSE 0 END) * 100.0 / COUNT(*), 2) AS attrition_rate
FROM salary_grouping
GROUP BY salary_group
ORDER BY attrition_rate DESC;
```

### Output

![Salary](salary_attrition.png)

### Insight

Employees earning below 3000 show significantly higher attrition compared to higher salary groups, indicating compensation dissatisfaction as a key driver.

---

## 🔹 5. Attrition by Overtime

### SQL Query

```sql
WITH overtime_attrition AS (
    SELECT overtime,
    COUNT(*) AS total_employees,
    SUM(CASE WHEN attrition = 'Yes' THEN 1 ELSE 0 END) AS attrition_count
    FROM hr_employee_attrition1
    GROUP BY overtime
)
SELECT overtime, total_employees, attrition_count,
ROUND(attrition_count * 100.0 / total_employees, 2) AS attrition_rate
FROM overtime_attrition
ORDER BY attrition_rate DESC;
```

### Output

![Overtime](overtime_attrition.png)

### Insight

Employees working overtime show higher attrition, suggesting workload pressure and poor work-life balance.

---

## 🔹 6. Job Role Analysis

### Output

![Job Role](jobrole_attrition.png)

### Insight

Certain job roles experience higher attrition due to stress, workload, or limited growth opportunities.

---

## 🔹 7. Job Satisfaction

### Output

![Satisfaction](satisfaction_attrition.png)

### Insight

Employees with low job satisfaction tend to leave more frequently.

---

## 🔹 8. Work-Life Balance

### Output

![Work Life Balance](worklife_balance_attrition.png)

### Insight

Poor work-life balance strongly contributes to employee attrition.

---

# 🔥 Combined Insights

* Employees with low salary and overtime show the highest attrition
* Younger employees leave more frequently
* Poor work-life balance increases turnover

---

# 💣 Business Problem

The organization faces high attrition due to:

* Low compensation
* High overtime
* Poor work-life balance

---

## 📊 Power BI Dashboard

📁 File: `hr_attrition_dashboard.pdf`

### Dashboard Insights

* Attrition is highest among low salary employees
* Overtime workers leave more
* Certain departments show higher attrition

---

# 💡 Recommendations

* Improve salary structure
* Reduce overtime workload
* Improve employee engagement
* Enhance work-life balance

---

# ✅ Conclusion

This project identifies key drivers of employee attrition and provides actionable insights to improve retention.
