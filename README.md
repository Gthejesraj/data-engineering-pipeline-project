# 🚔 San Francisco Crime Pattern Analysis Pipeline

**A comprehensive data engineering pipeline for real-time crime data analysis using modern ETL processes, cloud data warehousing, and advanced analytics.**

---

## 📊 Project Overview

This project focuses on analyzing **San Francisco crime patterns** using real-time data ingestion pipelines, automated ETL workflows, and advanced data analytics. The data is sourced from the **Socrata API** (San Francisco's Open Data Portal) and is processed, cleaned, and loaded into a **Snowflake Data Warehouse**. Analytical models and dashboards are built using **DBT (Data Build Tool)** and visualization platforms.

---

## ⚙️ Tech Stack

### **Data Engineering & Orchestration**
- **Apache Airflow** - Workflow orchestration and ETL pipeline automation
- **Python & Pandas** - Data processing and transformation
- **Socrata API** - Real-time crime data ingestion from SF Open Data Portal

### **Data Storage & Analytics**
- **Snowflake** - Cloud data warehouse for scalable analytics
- **DBT (Data Build Tool)** - Data transformation, testing, and modeling
- **SQL** - Data querying and analysis

### **Visualization & Monitoring**
- **Power BI / Tableau** - Interactive dashboards and visualizations
- **ArcGIS** - Geographic mapping and spatial analysis

---

## 🚀 Key Features

### **1. Automated Data Ingestion**
- Real-time data fetching from Socrata API
- Dynamic updates based on last known incident date
- Duplicate data prevention and incremental loading

### **2. ETL Pipeline Orchestration**
- Automated ETL workflows with Airflow DAGs
- Data extraction, transformation, and loading processes
- Error handling and retry mechanisms

### **3. Advanced Data Modeling**
- Complex transformations using DBT
- Data integrity testing and validation
- Historical data snapshots for trend analysis

### **4. Real-time Analytics**
- Live crime data uploads to Snowflake
- Time-series analysis for crime trends
- Geographic heatmaps and spatial analysis

---

## 📂 Project Structure

```
data-engineering-pipeline-project/
├── dags/                          # Airflow DAGs
│   ├── API_ETL.py                # Main ETL pipeline
│   ├── Historical_upload_ETL.py  # Historical data upload
│   └── automated_dbt.py          # DBT automation
├── dbt_group_project/            # DBT project
│   ├── models/                   # DBT models
│   ├── tests/                    # Data quality tests
│   ├── seeds/                    # Reference data
│   └── snapshots/                # Historical snapshots
├── analyses/                     # Ad-hoc analysis
├── Images/                       # Project documentation images
└── README.md                     # Project documentation
```

---

## 🔄 Data Pipeline Architecture

```
[Socrata API] → [Airflow ETL] → [Snowflake Data Warehouse] → [DBT Models] → [Power BI/Tableau Dashboards]
```

### **Pipeline Flow:**
1. **Data Extraction**: Socrata API provides real-time SF crime data
2. **Orchestration**: Airflow manages ETL workflows and scheduling
3. **Storage**: Snowflake stores processed data for analytics
4. **Transformation**: DBT models clean and structure data
5. **Visualization**: Dashboards provide insights and analytics

---

## 🛠️ Setup & Installation

### **Prerequisites**
- Python 3.8+
- Apache Airflow
- Snowflake account
- DBT CLI

### **Installation Steps**

1. **Clone the repository**
   ```bash
   git clone https://github.com/Gthejesraj/data-engineering-pipeline-project.git
   cd data-engineering-pipeline-project
   ```

2. **Set up Airflow**
   ```bash
   # Install Airflow
   pip install apache-airflow
   
   # Initialize Airflow database
   airflow db init
   ```

3. **Configure DBT**
   ```bash
   cd dbt_group_project
   dbt deps
   dbt run
   ```

4. **Set up Snowflake connection**
   - Configure Snowflake credentials in Airflow connections
   - Update DBT profiles.yml with Snowflake connection details

---

## 📈 Key Metrics & Analytics

- **Crime Trends**: Time-series analysis of crime patterns
- **Geographic Analysis**: Spatial distribution of incidents
- **Category Analysis**: Breakdown by crime types
- **Temporal Patterns**: Hourly, daily, and seasonal trends

---

## 🔧 Usage

### **Running the ETL Pipeline**
```bash
# Start Airflow webserver
airflow webserver --port 8080

# Start Airflow scheduler
airflow scheduler

# Trigger DAG manually
airflow dags trigger API_ETL
```

### **Running DBT Models**
```bash
cd dbt_group_project
dbt run
dbt test
dbt docs generate
```

---

## 📊 Data Sources

- **Primary**: San Francisco Police Department via Socrata API
- **Data Types**: Incident reports, crime categories, locations, timestamps
- **Update Frequency**: Real-time/API-driven
- **Historical Coverage**: Multi-year crime data

---

## 🤝 Contributing

This project was developed as part of Data 226 coursework. For contributions or questions, please open an issue or contact the development team.

---

## 📄 License

This project is for educational purposes as part of academic coursework.
