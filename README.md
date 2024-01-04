# Data-Pipeline-Using-MySQL-Azure-DataFactory-and-Azure-Data-Lake

## Understanding the problem :
We are using MySQl database (OLTP) system. We will be Extracting the data from MySQL to another external storage so the data Engineering team can dump this records in Data Warehouse (OLAP) System.
We will be using azure blob storage to store the extracted Data from MySQL or OLTP system. we can't move the data from MYSQL to Datawarehouse is because if some other team might need access to the data for analysis so its better to export the data to external storage such as azure blob storage.

## Creating 3 Resource Groups in Azure Portal
1. RG-DEV (Developer Resource Group)
2. RG-Stage (Staging Resource Group)
3. RG-PROD (Production Resource Group)

![Screenshot (480)](https://github.com/shekharj21/shekharj21/assets/54074505/ecee3836-0395-49a1-80c0-b14406bfa847)
