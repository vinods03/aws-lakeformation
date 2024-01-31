# aws-lakeformation

A lakeformation BLUEPRINT is essentially a glue workflow that has a glue job to move data across layers, a glue crawler to create glue data catalog tables etc. 
Refer "3. Populate tables in mysql RDS and bring data into S3 raw layer.txt" for more details.

Row or column level security is possible by using IAM users/roles/groups etc. 
More scalable way of doing this is through LF-TAGS (LAKEFORMATION-TAGS). 
Refer 5. Table permissions - columns and rows filters.txt for this and also 6. Table - enrich table metadata.txt for a related concept.

AWS Glue DATABREW is a visual data preparation tool that enables users to analyse, clean and normalize data without writing any code, to reduce the time it takes to prepare data for analytics and machine learning (ML) by up to 80% compared to today’s conventional, code-based data preparation. You can choose from over 250 pre-built transformations to automate data analysis/preparation tasks, such as filtering anomalies, converting data to standard formats, and correcting invalid values, all without the need to write code. 

There are 2 main aspects to DataBrew:
a. DQ profile job with or without DQ rules. 
Without DQ rules means just analysing the data like min value, max value, max length of a string, missing values etc.
With DQ rules means checking for some DQ aspects like value in a column is other than x,y,z or the format of the column is not as expected etc.
b. Data cleansing / transformation job using RECIPES.
You open a project, dataset. Then add transformations as steps into a "Recipe". You then publish the recipe. Create a job out of the Recipe and execute it.
Refer 7. Databrew - Clean the raw data and move into processed layer.txt for more details.

Automated / Manual SENSITIVE DATA DISCOVERY is possible using Amazon Macie.
You can use Managed data identifiers or create your own Custom data identifiers to identify the sensitive data in your dataset.
Refer 10. Macie - Sensitive data discovery.txt for more details.
