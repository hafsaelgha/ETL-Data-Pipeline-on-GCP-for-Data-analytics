# Uber-Data-analytics-ETL-Data-Pipeline-on-GCP

## 1-Introduction
The goal of this project is to perform data analytics on Uber data using various tools and technologies, including GCP Storage, Python, ComputeEngine, Mage Data Pipeline Tool, BigQuery, and Looker Studio.

## 2-Architecture
![ETL GCP  - Page 3](https://github.com/hafsaelgha/ETL-Data-Pipeline-on-GCP-for-Uber-Data-analytics/assets/99973359/78b0e7ea-f498-48ab-8ac8-fa055dde08f3)
- [ ] GCS : google cloud storage is a fully managed object storage that use stores objects into bucket. We can define the storage class, (standard in our case), the location type (multi-region),the ACL (public access), the uploads type… 
- [ ] Compute engine : it’s a virtual machine provided by Google Cloud to host our services, we changed its configuration depending on our use case (see section below).
- [ ] Mage : is a modern data tool created by an Ex Airbnb Engineer, which aims to be a competitor of Airflow but with more advanced services for data pipeline and with a nice UI which make it an easy cool modern tool ! 
- [ ] BigQuery : its a petabyte scale analytics data warehouse that allows us to execute fast SQL queries across large datasets.
- [ ] Looker Studio : free tool that turns your data into informative, easy to read, easy to share, and fully customizable dashboards and reports.


## 3-Data Dimensional modelling
![data dimensional modeling ](https://github.com/hafsaelgha/ETL-Data-Pipeline-on-GCP-for-Uber-Data-analytics/assets/99973359/a37510c8-3fbe-4f39-b726-e4cb54a13add)

## Steps and Remarks 
### I will include errors to avoid during this project too ! 
## 4-Storage on GCS
Converting from parquet file to csv file and store it on google cloud storage.
The Parquet format is based on a columnar structure, which means that data is organized in columns rather than rows. This allows for efficient data compression and better resource utilization when executing queries.
![object ](https://github.com/hafsaelgha/ETL-Data-Pipeline-on-GCP-for-Uber-Data-analytics/assets/99973359/678293e7-2859-4f1b-8800-4881caca399c)
**About Configuration of your bucket** : 
**Public API Object** : to extract data from it as a **public API** by using it’s URL.

## 5-Compute Engine 
See the basic configuration I used for my instance : 
![VM basic info](https://github.com/hafsaelgha/ETL-Data-Pipeline-on-GCP-for-Uber-Data-analytics/assets/99973359/597475c4-b6cb-4e9c-9344-541453cc87d1)
![VM config](https://github.com/hafsaelgha/ETL-Data-Pipeline-on-GCP-for-Uber-Data-analytics/assets/99973359/fa05ac9c-83e1-40a7-8c47-facf9d885ea1)
**Firewall : allow HTTP and HTTPS traffic**
Check if its allow access to port running mage on it (configure the **VPC network** by adding a **mage-access-rule** on protocol tcp and port 6789)

![VM firewalls](https://github.com/hafsaelgha/ETL-Data-Pipeline-on-GCP-for-Uber-Data-analytics/assets/99973359/5c911d00-dc9d-4aca-9311-7cd467442af4)

Install python3 and mage on it then Start mage project then Connecting to the machine trough its **IP4:6789** Then you have accezs to mage online !

![running mage](https://github.com/hafsaelgha/ETL-Data-Pipeline-on-GCP-for-Uber-Data-analytics/assets/99973359/1fb7e78d-ee46-4bb3-bb4a-6bdf20314e96)

## 6-Mage 
**Simplified UI !**
Mage provides a pre defined function for every stage on yout pipeline, all you have to do is to make it suits your use case ! 
![mage UI](https://github.com/hafsaelgha/ETL-Data-Pipeline-on-GCP-for-Uber-Data-analytics/assets/99973359/711d7a77-02b8-4109-89b3-c8e14074ce65)

## 7-ETL 
Every stage is shown as a block that rely on the other block : 
![final ETL ](https://github.com/hafsaelgha/ETL-Data-Pipeline-on-GCP-for-Uber-Data-analytics/assets/99973359/47938ac4-dce3-4159-a82f-55f10ca931c7)

## 8-BigQuery 
### Service account 
Check the service account to add ur credential to **config.yaml** file
![service account](https://github.com/hafsaelgha/ETL-Data-Pipeline-on-GCP-for-Uber-Data-analytics/assets/99973359/4598baf7-ce37-4801-b422-8df69fb63b6c)

### Query for analytic table 
![query for analytic table](https://github.com/hafsaelgha/ETL-Data-Pipeline-on-GCP-for-Uber-Data-analytics/assets/99973359/8eb37870-3729-4ba7-9913-cf965ee0b06f)

### Analytic table schema 
![analytic table schema](https://github.com/hafsaelgha/ETL-Data-Pipeline-on-GCP-for-Uber-Data-analytics/assets/99973359/fc25f84b-f2b6-45a9-b056-a49813945891)

### 9-Dashboard 
![dashboard](https://github.com/hafsaelgha/ETL-Data-Pipeline-on-GCP-for-Uber-Data-analytics/assets/99973359/30b0ed7b-9e85-4e82-8893-ebbdab999a08)

![dashboard 2](https://github.com/hafsaelgha/ETL-Data-Pipeline-on-GCP-for-Uber-Data-analytics/assets/99973359/c430849e-bf1c-4052-a1e0-e467461bc348)

and here is the final link for Dashboard : https://lookerstudio.google.com/s/rgrecwiQS2c
















