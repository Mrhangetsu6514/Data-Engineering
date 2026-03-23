Gemini said
To showcase your technical leadership and the 3 years of experience you bring to your projects, an ARCHITECTURE.md file should explain the "Why" behind your technical decisions. This document bridges the gap between your role as a founder and your technical execution.

Here is a professional draft you can use for your repository:

System Architecture: Automated Data Orchestration
Project Overview
This project serves as the automated backbone for data operations, specifically designed to bridge the gap between web-scraped property data and Business Intelligence (BI) visualization. By containerizing the environment, we ensure that the pipeline is reproducible, secure, and scalable.

1. Core Components
Orchestration Layer (Apache Airflow)
Executor: Uses the CeleryExecutor with a Redis broker to allow for concurrent task execution, essential for handling multiple scraping jobs simultaneously.

Dynamic DAGs: Custom Python DAGs manage the end-to-end flow, from triggering scrapers to validating data before it reaches the BI layer.

Storage Layer (PostgreSQL)
Metadata Database: A dedicated PostgreSQL 16 container stores Airflow’s internal state, job history, and connection configurations.

Data Integrity: The architecture uses volume persistence (postgres-db-volume) to ensure data is not lost if containers are restarted or updated.

Visualization Integration (Tableau)
Automated Refreshes: The system utilizes the Tableau Server Client (TSC) to trigger extract refreshes via the REST API immediately after new data is processed.

Decoupled Design: By using Airflow as the trigger, we ensure Tableau only updates when the underlying data is confirmed as "clean" and "complete."

2. Security & Best Practices
Secret Management
Zero-Hardcoding Policy: No sensitive credentials (database passwords, Tableau tokens, or Airflow UI logins) are stored within the code or Docker files.

Environment Variables: The system relies on a modular .env architecture. A .env.example template is provided to allow other developers to safely configure their own local environments.

Repository Cleanliness
Advanced Filtering: The .gitignore is configured to exclude local metadata (like Windows Zone.Identifier files), environment backups (.env.save), and Python cache files to maintain a professional, production-ready repository.

3. Workflow Diagram
Trigger: Airflow Scheduler initiates a property scraping DAG.

Extraction: Python scripts scrape rental listings and store them in the database.

Validation: Airflow tasks verify the data quality (checking for nulls or duplicates).

BI Update: Upon success, a final task sends a request to the Tableau API to refresh the dashboard extracts.
