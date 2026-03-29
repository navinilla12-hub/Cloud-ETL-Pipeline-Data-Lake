#  Cloud ETL Data Pipeline with Data Lake Architecture

##  Overview
This project demonstrates the design and implementation of a scalable **ETL (Extract, Transform, Load) pipeline** using a **data lake architecture**. The pipeline processes real-world NYC Taxi trip data and transforms it into analytics-ready datasets.

The system follows a **multi-layered architecture**:
- **Bronze Layer** → Raw data ingestion  
- **Silver Layer** → Cleaned and transformed data  
- **Gold Layer** → Aggregated, analytics-ready data  

---

##  Architecture
        ┌───────────────┐
        │  Raw Dataset  │
        └──────┬────────┘
               ↓
      🟤 Bronze Layer
     (Raw Data Storage)
               ↓
      ⚪ Silver Layer
  (Cleaned & Transformed)
               ↓
      🟡 Gold Layer
  (Aggregated Insights)

  
---

##  Tech Stack

- **Programming:** Python  
- **Data Processing:** Pandas  
- **Storage Format:** Parquet  
- **Architecture:** Data Lake (Bronze/Silver/Gold)  
- **Environment:** Google Colab  
- **Concepts:** ETL Pipelines, Data Validation, Partitioning  

---

##  Dataset

- **Source:** NYC Taxi Trip Data  
- **Format:** Parquet  
- **Data Includes:**  
  - Trip timestamps  
  - Distance traveled  
  - Fare and revenue  
  - Passenger activity  

---

##  Pipeline Workflow

### 1. Data Ingestion (Bronze Layer)
- Raw dataset is ingested and stored without modification  
- Ensures reproducibility and traceability  

### 2. Data Cleaning & Transformation (Silver Layer)
- Removed null and invalid records  
- Converted timestamps to proper formats  
- Engineered new features:
  - Trip duration  
- Filtered invalid trips (negative duration, zero distance)  

### 3. Data Aggregation (Gold Layer)
- Created daily-level analytics dataset  
- Metrics generated:
  - Average trip distance  
  - Average fare  
  - Total revenue  
  - Average trip duration  

---

##  Data Validation

Implemented validation checks to ensure:
- No missing values  
- No negative distances or revenue  
- Data consistency across pipeline stages  

---

##  Optimization Techniques

- Used **Parquet format** for efficient storage  
- Implemented **partitioning (year/month)** for scalable querying  
- Designed modular pipeline structure for reusability  

---

##  Sample Output

| Date       | Avg Distance | Avg Fare | Total Revenue | Avg Duration |
|------------|-------------|----------|--------------|-------------|
| 2023-01-01 | 3.2         | 12.5     | 120000       | 18.4 mins   |

---

##  Project Structure
cloud-etl-data-pipeline-data-lake/
README.md
etl_pipeline.ipynb
requirements.txt
sample_output/
gold_sample.csv


---

##  Key Learnings

- Designing scalable ETL pipelines  
- Implementing data lake architecture  
- Data cleaning and transformation workflows  
- Ensuring data quality and reliability  
- Structuring data for analytics and reporting  

---

##  Future Improvements

- Integrate **Apache Spark** for distributed processing  
- Add **Airflow orchestration** for scheduling pipelines  
- Deploy pipeline on **AWS (S3 + Glue + Athena)**  
- Add real-time streaming using Kafka  

---

##  How to Run

1. Open the notebook in **Google Colab**  
2. Upload the dataset (Parquet file)  
3. Run all cells sequentially  
4. Output will be stored in:
   - `/bronze/`
   - `/silver/`
   - `/gold/`

---

