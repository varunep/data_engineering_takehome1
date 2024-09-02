## Deployment to be done

### 1. Environment Preparation
- Ensure Spark cluster is configured and running.
- Install necessary Python libraries and Java packages on all nodes.

### 2. Packaging
- Bundle .py and dependencies into a zip file.
- Upload dependencies to a shared location (e.g., S3 bucket, ADLS).

### 3. Configuration
- Set Spark configurations based on the workload.

### 4. Deployment
- Submit job to Spark cluster using the following command:
  ```bash
  spark-submit --master yarn \
               --deploy-mode cluster \
               --conf spark.yarn.jars=hdfs:///path/to/jars \
               filename(.py)

   Cluster Deployment: For production environments, submit the PySpark job to a Spark cluster manager like YARN, Mesos, or Kubernetes. 
   Use CLI or console to deploy , schedule if using AWS EMR or Databricks.

   Automated Deployment: Integrate with CI/CD tools like Jenkins, GitHub Actions, or GitLab CI/CD to automate the deployment of PySpark jobs.

#### 5. Monitoring and Logging
Monitor job performance using Spark UI. or logs moonitoring services like Cloud watch if using Cloud services like AWS.

### 6. Data security
Data at Rest: Encrypt sensitive data stored in storage systems (eg. HDFS, S3).
Authorization: Use role-based access control (RBAC) to limit access to resources based on user roles and responsibilities.

### 7. Triggering the job
We can use variety of approaches to trigger our pyspark job depeding upon the requirement.

1 .  Using Workflow Orchestration Tool like Apache Airflow.
2. We can trigger the job using REST API endpoint.
3. CI/CD pipeline : If code is part of a larger project, we might want to integrate it into a CI/CD pipeline using Jenkins, GitLab CI, or GitHub Actions. These tools allow us to automatically trigger our PySpark jobs as part of your build and deployment process.
4. AWS Lambda : We can use AWS lambda to create event based triggers on the S3, which will trigger the Spark job on AWS environment based on an event.


### 8.Challenges

Some Columns were having complex texts and wrere large strings with special charecters so it was difficult to clean/transform it

