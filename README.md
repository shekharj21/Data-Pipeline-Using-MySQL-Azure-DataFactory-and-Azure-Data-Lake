# Data-Pipeline-Using-MySQL-Azure-DataFactory-and-Azure-Data-Lake

## Understanding the problem :
We are using MySQl database (OLTP) system. We will be Extracting the data from MySQL to another external storage so the data Engineering team can dump this records in Data Warehouse (OLAP) System.
We will be using azure blob storage to store the extracted Data from MySQL or OLTP system. we can't move the data from MYSQL to Datawarehouse is because if some other team might need access to the data for analysis so its better to export the data to external storage such as azure blob storage.

## Creating 3 Resource Groups in Azure Portal
1. RG-DEV (Developer Resource Group)
2. RG-Stage (Staging Resource Group)
3. RG-PROD (Production Resource Group)

![Screenshot (480)](https://github.com/shekharj21/shekharj21/assets/54074505/ecee3836-0395-49a1-80c0-b14406bfa847)

## Creating MYSQL Server Database :
1. open azure console.
2. select azure database for MYSQL servers.
3. select RG-DEV Resource Group
4. add name, region and MySQL version = 5.7
5. add firewall ports etc

![Screenshot (481)](https://github.com/shekharj21/shekharj21/assets/54074505/bbd0b97c-f87f-462b-b02b-0318f6dbdf71)

## Connecting and Quering MySQL DB :
1. select the database under RG-DEV.
2. on the left side click connect.
3. choose way to connect it ( I am Choosing Browser ).
4. Copy the command under "Connect From Browser".
5. click on azure terminal at the top and paste it &  enter the password which you chose during MYSQL creation.
6. we'll see mysql running in the azure terminal.


![Screenshot (482)](https://github.com/shekharj21/shekharj21/assets/54074505/0a24f01a-62b0-45f8-befb-1f221ef8d7aa)


