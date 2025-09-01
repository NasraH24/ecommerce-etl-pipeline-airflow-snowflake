# E-commerce ETL Pipeline with Airflow, Snowflake and Terraform

##  Project Overview
This project is an end-to-end **ETL pipeline** designed for **e-commerce transaction data**.  
The workflow:
- **Extracts** raw transaction data from local CSV files  
- **Transforms and cleans** the data using **Python (Pandas)**  
- **Loads** the processed data into **AWS S3** for staging  
- **Orchestrates** tasks with **Apache Airflow**  
- **Loads** cleaned tables into **Snowflake** for analysis and reporting  
- **Automates** the infrastructure setup using **Terraform**.

This pipeline simulates a real-world scenario for handling **dirty retail datasets**, applying best practices in **data transformation**, **cloud storage**, and **data warehousing**.



## Project Structure

```
your-snowflake-project/
├── airflow/                   -> Airflow DAGs, logs, plugins
│ ├── dags/                    -> DAGs for ETL pipeline
│ ├── logs/                    -> Airflow logs 
│ └── plugins/                 
│                              
├── assets/                    
│ └── datasets/                
│ ├── original_file/           -> Raw CSVs
│ ├── transformed_file/        -> Cleaned CSVs 
│ └── transformed_tables/      -> split tables
│
├── docker-compose.yaml        -> Airflow & Postgres
├── Makefile                   ->  Docker CLI shortcuts
├── python_scripts/            -> Python scripts for ETL tasks
├── terraform/                 -> Terraform scripts 
├── .env
├── .env.example               -> env vars template
├── .gitignore 
└── README.md 

```


##  Tech Stack
- **Python** (Pandas, Boto3, Snowflake Connector)  
- **Apache Airflow**  
- **AWS S3**  
- **Snowflake**  
- **Terraform**  
- **Docker & Docker Compose**

---

## Getting Started
### 1. Clone the repository
```bash
git clone https://github.com/YOUR_USERNAME/ecommerce-etl-pipeline-airflow-snowflake.git
cd ecommerce-etl-pipeline-airflow-snowflake
```


### 2. Set up environment variables

Copy .env.example to .env and fill in your credentials:

```bash 
cp .env.example .env
```
Edit .env with your real values:
```bash 
AWS_ACCESS_KEY_ID=your_key
AWS_SECRET_ACCESS_KEY=your_secret
AWS_DEFAULT_REGION=eu-west-2
S3_BUCKET_NAME=your_s3_bucket
SNOWFLAKE_ACCOUNT=your_snowflake_account
SNOWFLAKE_USER=your_username
SNOWFLAKE_PASSWORD=your_password
```
### Security

.env is .gitignored and will never be committed.

For production pipelines, use IAM least-privilege policies and Secrets Manager for secure credentials.



📄 License

This project is for educational and portfolio purposes.




