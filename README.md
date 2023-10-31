# Magu-HDSS-ALPHA-Data_to_OMOP-ETL
This repository contains code, and information to extract, transform and load ALPHA source data from Magu HDSS (Tanzania) to an OMOP database
The data is part of the ALPHA Network HIV incidence and mortality specs found here https://alpha.lshtm.ac.uk/
STEPS FOLLOWED

Profiling and Exploratory data analysis:
White Rabbit and R used to profile and generate scan report and EDA. Check the link for the EDA https://docs.google.com/spreadsheets/d/1h6A-uOf4lrWZMCKhoNzSkktMv10lhgM7SH-CcmCHgZo/edit#gid=0

Mapping and Implementation Guides:
Rabbit in a hat, Athena and Usagi tools were used to create mappings from source data to OMOP terminologies

Extract Transform Load :
We used PostgreSQL as OMOP instance database. Penataho and SQL scripts for transforming source codes to OMOP terminologies.

Data Quality Assurance:
OHDSI library for quality assurance of the CDM 'DataQualityDashboard' was installed and run against the OMOP database resulting in 98% score

Generating Aggregated (Results tables) data for Atlas using Achilles R library by OHDSI for data characterization tool.

Visualization in Atlas :

Aggregated data(results tables), OMOP tables and vocabulary tables were integrated with Atlas and webAPI.

https://github.com/OHDSI/WebAPI/wiki/CDM-Configuration

Migration to OHDSIonAWS:
Aggregated data migrated to AWS simple storage service (S3) and then to AWS Redshift database and later linked to AWS Atlas for wider audience based on access level.
