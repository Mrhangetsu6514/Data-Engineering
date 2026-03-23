🚀 Data Engineering Pipeline: Airflow, Docker, & Tableau
Orchestrating the Matzati.casa Property Platform & BI Automation
📂 Project Structure
A clean, modular organization is maintained to ensure the scalability of the Matzati property listing tools:

Plaintext
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
