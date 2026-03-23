---

# 🚀 Data Engineering Pipeline: Airflow, Docker, & Tableau

### *Orchestrating the Matzati.casa Property Platform & BI Automation*

[![Airflow Version](https://img.shields.io/badge/Airflow-3.1.7-blue?logo=apacheairflow)](https://airflow.apache.org/)
[![PostgreSQL](https://img.shields.io/badge/Database-PostgreSQL%2016-blue?logo=postgresql)](https://www.postgresql.org/)
[![Docker](https://img.shields.io/badge/Infrastructure-Docker-blue?logo=docker)](https://www.docker.com/)

---

## 📂 Project Structure

A clean, modular organization is maintained to ensure the scalability of the **Matzati** property listing tools:

```text
├── dags/                   # Python DAGs (Scrapers, ETL, Tableau Refreshes)
│   ├── property_pipeline.py # Core logic for Matzati listings
│   └── tableau_refresh.py  # Automation for BI extracts
├── config/                 # Airflow configuration files
├── plugins/                # Custom Airflow operators or sensors
├── .env.example            # TEMPLATE for secrets (Add to .gitignore!)
├── .gitignore              # Rules to exclude secrets and OS metadata
├── ARCHITECTURE.md         # Deep dive into system design
├── docker-compose.yaml     # Container orchestration (CeleryExecutor)
├── requirements.txt        # Python dependencies (TSC, Psycopg2)
└── README.md               # You are here
```

---

## 🛠️ Technology Stack

This project bridges the gap between raw data extraction and high-level marketing decision-making:

* **Orchestration:** **Apache Airflow 3.1.7** using `CeleryExecutor` for high-concurrency task management.
* **Containerization:** **Docker & Docker Compose** for environment isolation and portability.
* **Storage:** **PostgreSQL 16** for robust metadata management and listing storage.
* **BI Automation:** **Tableau Server Client (TSC)** via REST API for instant dashboard updates.

---

## 🛡️ Security & Portability

As a founder and developer, I prioritize **Infrastructure as Code (IaC)** and security best practices:

* **Zero-Hardcoding Policy:** All sensitive credentials for the Airflow UI, Postgres, and Tableau are managed through externalized environment variables.
* **Clean Version Control:** The `.gitignore` is optimized to block local Windows metadata (`*.Identifier`), environment backups (`.env.save`), and Python cache files.
* **Variable-Driven Config:** Internal connection strings (SQL Alchemy/Celery) are dynamically constructed using environment variables to prevent accidental exposure.

---

## 📘 Documentation

To understand the logic behind the "Tableau-Airflow Handshake" and the security implementation, see the full architectural breakdown:

### 🔗 [View the Technical ARCHITECTURE.md](./ARCHITECTURE.md)

---

## 🚀 Getting Started

### 1. Prerequisites
Ensure you have **Docker** and **Docker Compose** installed on your machine.

### 2. Configuration
The repository excludes private secrets. You must create your own `.env` file based on the provided template:
```bash
cp .env.example .env
# Edit .env with your specific Airflow and DB credentials
```

### 3. Deployment
Launch the entire stack with a single command:
```bash
docker-compose up -d
```
*Access the Airflow Web UI at `http://localhost:8080` using the credentials you defined in your `.env`.*

---

## 🏗️ Future Roadmap
* **Quality Gates:** Integrating data validation layers to ensure "clean" property data before BI ingestion.
* **Cloud Migration:** Preparing the Dockerized stack for deployment on AWS or GCP.

---

**Would you like me to help you format a specific "About the Founder" section to highlight your leadership at Matzati.casa in the README?**
