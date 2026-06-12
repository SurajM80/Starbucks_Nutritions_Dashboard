# ☕ Starbucks Nutrition Data Warehouse & Power BI Dashboard

## 📌 Project Overview

This project demonstrates an end-to-end **Data Engineering and Business Intelligence workflow** using the Starbucks Nutrition Dataset.

Instead of directly importing the CSV into Power BI, the data was transformed into a **Star Schema Data Warehouse** using **Python** and **MySQL** before being visualized through an interactive **Power BI Dashboard**.

The project focuses on **Data Modeling, ETL Processes, Data Warehousing, SQL Integration, and Business Intelligence Reporting**.

---

# 🎯 Objectives

- Analyze nutritional information of Starbucks beverages.
- Design a Data Warehouse using Star Schema.
- Create Fact and Dimension tables.
- Build an ETL pipeline using Python.
- Load transformed data into MySQL.
- Connect Power BI directly to MySQL.
- Develop an interactive dashboard for business insights.

---

# 🏗️ Project Architecture

```text
Starbucks CSV Dataset
          │
          ▼
     Python ETL
(Pandas Data Processing)
          │
          ▼
 Star Schema Modeling
          │
          ▼
      MySQL
 Data Warehouse
          │
          ▼
      Power BI
 Interactive Dashboard
```

---

# 🛠️ Tech Stack

### Programming
- Python
- Pandas

### Database
- MySQL
- MySQL Workbench

### Business Intelligence
- Power BI Desktop

### Data Modeling
- Star Schema
- Fact & Dimension Tables

---

# 📂 Dataset Information

The dataset contains nutritional information for Starbucks beverages, including:

- Beverage Category
- Beverage Name
- Beverage Preparation Type
- Calories
- Total Fat
- Saturated Fat
- Cholesterol
- Sodium
- Carbohydrates
- Sugars
- Protein
- Caffeine
- Vitamins & Minerals

### Dataset Size

| Metric | Value |
|----------|----------|
| Rows | 242 |
| Columns | 18 |

---

# 🔄 ETL Process

## 1️⃣ Extract

The Starbucks CSV file was loaded into Python using Pandas.

```python
df = pd.read_csv("starbucks.csv")
```

---

## 2️⃣ Transform

### Data Profiling

Performed:

- Row & Column Analysis
- Unique Value Analysis
- Data Structure Validation

### Dimension Table Creation

Created the following Dimension Tables:

#### DimCategory

| Category_ID | Beverage_category |
|------------|------------------|

#### DimBeverage

| Beverage_ID | Beverage |
|------------|-----------|

#### DimPrep

| Prep_ID | Beverage_prep |
|----------|---------------|

### Fact Table Creation

Created:

#### FactNutrition

Contains:

- Calories
- Total Fat
- Saturated Fat
- Sodium
- Carbohydrates
- Sugars
- Protein
- Caffeine
- Vitamin A
- Vitamin C
- Calcium
- Iron

Foreign Keys:

- Category_ID
- Beverage_ID
- Prep_ID

---

## 3️⃣ Load

Transformed tables were loaded into MySQL using:

```python
to_sql()
```

Tables Loaded:

- dim_category
- dim_beverage
- dim_prep
- fact_nutrition

---

# ⭐ Star Schema Design

```text
                 dim_category
                       │
                       │
dim_beverage ── fact_nutrition ── dim_prep
```

### Dimension Tables

| Table | Rows |
|---------|------|
| dim_category | 9 |
| dim_beverage | 33 |
| dim_prep | 13 |

### Fact Table

| Table | Rows |
|---------|------|
| fact_nutrition | 242 |

---

# 🗄️ MySQL Data Warehouse

A dedicated database was created:

```sql
CREATE DATABASE starbucks_dw;
```

The Star Schema was loaded into MySQL and used as the primary data source for Power BI.

---

# 📊 Power BI Dashboard

The Power BI dashboard was connected directly to MySQL and includes:

## Executive KPIs

- Total Beverages
- Average Calories
- Average Sugar
- Average Caffeine

## Visualizations

- Average Calories by Category
- Beverage Category Distribution
- Average Caffeine Analysis
- Top Caffeine Beverages
- Interactive Filtering by Beverage Preparation

## Features

- Dynamic Filtering
- Interactive Visuals
- Category-Level Analysis
- Nutrition Insights

---

# 💡 Key Learnings

Through this project, I gained practical experience in:

## Data Engineering

- ETL Pipeline Development
- Data Cleaning & Transformation
- Data Warehousing
- Star Schema Design
- Fact & Dimension Modeling
- MySQL Integration

## Business Intelligence

- Power BI Dashboard Development
- Data Visualization
- KPI Reporting
- Interactive Analytics

---

# 🚀 Future Improvements

- API Integration for Real-Time Data
- Automated ETL Scheduling
- Incremental Data Loading
- Cloud Data Warehouse Integration
- Apache Airflow Pipeline Orchestration
- Advanced Nutritional Analytics

---

# 📸 Project Screenshots

## Dashboard View

_Add Dashboard Screenshot Here_

## Star Schema Model View

_Add Model View Screenshot Here_

## MySQL Tables

_Add MySQL Workbench Screenshot Here_

---

# 👨‍💻 Author

**Suraj Madane**

Aspiring Data Engineer | Data Analyst | AI & Data Science Student

### Connect With Me

- LinkedIn: www.linkedin.com/in/surajmadane8392
- GitHub: https://github.com/Surajmadane8392

---

⭐ If you found this project interesting, feel free to connect and share your feedback.
