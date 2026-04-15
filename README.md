# 👥 HR Employee Attrition Analysis

![Excel](https://img.shields.io/badge/Excel-Data%20Cleaning-217346?style=for-the-badge&logo=microsoftexcel&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-Data%20Analysis-4479A1?style=for-the-badge&logo=mysql&logoColor=white)
![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![GitHub](https://img.shields.io/badge/GitHub-Version%20Control-181717?style=for-the-badge&logo=github&logoColor=white)

---

## 📌 Project Overview

Employee attrition is a critical challenge for organizations, leading to increased hiring costs, productivity loss, and reduced employee morale.

This project performs an end-to-end HR analytics study using the IBM HR Employee Attrition dataset to identify key factors influencing employee turnover and provide actionable insights.

---

## 👩‍💻 My Contribution

This project was independently completed by me as part of my data analytics learning journey.  
AI tools were used only for improving documentation and presentation.

---

## 🎯 Business Problem

> "What are the key factors driving employee attrition, and how can organizations reduce employee turnover and improve retention?"

---

## 📂 Dataset Information

| Attribute | Details |
|-----------|---------|
| Source | IBM HR Analytics Dataset (Kaggle) |
| File | `hr_employee_attrition.csv` |
| Records | 1,470 employees |
| Features | 35 columns |
| Target Variable | Attrition (Yes / No) |

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|------|---------|
| Microsoft Excel | Data Cleaning & Preprocessing |
| MySQL Workbench | Data Analysis using SQL |
| Power BI Desktop | Dashboard & Visualization |
| GitHub | Version Control |

---

## 🔄 Project Workflow

Dataset → Excel Cleaning → MySQL Analysis → Power BI Dashboard → GitHub

---

## 🧹 Data Cleaning (Excel)

- Duplicate Check — No duplicate records found  
- Null/Blank Check — No missing values found  
- Data Type Correction — Numeric columns formatted correctly  
- Outlier Detection — No significant outliers in MonthlyIncome  
- Irrelevant Columns Identified — `StandardHours`, `EmployeeCount`  

---

## 📊 Key Metrics Defined

- Attrition Rate = (Employees who left / Total Employees) × 100  
- Active Employees = Total Employees − Attrition Count  
- Overtime Impact = Attrition comparison based on overtime status  

---

## 🔍 SQL Analysis (MySQL)

| # | Business Question | Key Insight |
|---|------------------|-------------|
| Q1 | Overall Attrition Rate | 16.12% — above industry standard |
| Q2 | Department Wise Attrition | Sales highest (20.63%) |
| Q3 | Age Group Wise Attrition | Below 25 highest (39.18%) |
| Q4 | Gender Wise Attrition | Male (17.01%) > Female (14.80%) |
| Q5 | Job Role Wise Attrition | Sales Representative highest (39.76%) |
| Q6 | Salary Wise Attrition | Low salary highest (28.61%) |
| Q7 | Overtime Impact | Overtime employees 30.53% |
| Q8 | Job Satisfaction Impact | Low satisfaction 22.84% |
| Q9 | Years at Company | 0–2 years highest (29.82%) |
| Q10 | Work Life Balance Impact | Poor WLB 31.25% |

---

## 📊 Power BI Dashboard

### Page 1 — Overview
- KPI Cards: Total Employees, Attrition Count, Attrition Rate  
- Gauge Chart: Attrition Rate vs Target  
- Department Wise Attrition  
- Attrition by Overtime  
- Attrition by Gender  

### Page 2 — Detailed Analysis
- Age Group Wise Attrition  
- Salary Group Wise Attrition  
- Job Role Wise Attrition  
- Experience Wise Attrition  
- Work Life Balance Analysis  

---

## 💡 Key Findings

- Overall Attrition Rate: **16.12%**
- Employees below 25 show highest attrition  
- Sales department has maximum turnover  
- Low salary employees leave more frequently  
- Overtime significantly increases attrition risk  
- New employees (0–2 years) are more likely to leave  
- Poor work-life balance leads to higher attrition  

---

## ✅ Business Recommendations

| Issue | Recommendation |
|------|---------------|
| Young employee attrition | Career development & mentorship programs |
| Low salary attrition | Competitive compensation benchmarking |
| Overtime burnout | Flexible work policies |
| Sales attrition | Improved incentives & realistic targets |
| New joiner attrition | Strong onboarding programs |
| Work-life imbalance | Employee wellness initiatives |

---

## 🏁 Conclusion

The analysis shows that attrition is mainly driven by age, salary, overtime, and work-life balance.

By applying targeted HR strategies, organizations can reduce employee turnover and improve retention.

This project highlights how data-driven insights support better business decision-making.

---

## 📁 Repository Files

| File | Description |
|------|-------------|
| `hr_employee_attrition.csv` | Dataset |
| `SQL_QUERY_01.png` – `SQL_QUERY_10.png` | SQL outputs |
| `hr_attrition_dashboard.pdf` | Power BI dashboard |
| `README.md` | Documentation |



