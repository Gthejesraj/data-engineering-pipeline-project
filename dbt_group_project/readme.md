### 📊 **San Francisco Crime Pattern Analysis with Airflow, Snowflake, and DBT** 🚔

---

### **Project Overview**

This project focuses on analyzing **San Francisco crime patterns** using real-time data ingestion pipelines, automated ETL workflows, and advanced data analytics. The data is sourced from the **Socrata API** (San Francisco's Open Data Portal) and is processed, cleaned, and loaded into a **Snowflake Data Warehouse**. Analytical models and dashboards are built using **DBT (Data Build Tool)** and visualization platforms like **Power BI/Tableau**.

---

### ⚙️ **Tech Stack**

- **Airflow**: For orchestration and automation of ETL pipelines.
- **Snowflake**: Cloud-based data warehouse for storage and analytics.
- **DBT**: Data transformation, testing, and analytics.
- **Socrata API**: For fetching real-time crime data from San Francisco’s open data portal.
- **Python & Pandas**: Data preprocessing and transformation.
- **Power BI / Tableau**: For visualization of crime patterns.

---

### 🚀 **Key Features**

1. **Automated Data Ingestion**  
   - Fetches real-time data from the **Socrata API**.
   - Dynamically updates based on the **last known incident date** to avoid duplicate data ingestion.

2. **Real-Time Data Upload**  
   - Live crime data is uploaded directly to the Snowflake Data Warehouse via Airflow DAGs.

3. **ETL Workflow with Airflow**  
   - Automated ETL pipelines handle **data extraction**, **transformation**, and **loading** into Snowflake.

4. **Advanced Data Modeling with DBT**  
   - Perform complex transformations.
   - Test data integrity and create data snapshots for historical analyses.

5. **Visualization & Analysis**  
   - Interactive dashboards with **geographic heatmaps** (using Power BI/Tableau/ArcGIS).
   - Time-series analysis to identify crime trends over time.

---

### 📊 **Data Pipeline Architecture**

```
[Socrata API] --> [Airflow ETL] --> [Snowflake Data Warehouse] --> [DBT Models] --> [Dashboards in Power BI/Tableau]
```

---

### 🗃️ **Project Structure**

```
.
├── dags/
│   ├── socrata_to_snowflake_dag.py         # Fetches and processes data from Socrata API
│   ├── docker_etl_snowflake.py             # Uploads live data to Snowflake
│   └── dbt_etl_dag.py                      # Runs DBT models for data transformation
├── data/
│   └── filtered_data.csv                   # Intermediate data for Snowflake upload
├── dbt/
│   └── police_reports/                     # DBT models, snapshots, tests
├── README.md                               # Project documentation
└── requirements.txt                        # Python dependencies
```

---

### ⚡ **Airflow DAGs**

#### 1️⃣ **`socrata_to_snowflake_dag.py`**

- **Extract**: Fetch crime data using Socrata API.
- **Transform**: Clean, filter, and preprocess the data.
- **Load**: Insert data into Snowflake.

#### 2️⃣ **`docker_etl_snowflake.py`**

- Automates data uploads to Snowflake from CSV files using `PUT` and `COPY INTO` commands.

#### 3️⃣ **`dbt_etl_dag.py`**

- **DBT Run**: Executes data models to transform raw data.
- **DBT Test**: Runs tests to ensure data quality.
- **DBT Snapshot**: Tracks changes in historical data for time-series analysis.

---

### 🔍 **Key SQL & DBT Operations**

- **Data Cleaning**: Handling missing values, standardizing datetime formats.
- **Aggregations**: Calculating incident counts by neighborhoods, categories, and time periods.
- **Geospatial Analysis**: Mapping incidents with latitude/longitude coordinates.

---

### 📈 **Dashboard Highlights**

- **Heatmaps**: Identify high-crime areas in San Francisco using **ArcGIS** and **Power BI**.
- **Trend Analysis**: Visualize monthly/yearly crime trends.
- **Category Breakdown**: Analyze crimes by type (theft, assault, vandalism, etc.).

---

### 🔑 **Setup Instructions**

1. **Clone the Repository**

   ```bash
   git clone https://github.com/your-repo/sf-crime-analysis.git
   cd sf-crime-analysis
   ```

2. **Set Up Airflow**

   ```bash
   docker-compose up -d
   ```

3. **Configure Snowflake**

   - Set up Snowflake connection in Airflow (`Admin → Connections` → Add `snowflake_default`).

4. **Run the DAGs**

   - Trigger DAGs in Airflow UI (`http://localhost:8080`).

5. **DBT Operations**

   ```bash
   cd dbt/police_reports
   dbt run
   dbt test
   dbt snapshot
   ```

---

### 📝 **Future Enhancements**

- Real-time data streaming with **Kafka**.
- Advanced ML models to predict crime patterns.
- Integration with **GeoJSON** for advanced geospatial analytics.

---

### 👤 **Author**

**Pranav Reddy Gaddam**  
*Master’s in Data Analytics @ San José State University*  
*Email: pranavreddy.gaddam@sjsu.edu | GitHub:github.com/PranavReddyGaddam*

---

Let me know if you'd like to add or modify any specific sections. 🚀
