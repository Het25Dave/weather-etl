Overview
========

🌦️ Weather Data ETL Pipeline with Airflow and PostgreSQL
========================================================
This project implements a complete ETL (Extract, Transform, Load) pipeline to collect and store weather data using Apache Airflow and PostgreSQL.

🔧 Project Overview
===================
The pipeline automates the following steps:

**Extract:** Weather data is fetched in JSON format from a public API using latitude and longitude parameters.
**Transform:** The raw JSON response is processed and cleaned to extract relevant fields such as temperature, humidity, weather condition, and timestamp.
**Load:** The transformed data is inserted into a PostgreSQL database for structured storage and future analysis.

⚙️ Tools & Technologies
=======================
**Apache Airflow:** For scheduling, managing, and monitoring the ETL workflow.
**Python:** Used for data extraction, transformation, and task definitions.**
**PostgreSQL:** Serves as the data warehouse for storing weather records.
**Docker & Docker Compose:** To containerize and orchestrate the Airflow, PostgreSQL, and pgAdmin services.

📦 Architecture
===============
The ETL process is defined as a DAG in Airflow.

The DAG contains separate tasks for extraction, transformation, and loading.
Data is stored in a relational format inside a PostgreSQL table.
Optional visualization or querying can be done using pgAdmin.

Project Startup
===============

To fireup Astronomer for your project, enter **'astro dev init'** command in your terminal, which generates a project.

Project Contents
================

Your Astro project contains the following files and folders:

- **dags:** This folder contains the Python files for your Airflow DAGs. 
- **Dockerfile:** This file contains a versioned Astro Runtime Docker image that provides a differentiated Airflow experience. If you want to execute other commands or overrides at runtime, specify them here.
- **include:** This folder contains any additional files that you want to include as part of your project.
- **packages.txt:** Install OS-level packages needed for your project by adding them to this file.
- **requirements.txt:** Install Python packages needed for your project by adding them to this file. 
- **plugins:** Add custom or community plugins for your project to this file. 
- **airflow_settings.yaml:** This file contains all the information related to Connections, Varialbles and Pools related to Airflow UI required for the project.

Deploy Your Project Locally
===========================

Start Airflow on your local machine by running **'astro dev start'**.
To Restart your project run the command **'astro dev restart'**. 

This command will spin up five Docker containers on your machine, each for a different Airflow component:

- **Postgres:** Airflow's Metadata Database
- **Scheduler:** The Airflow component responsible for monitoring and triggering tasks
- **DAG Processor:** The Airflow component responsible for parsing DAGs
- **API Server:** The Airflow component responsible for serving the Airflow UI and API
- **Triggerer:** The Airflow component responsible for triggering deferred tasks
