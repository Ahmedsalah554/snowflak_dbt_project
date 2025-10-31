# Snowflake DBT Project

![DBT](https://img.shields.io/badge/dbt-v1.0+-orange)
![Snowflake](https://img.shields.io/badge/Snowflake-Integration-blue)
![Build](https://img.shields.io/badge/build-passing-brightgreen)
![License](https://img.shields.io/badge/license-MIT-lightgrey)

This project is a **DBT (Data Build Tool)** implementation for data transformation and modeling on **Snowflake**.  
It follows a modular structure that supports scalability, version control, and collaborative analytics workflows.

---

## 🚀 Project Overview
The **Snowflake DBT Project** enables efficient transformation and modeling of raw data stored in Snowflake.  
It provides a clean and reusable architecture for building data models, tests, macros, and documentation.

---

## 🗂 Project Structure
```
snowflak_dbt_project/
│
├── analyses/          # Custom analytical SQL queries and reports
├── dbt-env/           # Environment setup or configuration files
├── macros/            # Reusable SQL macros and utility functions
├── models/            # Core, staging, and mart models
├── seeds/             # Static CSV data files loaded into the warehouse
├── snapshots/         # Snapshot logic for tracking slowly changing data
├── tests/             # Custom schema and data quality tests
│
├── dbt_project.yml    # Main DBT project configuration
├── README.md          # Project documentation
└── .gitignore         # Git ignore rules
```

---

## ⚙️ Requirements
Before you begin, make sure you have the following installed:

- Python 3.10+
- dbt-core and dbt-snowflake
- Access credentials to a Snowflake account
- Git (for version control)
- Optional: Virtual environment for isolation

Install dbt and the Snowflake adapter:

```bash
pip install dbt-core dbt-snowflake
```

---

## 🧠 Configuration
1. Create or update your `profiles.yml` file (usually located at `~/.dbt/profiles.yml`):

```yaml
snowflake_dbt_project:
  target: dev
  outputs:
    dev:
      type: snowflake
      account: <your_account>
      user: <your_user>
      password: <your_password>
      role: <your_role>
      database: <your_database>
      warehouse: <your_warehouse>
      schema: <your_schema>
      threads: 4
      client_session_keep_alive: False
```

2. Test the connection:
```bash
dbt debug
```

---

## 🏗 Running the Project
Once configured, run the transformations:

```bash
# Run all models
dbt run

# Run tests
dbt test

# Build documentation site
dbt docs generate
dbt docs serve
```

---

## 📊 Example Folder Breakdown

- `models/staging/` → Cleans and standardizes raw Snowflake data.  
- `models/marts/` → Business logic and reporting tables.  
- `macros/` → Shared SQL logic for reusability.  
- `snapshots/` → Historical tracking for SCD (Slowly Changing Dimensions).  
- `tests/` → Ensures data quality and schema consistency.

---

## 🤝 Contribution
Contributions are welcome!  
Fork the repo, create a feature branch, and open a pull request.

---

## 📄 License
MIT License — see the `LICENSE` file for details.

---

## 📬 Contact
For questions or support, open an **Issue** on GitHub or contact the repository owner.
