# Covid19
## Problem Description

Welcome to the COVID-19 Data Engineering Project! The main objective of this project is to apply data engineering concepts and utilize various tools on AWS to create an end-to-end data engineering solution for COVID-19 data analysis.

The project follows an Extract, Transform, Load (ETL) approach, where users can extract, load, and transform the data to gain valuable insights. The ultimate goal is to create a simple data engineering project that enables efficient handling and analysis of COVID-19 data.

## Architecture

![Example Image](https://github.com/umidmirzaev/Covid19/blob/main/images/Architecture.png?raw=true)

## Important prerequisites

1. Create an IAM role named "s3-glue-role": This role should grant Glue the necessary permissions to call AWS services on your behalf.
2. Create Redshift Cluster and Configure VPC Security Group: Set up a Redshift cluster and adjust the VPC security group to allow inbound access by adding a new rule for your IP address.
3. Create an IAM role named "redshift_s3_access": This role should provide Redshift with permission to access data stored in Amazon S3.
4. Prepare Glue Environment for Redshift Job: Prior to creating a job in Glue, download the necessary external redshift-connector and boto3 library. Since Glue has limited support for default libraries, create a zip package containing these libraries and upload it to an S3 bucket.
5. Establish JDBC Connection to Redshift Cluster:To ensure successful execution of a job, create a JDBC connection to your Redshift cluster.
6. Create VPC Endpoint for Amazon S3:It is essential to create a VPC endpoint for Amazon S3 to establish connectivity between the VPC of your Glue job and S3.

## Key steps

1. Upload 'COVID-19 Data Lake' from a Registry of Open Data on AWS to Amazon S3: The project begins by uploading the 'COVID-19 Data Lake' from a Registry of Open Data onto the Amazon S3 storage service. 
2. Create and Run Crawlers in Amazon Athena: Next, we set up and execute crawlers within Amazon Athena. These crawlers scan the tables stored in the Amazon S3 buckets, extracting structured data and making it easily accessible for analysis.
3. Python ETL Job: We implement an ETL job in Python, which focuses on converting the relational data model into a dimensional data model using a STAR schema. 
4. Upload Transformed Data to Amazon S3: After the ETL job is executed, the resulting DataFrame is converted into a CSV-formatted string representation. This transformed data is then uploaded back to an Amazon S3 bucket for storage and convenient access.
5. Create, Configure VPC Networking, Connect, and Run ETL Job in AWS Glue: In this step, we create and configure Virtual Private Cloud (VPC) networking. By establishing secure communication and connectivity, we can seamlessly run the ETL job in AWS Glue to create tables in Amazon Redshift. 

## Tech Stacks

To build an end-to-end data pipeline for this project, we'll be utilizing the following tools:

- **Python**: including data extraction, transformation, and loading.
- **SQL**: querying and manipulating data within databases.
- **Amazon Athena**: Athena is instrumental in running queries on our data stored in Amazon S3. It allows us to analyze structured and semi-structured data using standard SQL syntax.
- **AWS Glue**: Glue is an ETL (Extract, Transform, Load) service provided by AWS. We'll utilize it to create and run our ETL jobs, transforming data between various formats and storing it in the desired destination.
- **Amazon Redshift**: Redshift is a fully-managed data warehousing service offered by AWS. It will serve as our storage and querying solution for large-scale data analysis.
- **Amazon S3**: S3 (Simple Storage Service) is an object storage service on AWS that will be used to store our raw and transformed data. It provides high durability, availability, and scalability.
- **IAM (Identity and Access Management)**: IAM will be employed to manage user access and permissions to various AWS resources, ensuring secure and controlled data handling.

## Data Model

Converting our relational data model to dimensional model by building a STAR schema.

Before data modeling:

![Example Image](https://github.com/umidmirzaev/Covid19/blob/main/images/before.jpg?raw=true)

After data modeling:

![Example Image](https://github.com/umidmirzaev/Covid19/blob/main/images/after.jpg?raw=true)


## Further Improvement

In addition to the project's results, there exist opportunities for analysis and visualization. By establishing a connection between Redshift and visualization tools such as Tableau or Power BI, it becomes feasible to conduct analysis and construct visualization tables. This integration enables users to explore the data further, extract meaningful insights, and present them in visually informative formats.



