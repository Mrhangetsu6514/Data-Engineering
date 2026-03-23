Data Engineering Pipeline: Airflow, Docker, & Tableau
🚀 Project Overview
This repository contains a containerized Apache Airflow environment designed to automate end-to-end data lifecycles. Originally built to power the Matzati.casa property platform, this architecture handles everything from complex web scraping of the Israeli rental market to triggering automated Business Intelligence (BI) refreshes in Tableau.

🏗️ Technical Architecture
For a deep dive into the system design, security protocols, and component interaction, please refer to our detailed documentation:
👉 View the ARCHITECTURE.md

🛠️ Tech Stack
Orchestration: Apache Airflow 3.1.7 (CeleryExecutor)

Containerization: Docker & Docker Compose

Database: PostgreSQL 16 (Metadata & Storage)

Messaging: Redis (Celery Broker)

BI Integration: Tableau Server Client (TSC) & REST API

Language: Python (Scraping, ETL, & DAG logic)

✨ Key Features
Automated BI Handshake: Automatically triggers Tableau extract refreshes only after data validation tasks succeed.

Security First: Implements a strict Zero-Hardcoding Policy. All sensitive credentials for the Airflow UI, Postgres, and Tableau are managed via encrypted environment variables.

Robust Scraping Pipelines: Includes production-ready scrapers designed to handle dynamic data extraction and storage.

Portability: Optimized docker-compose configuration with modular volume persistence and automated dependency management via requirements.txt.

🚦 Getting Started
Prerequisites
Docker and Docker Compose installed.

A Tableau Cloud/Server account (for BI automation features).

Installation
Clone the repository:

Bash
git clone https://github.com/Mrhangetsu6514/Data-Engineering.git
cd Data-Engineering
Configure Environment Variables:
Copy the template and fill in your specific credentials:

Bash
cp .env.example .env
Launch the Stack:

Bash
docker-compose up -d
Access the UI:
Open localhost:8080 and log in using the credentials defined in your .env file.

📈 Future Roadmap
Integration of Great Expectations for advanced data quality unit testing.

Implementation of Prometheus and Grafana for real-time container monitoring.

Expansion of the property pipeline to include historical price trend analysis.
