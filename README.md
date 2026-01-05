# Customer Clustering and Sales Analytics

---
## Problem Statement

With rising competition and evolving customer expectations, insurers leverage data-driven intelligence to understand customer behavior and tailor their offerings accordingly. Customer segmentation provides a structured way to group individuals with shared characteristics, enabling more efficient targeting and marketing strategies.

---

## Project Summary

This project automates an end-to-end customer segmentation workflow, integrating raw data ingestion from **Google Sheets**, clustering analysis using **K-Prototypes** and **AI (Gemini)**, data warehousing in **Google BigQuery**, and daily refreshed **Power BI dashboards**. It is designed to deliver actionable insights for marketing and sales teams through a fully automated, cloud-based, and production-ready solution.

---
## Technologies Used

- **Python**: `pandas`, `seaborn`, `matplotlib`, `kmodes`, `gower`, `prince`, `sklearn`, `pandas-gbq`
- **Artificial Intelligence**: gemini-2.5-flash 
- **GitHub Actions**: automation of Python scripts
- **Google BigQuery**: SQL
- **Power BI**: real-time dashboards

---
## Highlights

- Fully automated from raw data to dashboard insights
- Real-world use of **mixed-type clustering** with K-Prototypes
- CI/CD-ready pipeline with GitHub Actions
- Cloud-native design using BigQuery + Power BI
- Business-friendly, scalable, and no manual refreshes required

---
## ETL Process
![Alt text](./ETL_pipeline.png)
---

## Workflow Overview

1. **Data Collection**  
   - Raw tables ([customers](https://docs.google.com/spreadsheets/d/1-NdLEzPBOxY7NfzDngoS4id9ekZ-eqIF7ZnX6JXdweg/edit?usp=sharing), [sales](https://docs.google.com/spreadsheets/d/1j3R2rUUAlUZO-2-x2OlMeMV23wgXZy7LfatlnCLsDJk/edit?usp=sharing), [products](https://docs.google.com/spreadsheets/d/1HpCKgERS0F9qjHh3y0_GZ988JjX4vtKBX5rIksCgB5I/edit?usp=sharing) maintained in Google Sheets by business users (e.g. Sales Department)

2. **Data Processing + Clustering**  
   - Python script at **Google Colab** loads data, cleans it, and applies **K-Prototypes clustering**
   - Mixed-type features handled using **FAMD** and **Gower distance**
  
3. **GitHub Actions Automation**  
   - Python script is loaded to Github and is scheduled to run daily at 10pm using GitHub Actions
   - Uses **secure service account authentication** via GitHub Secrets

4. **BigQuery Integration**  
   - Processed datasets are written to **Google BigQuery**
   - Clean **SQL views** are created for use in reporting

5. **Power BI Dashboard**  
   - Power BI connects directly to BigQuery views
   - Dashboards auto-refresh daily at 11pm to reflect the most current segmentation and sales data

---

## Schedule & Maintenance

| Layer           | Schedule             | Managed By         |
|----------------|----------------------|---------------------|
| Python Script  | Daily @ 10pm BST     | GitHub Actions      |
| BigQuery Views | Live / real-time     | Google BigQuery     |
| Power BI       | Daily @ 11pm BST     | Power BI Scheduler  |

---
