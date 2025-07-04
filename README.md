# *AI-Lung-Diagnostics : End-to-End Data Understanding, Exploration, and Cleaning in MySQL*

**Author:** *Niranjan Kumar*  
**Date:** *30 June 2025*

---

## *Project Overview*

*This project showcases how raw healthcare data is handled in a real-world industry scenario entirely within a SQL database environment. The focus is on demonstrating the practical steps that data analysts and engineers typically follow to understand, explore, and clean data to make it ready for deeper analysis, reporting, or modeling.*

*The dataset used here represents patient-level information related to lung cancer, including demographic details, medical history, diagnostic timelines, and treatment outcomes. All steps were performed in MySQL Server using standard SQL queries, highlighting how large datasets are commonly managed in production environments where structured storage, consistency, and traceability are critical.*

---

## 1. Data Understanding

The first phase aimed to build a complete understanding of the dataset’s structure, size, and initial quality before moving into detailed exploration or transformations.

Key tasks performed:

- **Verified record count:** Checked the total number of rows to understand the dataset’s scale and assess potential data processing requirements.
- **Verified column count:** Checked the total number of columns to confirm that all relevant features are available.
- **Reviewed schema:** Retrieved and reviewed the list of all column names to understand what fields are included.
- **Inspected data samples:** Viewed the first few rows to validate that the data looks consistent and free from obvious structural issues.
- **Checked data types:** Verified the data type of each column to confirm that numerical, categorical, and date fields are stored appropriately.
- **Identified missing values:** Investigated key columns for NULL or missing values that could affect downstream analysis.
- **Checked for duplicate records:** Searched for duplicate rows to ensure that the dataset does not contain redundant entries which could bias results.

This foundational step ensures confidence in the data structure and highlights any immediate issues that need addressing before deeper work begins.

---

## 2. Data Exploration

With a clear understanding of the dataset’s shape and content, the next step focused on exploring the actual data distributions to detect anomalies, validate assumptions, and confirm that the data aligns with real-world expectations.

### Continuous Variables

- Identified important continuous columns, specifically `age`, `bmi`, and `cholesterol_level`, which are critical for patient health analysis.
- Examined minimum and maximum values to ensure these variables fall within realistic and medically plausible ranges.
- Performed basic outlier checks by comparing value ranges to expected human health parameters to catch invalid or extreme entries.

### Categorical Variables

- Identified major categorical columns including `gender`, `country`, `cancer_stage`, `family_history`, `smoking_status`, and `treatment_type`.
- Reviewed unique categories for each field to verify consistency and detect any spelling errors, unexpected categories, or formatting inconsistencies.
- Analyzed frequency distributions to check for imbalanced categories or unusual patterns that may need attention.

This exploration step bridges the gap between raw data and meaningful insights by highlighting potential areas that require cleaning or transformation.

---

## 3. Data Cleaning

Following data understanding and exploration, practical cleaning operations were carried out to improve the dataset’s usability and ensure consistency for future analysis.

Key cleaning tasks included:

- **Standardized binary columns:** Several binary variables (`hypertension`, `asthma`, `other_cancer`, `survived`) were originally stored as numeric flags (`0` and `1`). These were transformed into more interpretable string labels (`'No'` and `'Yes'`) to make the dataset more readable and consistent for non-technical stakeholders.
- **Adjusted column data types:** The binary columns were converted from numeric to text (`VARCHAR`) to properly store the new labels without errors.
- **Used batch updates for large data volumes:** Updates were run in safe, controlled batches using `LIMIT` and safe update mode adjustments to handle high row counts without causing server timeouts or accidental full-table modifications.
- **Validated cleaning results:** After each transformation, distinct values were checked to ensure that no residual numeric flags remained and that only the intended text values were present.

Through this methodical cleaning phase, the dataset was prepared to meet real-world standards for clarity, accuracy, and reliability.

---

## Project Outcome

By following these steps, the lung cancer dataset was systematically understood, explored, and cleaned within MySQL Server using industry-standard SQL practices. This process reflects how raw data is typically prepared inside production databases before being handed off to business intelligence teams, data scientists, or analysts for further modeling, visualization, and insight generation.

The cleaned and standardized dataset is now suitable for more advanced tasks such as statistical testing, exploratory data analysis in Python, dashboard creation, or the development of predictive models to support healthcare research and decision-making.

---

## Tools and Technologies Used

- **MySQL Server** for database management and SQL execution
- **MySQL Workbench** for writing and running queries and managing the database

---

## Next Steps

Future work will include exporting the cleaned dataset for further analysis in Python, creating visual dashboards, performing deeper statistical tests, or developing machine learning pipelines to generate actionable insights for healthcare applications.

---
