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

## Loading the data into MySQL :
1. You'll find a command to import and export data by clicking on the DB name.
2. open the terminal and upload the shopping.sql file.
3. command should be like this. ------> mysql -h shopping-database-server.mysql.database.azure.com -u ineuron -p <shopping.sql --------where shopping.sql is a SQL filename
4. Enter the Password & if u see no error then data is loaded Successfully.
5. copy the connect from "run from browser" command and paste it in the new terminal to see the data in MySQL.
   
![Screenshot (484)](https://github.com/shekharj21/shekharj21/assets/54074505/f5b722d4-7337-4560-8bfa-7e9609069fb7)

## Tables in the database :

![IMG_6186](https://github.com/shekharj21/shekharj21/assets/54074505/d38c65f5-880e-449d-99f0-a9ccd90c0b05)


## Configure Azure Data Factory with Azure DevOps Repo :
1. Search for data factory.
2. click and give a name to it.
3. use RG-DEV resource group.
4. create the data Factory.
5. open an account on (dev.azure.com) if not created because we will be using code Repo.
6. create Organization.
7. come again to data factry and select Azure Dev Code repo
8. enter all the details from drop down arrow and connect the repo with azure data factory.
9. add configuration as "main"

### Error handling (Organization name not available in Data factory)
10. If facing any error seeing organization name in data factory then go back to azure dev services and on the right you'll see your profile.
11. select profile and change directory. after that go to organization setting and go to "Microsoft Entra" and make sure azure active directory is connected.
12. then go again to the azure data factory now you'll see the organization name.

## Create pipeline
1. create Pipeline and assign a name to it and save it.
2. now go to azure devops repo to see something is generating.

