# 🧪 AWS Glue DataBrew – README

## 📘 Overview

**AWS Glue DataBrew** is a visual data preparation tool that allows **data analysts and data scientists** to clean, transform, and normalize data without writing code. It supports more than **250 built-in transformations** to prepare data for analytics, machine learning (ML), and reporting.

> Think of it as a **no-code spreadsheet on steroids** for data cleansing and preparation.

---

## 🧱 Key Features

- 🖱️ **Point-and-click interface** for cleaning and transforming data
- 🔁 Apply **over 250 built-in data transformations**
- 🧪 Profile data quality (missing values, outliers, statistics)
- 💾 Export jobs to Amazon S3 or Redshift
- 🛠️ Integrates with AWS Glue, S3, Redshift, and more
- 📊 Supports JSON, CSV, Parquet, Excel, and other formats
- 🔄 Automate transformations as scheduled jobs

---

## 🔄 Common Use Cases

| Use Case                       | Why DataBrew?                            |
| ------------------------------ | ---------------------------------------- |
| Data cleaning                  | Remove duplicates, nulls, fix types      |
| Data preparation for ML        | Feature extraction, normalization        |
| Exploratory data analysis      | Visual profiling and quick insights      |
| Ad-hoc transformations         | Drag-and-drop logic without writing code |
| Preprocessing before analytics | Ready data for Athena/Redshift queries   |

---

## 🔧 How It Works

Source Data (S3, Redshift, etc.)
↓
Create Dataset in DataBrew
↓
Apply Transformations (no-code UI)
↓
Save as Recipe
↓
Run Job → Export Result to S3 / Redshift

---

## ⚙️ Supported Data Sources

- Amazon S3
- Amazon Redshift
- AWS Glue Data Catalog
- Amazon Aurora / RDS (via JDBC)
- Upload local files (via S3)

---

## 🧠 Key Concepts

### 📁 Dataset

A reference to data stored in S3, Redshift, or Data Catalog.

### 🧪 Project

The workspace where you interactively clean, preview, and transform data.

### 📜 Recipe

A **reusable set of transformation steps** applied to a dataset.

### ⚙️ Job

A **scheduled or on-demand process** that applies a recipe to full data and writes output to a target location (S3, Redshift).

---

## 🔍 Data Profiling Features

- Column-level stats: min, max, mean, std deviation
- Nulls and unique counts
- Distribution charts
- Outlier detection
- Data type inference
- Schema mismatches

---

## 📦 Example Transformations

| Category          | Examples                               |
| ----------------- | -------------------------------------- |
| Cleaning          | Remove duplicates, fill missing values |
| Formatting        | Change case, convert data types        |
| Deriving          | Extract date parts, substring          |
| Aggregation       | Group by, count, sum                   |
| Conditional Logic | If/Then/Else rules                     |
| Joins & Lookups   | Join datasets using keys               |

---

## 🔒 Security & Access

- IAM permissions for DataBrew resources
- Data access via VPC and KMS encryption
- Logging and job monitoring via **CloudWatch**

---

## 🛠️ Getting Started

### 1. Create Dataset

Choose data from:

- Amazon S3
- Redshift
- AWS Glue Catalog

### 2. Start a Project

- Choose a dataset and a new or existing recipe
- Launch the **visual interface**

### 3. Apply Transformations

- Use the toolbar or right-click menus to clean/transform
- Preview results live

### 4. Save Recipe

- Reuse the recipe in other projects/jobs

### 5. Create Job

- Run the recipe on full dataset
- Output to S3, Redshift, or Glue Data Catalog

---

## 📊 Pricing

- Charged per **DataBrew session** (project time)
- Charged per **DataBrew job run**
- Pricing varies by region, refer to [DataBrew Pricing](https://aws.amazon.com/glue/pricing/)

---

## 🧠 Tips & Best Practices

- Split large files for faster previews
- Profile datasets before running transformations
- Reuse recipes across multiple datasets
- Schedule jobs for hourly/daily ETL processing
- Use S3 bucket policies to control access

---

## 🧰 Integrations

- Amazon S3 (input/output)
- Amazon Redshift (JDBC)
- AWS Glue (Data Catalog integration)
- Amazon Athena (query outputs)
- Amazon QuickSight (for visualization)

---

## 📚 References

- [AWS Glue DataBrew Documentation](https://docs.aws.amazon.com/databrew/index.html)
- [What is AWS Glue DataBrew?](https://aws.amazon.com/glue/features/databrew/)
- [DataBrew Tutorials](https://docs.aws.amazon.com/databrew/latest/dg/tutorials.html)
- [Pricing](https://aws.amazon.com/glue/pricing/)

---

## ✅ Summary

| Component | Description                                |
| --------- | ------------------------------------------ |
| Dataset   | Source data for cleaning                   |
| Project   | Interactive transformation UI              |
| Recipe    | Saved list of no-code transformation steps |
| Job       | Executes recipe on full dataset            |
| Output    | S3, Redshift, or Glue Catalog              |

---
